ADD
===
ADD is also like COPY to copy the content inside the image. But ADD has 2 extra capabilities

1. It can directly fetch the content from internet
2. It can directly untar the file inside container/image



98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ git pull
remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 8 (delta 4), reused 7 (delta 3), pack-reused 0 (from 0)
Unpacking objects: 100% (8/8), 662 bytes | 662.00 KiB/s, done.
From https://github.com/rajasekharbi/dockerfiles
   5e249a8..129b4d1  main       -> origin/main
Updating 5e249a8..129b4d1
Fast-forward
 ADD/Dockerfile | 4 ++--
 1 file changed, 2 insertions(+), 2 deletions(-)

98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ docker build -t add:v1 .
[+] Building 0.6s (7/7) FINISHED                                                                docker:default
 => [internal] load build definition from Dockerfile                                                      0.0s
 => => transferring dockerfile: 181B                                                                      0.0s
 => [internal] load metadata for docker.io/library/almalinux:9                                            0.1s
 => [internal] load .dockerignore                                                                         0.0s
 => => transferring context: 2B                                                                           0.0s
 => [2/2] ADD https://raw.githubusercontent.com/daws-86s/notes/refs/heads/main/session-53.txt /tmp/sessi  0.1s
 => CACHED [1/2] FROM docker.io/library/almalinux:9@sha256:9c869fd1056a929a1a6c6811a991b5dcb7a1ccfb8e8c4  0.0s
 => => resolve docker.io/library/almalinux:9@sha256:9c869fd1056a929a1a6c6811a991b5dcb7a1ccfb8e8c44165d97  0.0s
 => [2/2] ADD https://raw.githubusercontent.com/daws-86s/notes/refs/heads/main/session-53.txt /tmp/sessi  0.0s
 => exporting to image                                                                                    0.2s
 => => exporting layers                                                                                   0.1s
 => => exporting manifest sha256:fad66b737c2ca7556659cb2c09118201957e28ee88eae6f41c068eeffb562a9f         0.0s
 => => exporting config sha256:3cadc721929e6d678b1ae6da76ff98b3382278a7041e0a8cd7edd4527a63f941           0.0s
 => => exporting attestation manifest sha256:43f840cf38bf7a7247c5785ffcb844d0514f1564090c387c51ab6d7c485  0.0s
 => => exporting manifest list sha256:f839bed9b428d7e81cd18ad2dbaee823010d1fe9acb5d52002edbffdca80888d    0.0s
 => => naming to docker.io/library/add:v1                                                                 0.0s
 => => unpacking to docker.io/library/add:v1                                                              0.0s

98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ docke rps
-bash: docke: command not found

98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ docke run -d add:v1
-bash: docke: command not found

98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ docker run -d add:v1
c8dd2e47c738693f9579542654c250e6cae55c06fbddeae173649db33257d70e

98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ docker ps
CONTAINER ID   IMAGE     COMMAND        CREATED         STATUS         PORTS     NAMES
c8dd2e47c738   add:v1    "sleep 1000"   5 seconds ago   Up 5 seconds             festive_hawking

98.93.25.109 | 172.31.73.177 | t3.micro | https://github.com/rajasekharbi/dockerfiles.git
[ ec2-user@ip-172-31-73-177 ~/dockerfiles/ADD ]$ docker exec -it c8 bash
[root@c8dd2e47c738 /]# env
HOSTNAME=c8dd2e47c738
PWD=/
HOME=/root
LANG=C.utf8
TERM=xterm
LESSOPEN=||/usr/bin/lesspipe.sh %s
SHLVL=1
DEBUGINFOD_IMA_CERT_PATH=/etc/keys/ima:
PATH=/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
_=/usr/bin/env
[root@c8dd2e47c738 /]# cd/tmp/
bash: cd/tmp/: No such file or directory
[root@c8dd2e47c738 /]# cd /tmp/
[root@c8dd2e47c738 tmp]# ls -l
total 4
-rw------- 1 root root 1705 Jan  1  1970 session-53.txt
[root@c8dd2e47c738 tmp]# cat session-53.txt
Notes
#!/bin/bash
[root@c8dd2e47c738 tmp]# exit
exit


ADDing tar file
