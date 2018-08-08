A basic exploration of kubernetes
==============
If kubernetes means captain in greek, this is a pirate captain with a casual attitude towards best practices...
-------------
_...but this is how I am learning and exploring the multitude of ways you can deploy and use the many different pieces of kubernetes, the ever growing container orchestration system from Google._

_I acknowledge that much of what is here is hardly ideal or enterprise grade but my goal is to develop a conceptual and working understanding of various types of controllers, services, storage mechanisms and so on so when the time to tackle enterprise solutions comes, I can successfully navigate those problems._

This is serving as a general area for me to store files and write yamls for implementation them on a GCP account BUT the primary infrastructure that exists here is based around showing the latest equity prices for specific companies via an nginx web server and supported by a elasticsearch database.  It will contact the IEX exchange and their fantastic, free financial API (https://iextrading.com/developer/docs/) and pull down the latest price, then storing it in the elasticsearch engine before it is retrieved by the nginx webserver as it deploys.  

See below for a basic diagram I drew.

#imagediagramhere

Here is general list of improvements and concepts I'd like to approach and/or implement (some soon, some not so soon) as this potentially grows before my GCP dollars run out...

* automate the updating of the recent price page within the nginx image, potentially by making a NFS server on the cluster and mounting the directory where nginx looks for it's files or a configmap and triggering an update when the file changes - but again, nginx webpages are not exactly my endgoal (ingress is another story)
* get the jobs and initial commands driving some of the actions to run off a file stored remotely, or automate the build from developer updates to just the code, potentially off a github webhook.
* Use Istio or Kibana etc. to log and monitor these various pieces
* Better understand security and best practices for everything, from tackling vulnerabilities to just building a smarter, safer infrastructure.
* Integrate CI/CD pipelines for this entire process
* Various things like taints, secrets, best DNS practices, judging resource needs accurately, 
* Better understanding networking best practices, even with interaction between multiple clusters
* Integrate this with a VM or cluster of VMs on my homeserver and build a hybrid architecture.


