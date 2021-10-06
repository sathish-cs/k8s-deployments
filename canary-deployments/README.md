### Canary deployments

Canary deployments are useful to make new application only for small subset of users. It helps to identify bugs and issues, this helps us to fix before rolling out the feature.

Here we have two versions of application. Old application is running with 4 and new application is running with 1 replicas. 


`kubectl apply -f web-v1.yaml`

`kubectl apply -f web-v2.yaml`


Both applications is having same label hence most of the traffic goes to old version but only few can see version 2.

Please check canary strategies using below link.


[Application deployed using canary](http://34.149.151.182/canary/) 

Here we can see both v1 and v2 but once we are sure about the application stablity then v2 can be ready to rollout completely.

Note: In production only 10-15% traffic routes to new version. 
