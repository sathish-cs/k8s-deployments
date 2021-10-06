## Blue Green deployment strategies.

Blue green is a deployment model that gradually transfer traffic from old to new application. Old version called as blue and new version called as green. Its gives rapid way to rollback in case of issues with new deployment always can be rollback to old application (blue)


Application is deployed and running with v1 image. 

`kubectl create -f web-v1.yaml`

Now developer pushed image with new features and tagged image as v2. 

`kubectl create -f web-v2.yaml`

Now both v1 and v2 is deployed on the cluster, but before making new application to live it has to be througly tested. Once tested traffic can be redirect to v2.

Both v1 and v2 is having diferrent labels and service is pointed to v1, that needs to be change to v2 to make it live. 

* Patch used to update any config like deployments, services etc. Services manage pods using the labels using patch we are going to modify those labels.

` kubectl patch svc web -p '{"spec":{"selector":{"version":"v2.0"}}}'` 

Now services manage pods which is having `version=v2.0` and latest appication is live.

