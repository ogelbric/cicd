TMC integration


To check on deployment in cluster: 

k get kustomizations -A

[root@localhost ~]# k get kustomizations -A

NAMESPACE                            NAME              AGE   READY   STATUS
tanzu-continuousdelivery-resources   application1      43h   True    Applied revision: main/7d54a879444ebebb29eb09c4cb9f1a8e95f15498
tanzu-continuousdelivery-resources   tanzu-app         70m   True    Applied revision: main/7d54a879444ebebb29eb09c4cb9f1a8e95f15498
tanzu-continuousdelivery-resources   tanzu-auth        70m   True    Applied revision: main/7d54a879444ebebb29eb09c4cb9f1a8e95f15498
tanzu-continuousdelivery-resources   tanzu-namespace   70m   True    Applied revision: main/7d54a879444ebebb29eb09c4cb9f1a8e95f15498

[root@localhost ~]# k get svc -norfns

NAME    TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)        AGE
nginx   LoadBalancer   10.96.61.129   192.168.2.104   80:30931/TCP   18m

[root@localhost ~]# k get deployments -n orfns

NAME    READY   UP-TO-DATE   AVAILABLE   AGE
nginx   4/4     4            4           18m

[root@localhost ~]# k get pods -n orfns

NAME                     READY   STATUS    RESTARTS   AGE
nginx-54f4568dfc-f5vcf   1/1     Running   0          18m
nginx-54f4568dfc-kxr2g   1/1     Running   0          18m
nginx-54f4568dfc-lgclv   1/1     Running   0          18m
nginx-54f4568dfc-lhfw4   1/1     Running   0          18m

