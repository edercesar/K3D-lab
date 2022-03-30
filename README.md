# Instalação do K3D no Linux </br>

wget -q -O - https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash </br>

# Instalar o KUBECTL para interagir com o Cluster </br>

1 - curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" </br>
2 - curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"  </br>
3 - echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check </br>
o comando acima devera retornar o resultado : kubectl: OK </br>
4 - sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl </br>
Pronto Kubectl instalado



# Criando o cluster </br>

k3d cluster create meucluster --agents 2 --servers 1 -p "8080:30000@loadbalancer" </br>

# deletando um cluster </br>
k3d cluster delete meucluster </br>

# Aplicando um deploy </br>

kubectl apply -f deployments.yaml </br>

#verificando os pods </br>

kubectl get pods </br>

# verificando os services </br>

kubectl get service </br>

#verificar os logs de um pod </br>

kubectl describe pod/nome do POD  </br>