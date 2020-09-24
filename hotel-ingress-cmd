krishna@evoke:~$ kubectl apply -f hotel-ingress.yml 
namespace/hotel unchanged
ingress.extensions/hotel-ingress configured
deployment.apps/hotel unchanged
service/hotel-svc unchanged
krishna@evoke:~$ kubectl get ns
NAME                   STATUS   AGE
default                Active   2d7h
hotel                  Active   46m
kube-node-lease        Active   2d7h
kube-public            Active   2d7h
kube-system            Active   2d7h
kubernetes-dashboard   Active   2d6h
krishna@evoke:~$ kubectl describe namespace hotel
Name:         hotel
Labels:       <none>
Annotations:  Status:  Active

No resource quota.

No LimitRange resource.
krishna@evoke:~$ kubectl get all --namespace hotel
NAME                         READY   STATUS    RESTARTS   AGE
pod/hotel-6c597bfb95-82vz2   1/1     Running   0          47m
pod/hotel-6c597bfb95-btdf9   1/1     Running   0          47m

NAME                TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)   AGE
service/hotel-svc   ClusterIP   10.105.8.230   <none>        80/TCP    47m

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/hotel   2/2     2            2           47m

NAME                               DESIRED   CURRENT   READY   AGE
replicaset.apps/hotel-6c597bfb95   2         2         2       47m
krishna@evoke:~$ minikube service
💡  You must specify a service name
krishna@evoke:~$ minikube service list
|----------------------|------------------------------------|--------------|-----|
|      NAMESPACE       |                NAME                | TARGET PORT  | URL |
|----------------------|------------------------------------|--------------|-----|
| default              | kubernetes                         | No node port |
| hotel                | hotel-svc                          | No node port |
| kube-system          | ingress-nginx-controller-admission | No node port |
| kube-system          | kube-dns                           | No node port |
| kubernetes-dashboard | dashboard-metrics-scraper          | No node port |
| kubernetes-dashboard | kubernetes-dashboard               | No node port |
|----------------------|------------------------------------|--------------|-----|
krishna@evoke:~$ minikube service hotel-svc -n hotel --url
😿  service hotel/hotel-svc has no node port
krishna@evoke:~$ kubectl get ingress -n hotel --watch
NAME            CLASS    HOSTS               ADDRESS          PORTS   AGE
hotel-ingress   <none>   hotel.example.com   192.168.99.112   80      48m
^Ckrishna@evoke:~$ 

