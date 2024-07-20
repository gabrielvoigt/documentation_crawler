# Organização das pastas

A proposta do documento é explicar como se organiza as pastas no projeto.

## Pasta Genesis

![Crawler_genesis-Crawler_-_Folder_-_Genesis.drawio.png](Crawler_genesis-Crawler_-_Folder_-_Genesis.drawio.png)

A pasta Genesis, ela armazena todos os hosts que foram informados na configuração url da pasta config.

> Cada url, contém as pastas robots, sitemaps e pages, além de arquivo de config para aquele host.

## Robots.txt

O crawler faz o download do ficheiro **robots.txt** do site que está a ser rastreado.

> O arquivo **robots.txt** é utilizado para instruir os robôs de busca sobre quais partes do site devem ser rastreadas ou não.

## Sitemaps.txt

O arquivo sitemaps.txt é aonde a partir do robots.txt são extraídos as urls do sitemaps.
A partir do sitemap que são feitas as pesquisas para coletar as urls dos produtos.

## Config.txt

O **config.txt** da url é onde deixo as configurações de como deve ser lidas as páginas da url.

## Getpage.txt

Aqui estão todas as urls que foram contempladas para que sejam lidos pelo crawler.

## Pages

Aqui ficam armazenados os arquivos que foram coletados das páginas. São coletados HTMLs, JSONs, PDF e Images do site.

<seealso>
    <!--Provide links to related how-to guides, overviews, and tutorials.-->
</seealso>