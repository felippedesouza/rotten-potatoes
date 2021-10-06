# Rotten Potatoes

> Base de dados usado: https://github.com/KubeDev/rotten-potatoes

## Com Docker Compose

1. `cd rotten-potatoes/src`
1. `docker compose up --build` (`ctrl+c` para parar e sair do container, `docker-compose down` para remover os containers)
1. quando terminar de iniciar os containers,abra o navegador cole a url `localhost:8080`

## Com Kubernetes

### Subindo imagem pro Docker Hub

1. `docker image build -t felippedeiro/rotten-potatoes:v1 ./src`
1. `docker login`
1. `docker push felippedeiro/rotten-potatoes:v1`
1. `docker tag felippedeiro/rotten-potatoes:v1 felippedeiro/rotten-potatoes:latest`
1. `docker push felippedeiro/rotten-potatoes:latest`

### Iniciando Kubernetes

1. `cd rotten-potatoes/`
1. `kind create cluster --name meucluster --config cluster.yaml`
1. `kubectl apply -f ./k8s/deployment.yaml` (`kubectl delete -f ./k8s/deployment.yaml` para remover tudo que foi feito)
1. espere todos os objetos do kubernetes estarem funcionando (pode usar o comando `watch kubectl get all`), abra o navegador cole a url `localhost:8080`

## Com CI/CD e Digital Ocean

cp iniciativa-k8s-kubeconfig.yaml ~/.kube/config

crie um cluster na digital ocean
copie o kube config
cole na pasta .kube/config
crie um secrets no github com chave K8S_CONFIG e no valor cole o kubeconfig da digital ocean
faça um push do app pro github
rode `watch kubectl get all` e espere aparce um ip publico
quando aparecer coloque o ip publico na url do navegador e rode o site

mude o nome da pasta de `github-example` para `.github`
