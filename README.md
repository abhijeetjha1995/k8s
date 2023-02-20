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

