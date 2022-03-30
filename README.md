## Criando o cluster </br>

k3d cluster create meucluster --agents 2 --servers 1 -p "8080:30000@loadbalancer" </br>

## deletando um cluster </br>
k3d cluster delete meucluster </br>

# Aplicando um deploy </br>

kubectl apply -f deployments.yaml </br>

#verificando os pods </br>

kubectl get pods </br>

## verificando os services </br>

kubectl get service </br>

#verificar os logs de um pod </br>

kubectl describe pod/nome do POD  </br>