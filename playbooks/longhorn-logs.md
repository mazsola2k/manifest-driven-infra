kubectl apply -f longhorn.yaml 
namespace/longhorn-system created
priorityclass.scheduling.k8s.io/longhorn-critical created
serviceaccount/longhorn-service-account created
serviceaccount/longhorn-ui-service-account created
serviceaccount/longhorn-support-bundle created
configmap/longhorn-default-setting created
configmap/longhorn-storageclass created
customresourcedefinition.apiextensions.k8s.io/backingimagedatasources.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/backingimagemanagers.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/backingimages.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/backupbackingimages.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/backups.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/backuptargets.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/backupvolumes.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/engineimages.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/engines.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/instancemanagers.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/nodes.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/orphans.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/recurringjobs.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/replicas.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/settings.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/sharemanagers.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/snapshots.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/supportbundles.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/systembackups.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/systemrestores.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/volumes.longhorn.io created
customresourcedefinition.apiextensions.k8s.io/volumeattachments.longhorn.io created
clusterrole.rbac.authorization.k8s.io/longhorn-role created
clusterrolebinding.rbac.authorization.k8s.io/longhorn-bind created
clusterrolebinding.rbac.authorization.k8s.io/longhorn-support-bundle created
service/longhorn-backend created
service/longhorn-frontend created
service/longhorn-conversion-webhook created
service/longhorn-admission-webhook created
service/longhorn-recovery-backend created
service/longhorn-engine-manager created
service/longhorn-replica-manager created
daemonset.apps/longhorn-manager created
deployment.apps/longhorn-driver-deployer created
deployment.apps/longhorn-ui created




kubectl -n longhorn-system get pods
NAME                                                READY   STATUS              RESTARTS   AGE
csi-attacher-58b6c6fdf6-4sd6g                       0/1     ContainerCreating   0          36s
csi-attacher-58b6c6fdf6-r9n6j                       1/1     Running             0          36s
csi-attacher-58b6c6fdf6-vv2bk                       1/1     Running             0          36s
csi-provisioner-74f57b955d-dkm75                    0/1     ContainerCreating   0          35s
csi-provisioner-74f57b955d-m7czg                    0/1     ContainerCreating   0          35s
csi-provisioner-74f57b955d-tj8mw                    0/1     ContainerCreating   0          36s
csi-resizer-6cfcbf5f5-52kl8                         0/1     ContainerCreating   0          35s
csi-resizer-6cfcbf5f5-ct78k                         0/1     ContainerCreating   0          35s
csi-resizer-6cfcbf5f5-xdjlx                         0/1     ContainerCreating   0          35s
csi-snapshotter-5fcb76449-2rvm2                     0/1     ContainerCreating   0          35s
csi-snapshotter-5fcb76449-n6zmh                     1/1     Running             0          35s
csi-snapshotter-5fcb76449-tnps6                     0/1     ContainerCreating   0          35s
engine-image-ei-5cefaf2b-rbrp8                      1/1     Running             0          53s
instance-manager-ff19d355890ab92648af988c85e2e916   1/1     Running             0          54s
longhorn-csi-plugin-r28xf                           0/3     ContainerCreating   0          35s
longhorn-driver-deployer-664f6d96b9-h9ssn           1/1     Running             0          76s
longhorn-manager-fqvhk                              1/1     Running             0          76s
longhorn-ui-d5f4cddb5-9rzcb                         1/1     Running             0          76s
longhorn-ui-d5f4cddb5-lxvhg                         1/1     Running             0          76s

kubectl get storageclass | grep longhorn
longhorn (default)   driver.longhorn.io   Delete          Immediate           true                   3m51s

 kubectl -n longhorn-system get pods     
NAME                                                READY   STATUS    RESTARTS   AGE
csi-attacher-58b6c6fdf6-4sd6g                       1/1     Running   0          3m50s
csi-attacher-58b6c6fdf6-r9n6j                       1/1     Running   0          3m50s
csi-attacher-58b6c6fdf6-vv2bk                       1/1     Running   0          3m50s
csi-provisioner-74f57b955d-dkm75                    1/1     Running   0          3m49s
csi-provisioner-74f57b955d-m7czg                    1/1     Running   0          3m49s
csi-provisioner-74f57b955d-tj8mw                    1/1     Running   0          3m50s
csi-resizer-6cfcbf5f5-52kl8                         1/1     Running   0          3m49s
csi-resizer-6cfcbf5f5-ct78k                         1/1     Running   0          3m49s
csi-resizer-6cfcbf5f5-xdjlx                         1/1     Running   0          3m49s
csi-snapshotter-5fcb76449-2rvm2                     1/1     Running   0          3m49s
csi-snapshotter-5fcb76449-n6zmh                     1/1     Running   0          3m49s
csi-snapshotter-5fcb76449-tnps6                     1/1     Running   0          3m49s
engine-image-ei-5cefaf2b-rbrp8                      1/1     Running   0          4m7s
instance-manager-ff19d355890ab92648af988c85e2e916   1/1     Running   0          4m8s
longhorn-csi-plugin-r28xf                           3/3     Running   0          3m49s
longhorn-driver-deployer-664f6d96b9-h9ssn           1/1     Running   0          4m30s
longhorn-manager-fqvhk                              1/1     Running   0          4m30s
longhorn-ui-d5f4cddb5-9rzcb                         1/1     Running   0          4m30s
longhorn-ui-d5f4cddb5-lxvhg                         1/1     Running   0          4m30s

