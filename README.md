# k8s
Kubernetes learning

Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

The name Kubernetes originates from Greek, meaning helmsman or pilot. K8s as an abbreviation results from counting the eight letters between the "K" and the "s". Google open-sourced the Kubernetes project in 2014. Kubernetes combines over 15 years of Google's experience running production workloads at scale with best-of-breed ideas and practices from the community.


#### What is Kubernetes used for?
Kubernetes is used to create applications that are easy to manage and deploy anywhere. When available as a managed service, Kubernetes offers you a range of solutions to meet your needs. Here are some common use cases.
Increasing development velocity
Kubernetes helps you to build cloud-native microservices-based apps. It also supports containerization of existing apps, thereby becoming the foundation of application modernization and letting you develop apps faster.

Deploying applications anywhere
Kubernetes is built to be used anywhere, allowing you to run your applications across on-site deployments and public clouds; as well as hybrid deployments in between. So you can run your applications where you need them.

Running efficient services
Kubernetes can automatically  adjust the size of a cluster required to run a service. This enables you to automatically scale your applications, up and down, based on the demand and run them efficiently.
![image](https://user-images.githubusercontent.com/59694469/220154452-14a3fd33-560f-45d4-9f22-a1a52a70d5e1.png)


#### Minikube
Minikube is an open source tool that enables you to run Kubernetes on your laptop or other local machine. It can work with Linux, Mac, and Windows operating systems. It runs a single-node cluster inside a virtual machine on your local machine.
![image](https://user-images.githubusercontent.com/59694469/220157159-e70d34b5-35ad-4c58-a0e3-51dea458871f.png)


#### kubectl
 kubectl is a command line interface (CLI) for managing operations on your Kubernetes clusters. It does so by communicating with the Kubernetes API/Clustor and manage all the different node doing and what different conatainer running.
 
### Docker Desktop's Kubernetes Setup and Installation - Windows

* Note - It is assumed that Docker Desktop has already been installed and is in a working state.
1. Click the upward-facing arrow on the right side of the Windows System Tray, then click the Docker icon.
![image](https://user-images.githubusercontent.com/59694469/220159055-071506a5-f6f4-4d06-aa8a-956050ecb148.png)

2. Click the Gear icon in the top menu bar of the Docker Desktop application.
![image](https://user-images.githubusercontent.com/59694469/220159286-ab0790b5-2891-4cf3-a1f4-986b0502de3d.png)

3. In the General settings section, make sure that the Use WSL 2 based engine box is checked. This assumes that WSL2 is supported by your OS and has already been installed and enabled. If not, please see the WSL2 setup instructions here.
![image](https://user-images.githubusercontent.com/59694469/220159399-853ac7f6-622d-4f5e-869b-af2261b18bcc.png)

4. Click Kubernetes in the left side menu.

 ![image](https://user-images.githubusercontent.com/59694469/220159501-563ca20d-8f8a-4c21-8743-51ec051bf1aa.png)

5. Check the Enable Kubernetes box and then click the Apply & Restart button.
![image](https://user-images.githubusercontent.com/59694469/220159622-f01c5fcb-8d61-4d84-8137-ac4617cc7e22.png)
![image](https://user-images.githubusercontent.com/59694469/220159713-7a363b75-9b6c-4a85-8476-b9a2dedfb3fd.png)

6. Click Install to allow the cluster installation.
![image](https://user-images.githubusercontent.com/59694469/220159953-c49796e5-86dd-4f79-99d1-7d19943fe231.png)

7. After the installation dialog disappears, look at the bottom left side of the General Settings page and make sure there is a green Kubernetes icon. If you click it, it should display a RUNNING tooltip.

![image](https://user-images.githubusercontent.com/59694469/220160050-c08dccab-a6d4-49a2-92e4-c25ec2b785ce.png)

8. Finally, open up your terminal of choice and make sure that you can run ``` kubectl version ```
![image](https://user-images.githubusercontent.com/59694469/220160425-2c15639e-3663-473d-bb6a-bb7c6250c985.png)

* Note - the client and server can be off by one minor version without error or issue.

### Minikube Setup on Windows
Follow to install : https://minikube.sigs.k8s.io/docs/start

#### Start Minikube
```
minikube start
```

# Minikube Setup on Linux
These instructions should be valid for Debian, Ubuntu, or Mint Linux distributions. Your experience may vary if using other distributions such as RHEL, Arch, non-desktop distributions like Ubuntu server, or lightweight distros which may omit many expected tools.
## Install Minikube

In your terminal run the following:
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

#### Starting Minikube and Testing Installation


After you have successfully installed Minikube we need to start and test the cluster to make sure everything is working correctly.
1. Add your user to the docker group
Note - If this step was performed when Docker was installed, it can be skipped.
In your terminal, run:
```
sudo usermod -aG docker $USER && newgrp docker
```
Log out of the user profile and log back in so these changes take effect. If running inside a VM, you will need to restart the entire machine, not just log out.
2. Start with the default driver:
In your terminal, run:
```
minikube start
```
Your output should look similar to this:
![image](https://user-images.githubusercontent.com/59694469/220164433-a5b11feb-fea4-4f45-ad46-2bccdbe38402.png)


2. Check Minikube Status
After you see a Done! message in your terminal, run minikube status to make sure the cluster is healthy. Pay particular attention that the **apiserver** is in a "**Running**" state. 

![image](https://user-images.githubusercontent.com/59694469/220164376-94a5a06f-5cc4-4470-92bc-be6121a4b002.png)

3. Install kubectl
In your terminal run the following:
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
4. Test kubectl
Lastly, open up your terminal and make sure that you can run ```kubectl version```
![image](https://user-images.githubusercontent.com/59694469/220164324-012a3785-35b5-4efc-89a4-7e9980dd966b.png)

Note - the client and server can be off by one minor version without error or issue.

### Work fLow daigram 
* 1
![image](https://user-images.githubusercontent.com/59694469/220164243-83d03b68-2cb1-4ae7-903a-4ea1dde9c54e.png)

* 2
![image](https://user-images.githubusercontent.com/59694469/220165499-00df0e35-0fdb-495a-8ee0-441c74b15243.png)

### Master 
When we run **kubectl** command to run config files are running k8s clustor handle by mater.

### Kube-apiserver 
kube-apiserver is 100% responsible for monitoring current status of all the different node inside the clustor and make sure every thing doing current thing.


![image](https://user-images.githubusercontent.com/59694469/220165639-4c034414-764d-43c1-a5b6-71cf9013a7e1.png)


* in config file we define object type using **kind** eg: ```kind: Service``` or ```kind: Pod```. line 2 in client-node-port.yaml 
* line no 7 to line no 10 in client-node-port.yaml  port defination

# Config files example

#### file 1 : client-pod.yml

```
apiVersion: v1
kind: Pod
metadata:
  name: client-pod
  labels:
    component: web         <!-- key and value which used in client-node-port.yml (kind: Service) file  -->
spec:
  containers:
    - name: client                          <!-- name of container -->
      image: abhijeetjha1995/multi-client   <!-- Image of docker HUb -->
      ports:
        - containerPort: 3000               <!-- Container running on port -->

```
#### file 2 : client-node-port.yml

```
apiVersion: v1
kind: Service
metadata:
  name: client-node-port
spec:
  type: NodePort
  ports:
    - port: 3050            <!-- K8s containers use it to intract each other -->
      targetPort: 3000      <!-- Port where our app is running -->
      nodePort: 31515       <!-- Port use to open the project in browser -->
  selector:
    component: web          <!-- labels key value of client-node-port.yml  -->
```

### Running  container

```
kubectl apply -f <filename>
```

* kubectl : CLI we use to change/run our cluter
* apply : - change the current configuration of cluster
* -f : we want to specify afile that hasthe cofig changes
* <filename> : path of config file
 
 Eg: 
 ![image](https://user-images.githubusercontent.com/59694469/220335206-f004fa4d-8a89-44e0-9b70-233860f90047.png)

 
 ### Print the status of running pods
 ```
 kubectl get pods
 ```
 Eg:
 ![image](https://user-images.githubusercontent.com/59694469/220335352-e504710d-8ec9-44da-aa30-1d5e15d34362.png)

 
 ### Print the status of running services
 ```
 kubectl get services
 ```
 Eg:
 ![image](https://user-images.githubusercontent.com/59694469/220335446-0a49cd46-1806-40af-93cb-888e2b2111d1.png)


 ### Get the k8s local machine running ip
 
 ```
 minikube ip
 ```

### Delete service
```
  kubectl delete service <service-Name>
```

### Delete pod
```
  kubectl delete pod <pod-Name>
```

### Delete pod or services using config file
```
  kubectl delete -f <fileName.yaml>
```
eg:
```
  kubectl delete -f client-pod.yaml
```

### Print the status of running deployments
```
  kubectl get deployments
```

### Get Detailed info about Pod
```
  kubectl get pods -o wide
```

### description about a pod ya all the pod

```
  kubectl describe pods


  <!-- for a single pod  -->
  kubectl describe pods <pod-name>
```


## Imperative command to update the image 

We need this command to update runing k8s pod image. Whenever we push new version on image to docker hub then we need
to inform k8s that image updated with the latest version then pods get pull of latest version of pod and running that 
so user can see new changes of that image.

```
  kubectl set image <object_type>/<object_name> <container_name>=<new image to use>
```
* <object_type>     : Type of object. eg: deployment
* <object_name>     : Name of the object eg.: client-deployment (reference of client-deployment.yaml) 
* <container_name>  : Name of the container which we are updating  (get this from config file)
* <new image to use>: Full name of image to use with tag

eg: 
```
  kubectl set image deployment/client-deployment client=abhijeetjha1995/multi-client:v5
```

### Access the docker service running images in k8s virtual node
```
  eval $(minikube docker-env)
```


# Multi Conatiner Deploy

![image](https://user-images.githubusercontent.com/59694469/226537480-a6b1465f-62be-4b26-a204-b71ee46cb39c.png)


### Here we need to create 2 config file for each deployment. File created followed by service name with 1st for deployment.yaml and 2nd  cluster-ip-service.yaml

eg. 

 1. client-deployment.yaml
 2. client-cluster-ip-service.yaml

*   **client-deployment.yaml** used for created a pod and development.
*   **client-cluster-ip-service.yaml** used for make client pod accesable to other service like Ingress Service then it can be access by user/traffic 

eg: 
client-deployment.yaml
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: client-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      component: web
  template:
    metadata:
      labels:
        component: web
    spec:
      containers:
        - name: client
          image: abhijeetjha1995/multi-client
          ports:
            - containerPort: 3000
            env:  <!-- here we define env >

```

client-cluster-ip-service.yaml
```
apiVersion: v1
kind: Service
metadata:
  name: client-cluster-ip-service
spec:
  type: ClusterIP
  selector:
    component: web
  ports:
    - port: 3000
      targetPort: 3000
```


#### To run all config (.yaml) file from the folder in single command

```
  kubectl apply -f k8
```

## Volume

![image](https://user-images.githubusercontent.com/59694469/226650216-03996084-0f74-43f3-942a-d1b715c6de77.png)


#### When we are storing data in database container (like: Postgres ) data stored in that particluar conatiner only if container crashed and re-create new one then all sotred data will delete and new container created with new clean database container. To avoid such type of issue we use volume of database.
 
* Persistent Volume Claim :  Here we can say it is the way to store the data on host machine if db container will crashed and new container is created then data is safe because data is in not stored in that particular container data stored in out side of container on host machine. 
 

![image](https://user-images.githubusercontent.com/59694469/226652472-518119e0-af4a-4052-a299-e1793649f081.png)


![image](https://user-images.githubusercontent.com/59694469/226650349-de555bcb-1130-4a22-8b28-02b7b5087d65.png)


![image](https://user-images.githubusercontent.com/59694469/226652338-3d3ddf6c-729a-4d68-ab58-792a9d0ee8cf.png)

![image](https://user-images.githubusercontent.com/59694469/226652393-e38e168a-13d3-4e3d-b04a-957747ae9e93.png)


![image](https://user-images.githubusercontent.com/59694469/226652594-9e1f53b2-e7da-406d-b59b-80bae8aab4f2.png)

 ### commands
 * Get Persistent Volume 
 ```
  kubectl get pv
 ```
 
 * Get Persistent Volume Claim
 ```
  kubectl get pvc
 ```
 
 ### Expamle of Persistent Volume Claim config file *database-persistent-volume-claim.yaml*
 
 ```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: database-persistent-volume-claim
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 2Gi <!-- Size of reserved memory --> 

 ```
 
 * accessModes types :
 
 ![image](https://user-images.githubusercontent.com/59694469/226830553-a296a431-de19-4ca7-a79b-225c75693526.png)

 
 ### Storage Class Name
  A StorageClass provides a way for administrators to describe the "classes" of storage they offer. Different classes might map to quality-of-service levels, or to backup policies, or to arbitrary policies determined by the cluster administrators. Kubernetes itself is unopinionated about what classes represent.
 
 * In this project i don't define storageClassName then PVC create default storageClassName.

 * storageClassName is different for different machine host here is the url where we can find out storageClassName for different cloud platform : https://kubernetes.io/docs/concepts/storage/storage-classes

* *commands*
  * Get list of Storage Class

  ```
    kubectl get storageclass
  ```
  * Get Details about Storage Class

  ```
    kubectl describe storageclass 
  ```

 ## Creating a Secret
 
 * The way to store confidential data (like Username and password)
 
 ![image](https://user-images.githubusercontent.com/59694469/226655138-b4fe7259-5ee3-4073-a23f-893729ec793a.png)
 
 eg: 
 ```
  kubectl create secret generic password --from-literal PGPASSWORD=password123
 ```
 
 How Secret password is used in postgres-deployment.yaml : line no : 29 to 33 
 ```
             env:
            - name: POSTGRES_PASSWORD
              valueFrom:
                secretKeyRef:
                  name: pgpassword
                  key: PGPASSWORD
 ```

# Handling trafic with ingress controllers 

## Optional Reading on Ingress Nginx
Just in case you wanted to understand ingress-nginx a bit better, check out this article by Hongli Lai - https://www.joyfulbikeshedding.com/blog/2018-03-26-studying-the-kubernetes-ingress-system.html.  Hongli is an absolute genius, he co-created Phusion Passenger, an extremely popular webserver that integrates with Nginx.

## Docker Driver and Ingress - IMPORTANT
We've noticed many macOS and Windows students attempting to take the course with the docker driver when using Minikube instead of Docker Desktop.

The docker driver is not supported for use in this course if you are on macOS or Windows. It currently does not work with any type of ingress:

https://minikube.sigs.k8s.io/docs/drivers/docker/#known-issues

If you have started the course with the docker driver, you will need to switch to a different driver in order to continue.

Delete your cluster:
```
minikube delete
```
Restart with a different driver:

macOS:
```
minikube start --driver=hyperkit
```
or
```
minikube start --driver=virtualbox
```
Windows:

Windows students should be using Docker Desktop with WSL2 and not Minikube. A VM driver will not work since it would require virtualization that is in conflict with WSL2. You should stop and head back to the instructions to enable Docker Desktop's Kubernetes instead.

Linux:

If you are a Linux user, the ingress add-on should be supported when using the docker driver.


## Ingress Nginx Installation Info
In the upcoming lecture, we will be installing Ingress Nginx. In the video, it is shown that there is a required mandatory command that needed to be run for all providers. This has since been removed, so, the provider-specific commands (Docker Desktop, Minikube, etc) are all that are required. Please triple-check that you are installing Ingress Nginx(https://kubernetes.github.io/ingress-nginx/) and not Nginx Ingress(https://docs.nginx.com/nginx-ingress-controller/), which is a totally different and incompatible library.

### Installation - Docker Desktop (macOS and Windows)

![image](https://user-images.githubusercontent.com/59694469/227201039-427856b0-a882-46bf-a12b-004df3307403.png)


https://kubernetes.github.io/ingress-nginx/deploy/#quick-start

Installation - Minikube

https://kubernetes.github.io/ingress-nginx/deploy/#minikube
