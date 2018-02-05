# Useful commands & links

Examples of ingress resource specification:
https://kubernetes.io/docs/concepts/services-networking/ingress/#simple-fanout

```
kubectl get ingress
kubectl describe ingress <INGRESS_NAME>
```

# Instructions


## Create and ingress
1. Make sure to start the ingress addons
```
minikube addons enable ingress
```
2. Update your hosts file by add minikube.info pointing to your minikube IP
	* Get minikube IP
	```
    minikube ip
    ```
    * Add the following to the end of your hosts file
    ```
    <minikube_ip> minikube.info
    ```
    > __Hosts file location:__
    > 
    > __Windows:__ C:\Windows\System32\drivers\etc 
    > 
    > (Follow this instructions https://support.microsoft.com/en-us/help/923947/you-cannot-modify-the-hosts-file-or-the-lmhosts-file-in-windows-vista)
    > 
    > __Linux / macOS:__ /etc/hosts


3. Create an ingress resource to redirect http://minikube.info traffic to your WordPress application



## I'm feeling lucky
1. Create 2 Deployments of NGINX web server
2. Make the index.html to be represented as configmap
>Use configmap yaml files from the solution directory to discover something very interesting
3. Create an ingress resource to access the applications by reverse proxy style (http://minikube.info/webserver1 and http://minikube.info/webserver2)
