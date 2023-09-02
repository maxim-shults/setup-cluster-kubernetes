setup kubernetes with kubeadm \
download the repository and run on all nodes \
git clone https://github.com/maxim-shults/setup-cluster-kubernetes.git \
navigate to folder where you cloned and change access permissions in teminal \
chmod +x install_k8s.sh and run ./install_k8s.sh \
on masternode run \
kubeadm init --pod-network-cidr=10.244.0.0/16 --apiserver-adverstise-address= IP OF THE MASTER NODE
