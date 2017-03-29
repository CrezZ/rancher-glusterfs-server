# rancher-glusterfs-server

forked from nixelsolutions/rancher-glusterfs-server

Gluster FS Cluster for being used with Rancher Server

This container create distributed FS for ALL hosts when it run. All data will be copied as a replica in /GLUSTER_BRICK_PATH

Default ENVINRONMENTS:
- ENV ROOT_PASSWORD **ChangeMe**
If password not change container take error.
- ENV SSH_PORT 2222
- ENV SSH_USER root
- ENV SSH_OPTS -p ${SSH_PORT} -o ConnectTimeout=20 -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no
- ENV GLUSTER_VOL ranchervol
- ENV GLUSTER_BRICK_PATH /gluster_volume
- ENV SERVICE_NAME gluster
- ENV DEBUG 0

This service use Rancher DNS service for resolve all containers with name SERVICE_NAME. Each container can be peered with others, Replica count will be equal bricks count. 

Mount to host /data for share volume -v /data:/gluster_volume

