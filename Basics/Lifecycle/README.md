This manifest file is to understand lifecycle of a pod/deployment.

The lifecycle seperates into 2;
Init container; image busybox starts and dies after 10seconds.
Main container(PostStart > Readiness&Liveness Probe > preStop); 
-Busybox image get created. 
-Echo Running in file /timing and dies after 120 seconds. 
-echo postStart in /timing file and sleep after 10seconds. echo end postStart
-Readiness&liveness probes starts after 35seconds(initialDelaySeconds) and echo's Readiness&Liveness Probe in /timing file.
-echo preStop in /timing and sleep after 10seconds.

Pod status acts as; Init:0/1 > Podinitializing > Running > Completed