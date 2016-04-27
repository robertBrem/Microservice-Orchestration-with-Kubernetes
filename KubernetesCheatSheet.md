Kubernetes CheatSheet
=====================

Debugging
---------
* Lists all nodes  
  `kubectl get no`  
  `kubectl get nodes`  
* Lists all pods  
  `kubectl get po`  
  `kubectl get pods`  
* Lists all replication controllers  
  `kubectl get replicationcontrollers`  
  `kubectl get rc`  
* Lists all services  
  `kubectl get services`  
  `kubectl get svc`  

* Label filtered list of pods  
  `kubectl get po -l name=reservation,version=2.0.0`  

* Receive events for changes depending on pods  
  `kubectl get po --watch-only`  

* Detailed information about a node, pod, replication controller or service  
  `kubectl describe node adessoch-kubernetes-demo02.test-server.ag`  
  `kubectl describe pod reservation-v2-vtgks`  
  `kubectl describe rc reservation-v2`  
  `kubectl describe svc reservation`  
  
Declarations
------------
[replication controller](https://gist.github.com/robertBrem/3065cca2031f16d7f838)  
[service](https://gist.github.com/robertBrem/68706f161388b7307bb0)  

Actions
-------
* Delete a pod  
  `kubectl delete pod reservation-v2-bjymj`  
* Scale a replication controller  
  `kubectl scale rc reservation-v2 --replicas=3`  
* Update a service  
  `kubectl patch service reservation -p '{"spec":{"selector":{"version":"3.0.0"}}}'`  
* Rolling update  
  `kubectl rolling-update reservation-v2 -f ctrl/reservation-v3.yml --update-period=1s`  
