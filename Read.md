# Intalação do Docker e Docker Compose
## 01 - Primeiro vamos remover a instalação do cocker caso ele exista.

#### 01.1  - Removendo possiveis pacotes Docker que possam esta em conflito, execute o comando abaixo.

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```
#### 01.2 - Execute o comando abaixo para remover o diretorio caso ele exista: \
``/var/lib/docker``



# 02 - Adicionando repositório oficcial do docker para a instalação em um sistema operacional Ubuntu.
#### 02.1 - Add the repository to Apt sources:
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
#### 02.2 - Intalando o docker e seus agregados na ultima versão:
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

# Execute os comandos com root:
Na maquina virtual onde esta sendo executado o kong na forma de container edite o arquivo
\
``/ect/hosts`` \
\
insira uma linha com o seguinte conteudo: \
\
``127.17.0.1 host.docker.internal``

### Agora execute os seguintes comandos
``chmod +x start``\
\
``./start`` \
\
Agora o kong esta funcionando e em execução.



