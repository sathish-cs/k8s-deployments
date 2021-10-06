### Canary deployments

Canary deployments are useful to make new application only for small subset of users. It helps to identify bugs and issues, this helps us to fix before rolling out the feature.

Here we have two versions of application. Old application is running with 4 and new application is running with 1 replicas. 


`kubectl apply -f web-v1.yaml`

`kubectl apply -f web-v2.yaml`


Both applications is having same label hence most of the traffic goes to old version but only few can see version 2.

