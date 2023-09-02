setup kubernetes with kubeadm \
download the repository and run on all nodes \
git clone https://github.com/maxim-shults/setup-cluster-kubernetes.git \
navigate to folder where you cloned and change access permissions in teminal \
chmod +x install_k8s.sh and run ./install_k8s.sh \
only on masternode run \
kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-adverstise-address= IP OF THE MASTER NODE
if everything is ok you should see Your Kubernetes control-plane has initialized successfully!\
follow the orders \
setup network addon \
kubectl apply -f https://github.com/weaveworks/weave/releases/download/v2.8.1/weave-daemonset-k8s.yaml
last thing edit DaemonSet \
kubectl edit ds weave-net -n kube-system \
add in containers /


       - command:
        - /home/weave/launch.sh
        env:
        - name: IPALLOC_RANGE
          value: 10.244.0.0/16
