Para usar este repositório, clone-o em seu host Docker, navegue até o diretório "prometheus-windows-exporter" e execute o comando "docker-compose up -d".

```
git clone https://github.com/luiscruzcwb/prometheus-windows-exporter
```
Navegue até a pasta _**prometheus-windows-exporter**_
```
cd /prometheus-windows-exporter
```
Execute o arquivo **_docker-compose_** (se necessário faça ajustes, conforme sua necessidade).
```
docker-compose up -d
```
## Downloading Windows Exporter e Instalação

Para baixar o Prometheus Windows Exporter, acesse a página do [GitHub](https://github.com/prometheus-community/windows_exporter) da comunidade.

Faça o download da versão mais recente (v0.22.0 no momento) do Windows Exporter na seção "Releases".

Se você estiver usando uma **versão de 32 bits** do sistema operacional Windows, clique no link **_windows_exporter-*-386.msi._**

Se você estiver usando uma **versão de 64 bits** do sistema operacional Windows, clique no link **_windows_exporter-*-amd64.msi._**

## Instalando o Windows Exporter

O Prometheus Windows Exporter possui vários coletores, cada um responsável por exportar informações específicas. Alguns coletores estarão desativados por padrão, para obter uma lista dos coletores compatíveis, ativos e desativados, visite a seção "Collectors" na página do [GitHub](https://github.com/prometheus-community/windows_exporter). 

Após o download, em seu Windows OS, navegue executando o terminal como administrador até a pasta que se encontra o arquivo, e execute o seguinte comando:
```
msiexec /i ./windows_exporter-0.22.0-amd64.msi
```
O Windows Exporter estará em execução na porta 9182 do seu computador com Windows, para verificar abra o navegador e acesse o endereço: http://localhost:9182/metrics. 

Se você visualizar a saída abaixo, significa que o Windows Exporter está em funcionamento.
		
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fe38rp9464cmi1mvm5zw.png)

## Configurando o Windows Exporter no Prometheus

Navegue até a pasta _**prometheus**_ e dite o arquivo 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk3MTQ1OTIxLDExMzQ0NDIyMzcsMTI3OT
EwMjQ2Ml19
-->