# Deployment menggunakan kubernetes

login dulu ke cluster kubernetes, dengan cara download kubeconfig sesuai provider kubernetes yang digunakan.



clone repo
```sh
git clone https://github.com/febriyanadji/test-spe.git
cd test-spe
```

masuk ke folder yaml kubernetes, lalu apply manifest
```
cd ./soal7
kubectl apply -f .
```

pastikan semua komponen berjalan dengan baik :
```sh
kubectl get pods -n default
kubectl get services -n default
kubectl get ingress -n default
```