# Uso do Helm

- Neste capítulo, vamos explorar como utilizar o Helm para gerenciar aplicações em um cluster Kubernetes.

- Aqui, criaremos um Chart simples que implanta uma aplicação web chamada "Giropops Senhas" (desenvolvido pela galera da LinuxTips), junto com um banco de dados Redis.

  - O repositório do Giropops Senhas pode ser encontrado em: https://github.com/badtuxx/giropops-senhas

## Estrutura do Chart
- A estrutura básica do Chart que criaremos é a seguinte:

```
uso-do-helm/
├── chart/
│   ├── Chart.yaml
│   ├── values.yaml
│   └── templates/
│       ├── app-deployment.yaml
│       ├── app-service.yaml
│       ├── redis-deployment.yaml
│       └── redis-service.yaml
```
- Onde:
  - `Chart.yaml`: Contém metadados sobre o Chart.
  - `values.yaml`: Define os valores padrão que podem ser personalizados.
  - `templates/`: Contém os templates dos recursos Kubernetes que serão criados.

## Instalando o Chart
- Para instalar o Chart que criamos, você pode usar o seguinte comando:
```bash
helm install giropops-senhas ./chart
```

### Listando Releases
- Após a instalação, você pode listar as releases instaladas com:
```bash
helm list
```

## Desinstalando o Chart
- Para desinstalar a release criada, utilize o comando:
```bash
helm uninstall giropops-senhas
```

Bem simples!