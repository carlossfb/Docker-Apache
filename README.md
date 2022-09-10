
## Docker - Apache

#### Criando o volume onde ficará armazenado o site

```bash
   docker volume create site
```
#### Acessando a pasta onde ficará o arquivo index

```bash
   cd /var/lib/docker/volumes/site/_data
```
#### Criando nossa página simples

```bash
   nano index.html
```
Dentro do arquivo:
```bash
   <html>
   <h1>Apache OK</h1>
   </html>
```
#### Rodando a aplicação com o docker
```bash
   docker run --name apache-A -dt -p 80:80 --mount type=volume,src=site,dst=/usr/local/apache2/htdocs/ httpd
```
