<h1 align="center">Novo SGA Kubernetes Helm Charts </h1>

#### 1 - Criar um repositorio onde ficarão armazenados os Charts

#### 2 - Criar os pacotes com a devida versão.

Ex: `helm package novosga --destination ./packages --version 0.1.1`

#### 3 - Copiar o pacote para raiz do repositorio dos charts

`cp ./packages/novosga-0.1.1.tgz ../my-helm-charts`

#### 4 - Criar o arquivo robots.txt

`echo -e “User-Agent: *\nDisallow: /” > robots.txt`

Este arquivo irá evitar bot crawling no repositorio.

#### 5 - Criar arquivo index.yaml

O arquivo index.yaml contem metadata sobre os pacote, O comando `helm repo index` deve ser executado no mesmo diretorio onde os pacotes estão localizados.

` helm repo index . --url https://marcusjava.github.io/helm-charts-repo/`

Exemplo de um arquivo index.yaml

```markdown
    apiVersion: v1
    entries:
    alpine: - created: 2016-10-06T16:23:20.499814565-06:00
    description: Deploy a basic Alpine Linux pod
    digest: 99c76e403d752c84ead610644d4b1c2f2b453a74b921f422b9dcb8a7c8b559cd
    home: https://helm.sh/helm
    name: alpine
    sources: - https://github.com/helm/helm
    urls: - https://technosophos.github.io/tscharts/alpine-0.2.0.tgz
    version: 0.2.0 - created: 2016-10-06T16:23:20.499543808-06:00
    description: Deploy a basic Alpine Linux pod
    digest: 515c58e5f79d8b2913a10cb400ebb6fa9c77fe813287afbacf1a0b897cd78727
    home: https://helm.sh/helm
    name: alpine
    sources: - https://github.com/helm/helm
    urls: - https://technosophos.github.io/tscharts/alpine-0.1.0.tgz
    version: 0.1.0
    nginx: - created: 2016-10-06T16:23:20.499543808-06:00
    description: Create a basic nginx HTTP server
    digest: aaff4545f79d8b2913a10cb400ebb6fa9c77fe813287afbacf1a0b897cdffffff
    home: https://helm.sh/helm
    name: nginx
    sources: - https://github.com/helm/charts
    urls: - https://technosophos.github.io/tscharts/nginx-1.1.0.tgz
    version: 1.1.0
    generated: 2016-10-06T16:23:20.499029981-06:00
```

Estrutura final do repositorio:

```markdown
├── index.yaml
├── novosga-0.1.1.tgz
├── novosga-0.1.2.tgz
├── README.md
└── robotos.txt
```

## Autor

👤 **Marcus Vinicius**

- Github: [marcusjava](https://github.com/marcusjava)
