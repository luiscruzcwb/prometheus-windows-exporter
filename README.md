Para usar este repositório, clone-o em seu host Docker, navegue até o diretório "prometheus-windows-exporter" e execute o comando "docker-compose up -d".

```
git clone https://github.com/luiscruzcwb/prometheus-windows-exporter
```
Navegue até a pasta _**prometheus-windows-exporter**_
```
cd /prometheus-windows-exporter
```

## Configurando o Host

Navegue até a pasta _**prometheus**_ e edite o arquivo _**prometheus.yml**_.

> O arquivo `prometheus.yml` é o arquivo de configuração principal do
> Prometheus, sendo usado para definir as configurações relacionadas ao
> comportamento do Prometheus, como os alvos de coleta de dados, regras
> de gravação e alertas.

Inclua na sessão ***## Hosts OS Windows / Windows Servers*** os seus alvos de coleta, como exemplo abaixo: 

      - job_name: 'hostname'
        scrape_interval: 10s
        static_configs:
          - targets: ['IP-Host:9182']
          
Recomendo criar uma entrada para cada Host, caso contrario, basta separa os hosts dessa forma: ***['IP-Host1:9182'],['IP-Host2:9182']***


## Downloading Windows Exporter
Para baixar o Prometheus Windows Exporter, acesse a página do [GitHub](https://github.com/prometheus-community/windows_exporter) da comunidade.

Faça o download da versão mais recente (v0.22.0 no momento) do Windows Exporter na seção "Releases".

Se você estiver usando uma **versão de 32 bits** do sistema operacional Windows, clique no link **_windows_exporter-*-386.msi._**

Se você estiver usando uma **versão de 64 bits** do sistema operacional Windows, clique no link **_windows_exporter-*-amd64.msi._**

## Instalando Windows Exporter

Após o download, em seu host windows, navegue até o local do download,  via terminal (execute como administrador), e execute o seguinte comando:
```
msiexec /i ./windows_exporter-0.22.0-amd64.msi
```
O Windows Exporter estará em execução na porta 9182 do seu host windows, para verificar abra o navegador e acesse o endereço: http://localhost:9182/metrics. 


Execute o arquivo **_docker-compose_** (se necessário faça ajustes, conforme sua necessidade).
```
docker-compose up -d
```




## Visualizando dados no Grafana

Em seu navegador, acesse o endereço: http://localhost:3000/.

    Usuário: Admin
    Senha: grafana 
    
> Esses dados de acesso podem ser alterados nas configurações do Grafana, alterando o arquivo **config.monitoring** em **/grafana/config.monitoring**  do ***docker-compose***. 

Em Home > Dashboards > ***windows_exporter for Prometheus***, os seus dados já estarão sendo apresentados. 

![enter image description here](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4st2bjk9un7peji4dd0o.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM0NTEwNjE3OCwxMTA2MDQzNTUxLC0xOD
A1NTI1NDg4LDMzNjIwMjk4MiwtMTE4OTgyOTMwMSwxNjYyMjE4
NDQzLDE1OTQ5NDEzOTMsLTIxMDMxMjc3MzgsNDIzOTI5Mjc5LC
01NzY1OTUxNiwxMTM0NDQyMjM3LDEyNzkxMDI0NjJdfQ==
-->