# K8S Challenges
This is a repo based on the K8s challenges offered in the course [CKAD with Tests](https://www.udemy.com/course/certified-kubernetes-application-developer)

## Challenge 1
This is found in **challenge-1** folder and captures the following:
- Namespace creation: avaialble in the **ns-development.yaml**
- Role creation: available in the **dev-role.yaml**
- Role Binding: available in the **dev-binding.yaml**
- Persistent Volume: available in the **pv.yaml**
- Persistent Volume Claim: available in the **pvc.yaml**
- Pod with links to the persistent volume: available in the **pod.yaml**
- A NodePort Service: available in the **svc.yaml**

## Challenge 2

- Change the controlplane port from **6433** to **6443**
- Change the certificate in **/etc/kubernetes/manifests/kube-apiserver.yaml** to **ca.crt** where you see **ca-authority.crt**
- Restart the kubelet
  ```sh
  systemctl restart kubectl
  ```
- Update the coredns image
- Update the **node01** to accept scheduling
  ```sh
  k uncordon node01
  ```

Apply the manifests in the **challenge-2** folder
```sh
k create -f data-pv.yaml
k create -f data-pvc.yaml
k create -f pod-file-server.yaml
k create -f svc.yaml
```