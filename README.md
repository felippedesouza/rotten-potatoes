# rotten-potatoes

## Como usar?

> Base de dados usado: https://github.com/KubeDev/rotten-potatoes

1. vá ate a pasta do app `cd rotten-potatoes/`
1. crie um cluster kubernetes: `kind create cluster --name meucluster --config cluster.yaml`
1. vá ate a pasta do k8s `cd k8s/` e rode:
   1. `kubectl apply -f deployment.yaml`
1. abra o navegador cole a url `localhost:8080`
