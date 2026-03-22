# install kubescape
curl -s https://raw.githubusercontent.com/armosec/kubescape/master/install.sh | /bin/bash

#Adding env variables
export PATH=$PATH:/home/ubuntu/.kubescape/bin

#Run the scan using nsa framework
kubescape scan framework nsa --submit

# Troubeshoot Node NotReady
docker ps
docker exec -it telco-cluster-worker2 bash
systemctl restart kubelet

#action 
systemctl restart containerd
systemctl status containerd

#delete pods
kubectl delete pod calico-kube-controllers-d4544f494-vnjmn -n kube-system

# test
kubectl exec -n ran-services ran-client -- wget -T 5 0 - http://$TARGET_IP:80

docker exec -it telco-cluster-worker bash
