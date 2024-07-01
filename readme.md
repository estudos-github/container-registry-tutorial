# Container Registry

### Efetuar autenticação no Container Registry
```bash
export CR_PAT=YOUR_TOKEN
echo $CR_PAT | docker login ghcr.io -u YOUR_USERNAME --password-stdin
```
>Atenção: Personal access token (classic) deve conter as permissões: `read:packages`, `write:packages` e `delete:packages`.

## Publicar uma imagem  

1) Construir a imagem localmente
   
```bash
build -t IMAGE_NAME:latest .
```
2) Fazer push da imagem. Isso cria um pacote na organização
```bash
docker push ghcr.io/NAMESPACE/IMAGE_NAME:latest
```
3) Associar o pacote criado à um repositório da organização.

## Utilizar uma imagem 
 
1) Fazer pull da imagem.  
```bash
docker pull ghcr.io/NAMESPACE/IMAGE_NAME:latest
```
