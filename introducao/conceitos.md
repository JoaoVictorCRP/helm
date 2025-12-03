# Conceitos do Helm

O Helm é uma ferramenta de gerenciamento de pacotes para Kubernetes que facilita a instalação, atualização e gerenciamento de aplicações dentro de clusters Kubernetes. Vejamos seus principais conceitos:

- **Chart**: Um Chart é um pacote pré-configurado que contém todos os recursos necessários para implantar uma aplicação no Kubernetes. Ele inclui templates de arquivos YAML, valores padrão e metadados, podemos pensar nele como um "pacote de software".

- **Release**: Uma Release é uma instância específica de um Chart implantado em um cluster Kubernetes. Cada vez que você instala um Chart, uma nova Release é criada, permitindo múltiplas implantações do mesmo Chart **com diferentes configurações**.
  - Imagine um chart de MySQL. Você pode ter várias releases desse chart, cada uma com diferentes configurações, como nomes de banco de dados ou credenciais.

- **Repository**: Um Repository é um local onde os Charts são armazenados e compartilhados. Helm permite adicionar repositórios personalizados, facilitando o acesso a Charts de diferentes fontes.

## Buscando Charts

- Para buscar Charts em repositórios públicos adicionados na sua máquina, você pode usar o comando:

```bash
helm search repo <termo-de-busca>
```

- Para buscar Charts em repositórios públicos na internet, utilize:

```bash
helm search hub <termo-de-busca>
```

## Instalando um Chart

- Para instalar um Chart, você pode usar o comando:

```bash
helm install <nome-da-release> <nome-do-chart>
```

- Um detalhe é que o Helm não espera a conclusão da instalação para retornar o prompt. Se você quiser aguardar até que todos os recursos estejam prontos, pode adicionar a flag `--wait`, ou então acompanhar o progresso usando o comando `helm status <nome-da-release>`.

## Customização do Chart

- Para verificar quais os valores configuráveis de um Chart, você pode usar:

```bash
helm show values <nome-do-chart>
```

- Com isso, você pode criar um arquivo YAML personalizado para sobrescrever os valores padrão do Chart durante a instalação:

```bash
helm install <nome-da-release> <nome-do-chart> -f meu-valores.yaml
```