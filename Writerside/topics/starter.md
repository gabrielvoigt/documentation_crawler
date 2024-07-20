# Crawler Genesis

<!--Writerside adds this topic when you create a new documentation project.
You can use it as a sandbox to play with Writerside features, and remove it from the TOC when you don't need it anymore.-->

## Próposito do documento

 Este documento tem como objetivo especificar o funcionamento do Crawler Genesis, um projeto que visa a criação de um sistema de coleta de dados.

## Funcionamento

O %CRAWLER% possui duas etapas: 
- A **primeira etapa** é a coleta de dados, onde o sistema busca informações em sites de produtos e os salva em <tooltip term="HTML">HTML</tooltip>, <tooltip term="JSON">JSON</tooltip> ou <tooltip term="PDF">PDF</tooltip>.
<note>
    No futuro haverá a coleta de dados com printscreen.
</note>
- A **segunda etapa** é a análise dos dados coletados, onde o sistema verifica e extrai os dados para um arquivo CSV.

## Primeira etapa
    
A primeira etapa é a coleta de dados, onde o sistema salva as páginas dos produtos em um arquivo **<tooltip term="HTML">HTML</tooltip>** ou **<tooltip term="JSON">JSON</tooltip>** ou **<tooltip term="PDF">PDF</tooltip>**. Depois de salvar os arquivos, os ficheiros são enviados para a segunda etapa.

<img src="Crawler_genesis-Primeira Etapa.png" alt="First step" border-effect="line" title="First Step"/>

> **Veja como funciona o [Crawler](How-to-works.md)**

## Segunda etapa

A segunda etapa é a análise dos dados coletados, onde o sistema verifica e extrai os dados para um arquivo **CSV**.

<img src="Crawler_genesis-Segunda Etapa.png" alt="Second step" border-effect="line" title="Second Step"/>



> **Veja como funciona o [Extrator de dados](How-to-works.md)**

> **todo: fazer o link direto para o tópico correspodente. 
> (ancora) Adicionar topico de como baixar o projeto do git. 
> Falar sobre versionamento do projeto. 
> Modelar o esquema de pastas do projeto.
> Criar o fluxo dos dados dentro do Crawler
> Fazer diagrama em draw.io, mermaid ou d2
> Sobre o arquivo de configuração do crawler e do Extractor
> Fazer versionamento dos arquivos de configuração via git
> Fazer um tópico sobre o Teste no sistema via playwriting, selenium**
{style="warning"}

## Comunicação entre os sistemas

O Crawler Genesis se comunica com o sistema de extração de dados por meio de **<tooltip term="Nostr">Nostr</tooltip>**. 
Além disso, o crawler também faz uso do **<tooltip term="IPFS">IPFS</tooltip>** para armazenar os páginas coletadas e disponibilizar o acesso ao **Extractor**.


![comunicacao_entre_os_sistemas.png](comunicacao_entre_os_sistemas.png){ width=550 }

## Crawler
 
- Extrai os HTMLs das páginas e salva em um pasta chamada _Pages_.

- Os arquivos são compactados em **<tooltip term="GZIP">GZIP</tooltip>**.

- Depois de compactado o arquivo é enviado para o gateway do **<tooltip term="IPFS">IPFS</tooltip>**, o **<tooltip term="IPFS">IPFS</tooltip>** gera um hash do arquivo e então, eu envio esse hash via **<tooltip term="Nostr">Nostr</tooltip>** para o Extractor. O Extractor desconhece essa informação do hash, então preciso informar do que se trata, pela mensagem que está sendo enviada via **<tooltip term="NOSTR">Nostr</tooltip>**.

Pensei em enviar uma mensagem com o hash do arquivo, tipo de arquivo, qual a origem da página, no caso o host, também adicionar a data de envio.

## Extractor

O extractor fica ligado à espera de uma mensagem do relay do **<tooltip term="Nostr">Nostr</tooltip>**, quando a informação chegar, ele é instruído a fazer algo.

- Baixar o arquivo do **<tooltip term="IPFS">IPFS</tooltip>**.
- Extrair o **<tooltip term="HTML">HTML</tooltip>** para um ficheiro **<tooltip term="CSV">CSV</tooltip>**.

### Convert selection to XML
If you need to extend an element with more functions, you can convert selected content from Markdown to semantic markup.
For example, if you want to merge cells in a table, it's much easier to convert it to XML than do this in Markdown.
Position the caret anywhere in the table and press <shortcut>Alt+Enter</shortcut>:

<img src="convert_table_to_xml.png" alt="Convert table to XML" width="706" border-effect="line"/>

## Feedback and support
Please report any issues, usability improvements, or feature requests to our
<a href="https://youtrack.jetbrains.com/newIssue?project=WRS">YouTrack project</a>
(you will need to register).

You are welcome to join our
<a href="https://jb.gg/WRS_Slack">public Slack workspace</a>.
Before you do, please read our [Code of conduct](https://plugins.jetbrains.com/plugin/20158-writerside/docs/writerside-code-of-conduct.html).
We assume that you’ve read and acknowledged it before joining.

You can also always email us at [writerside@jetbrains.com](mailto:writerside@jetbrains.com).

<seealso>
    <category ref="wrs">
        <a href="https://plugins.jetbrains.com/plugin/20158-writerside/docs/markup-reference.html">Markup reference</a>
        <a href="https://plugins.jetbrains.com/plugin/20158-writerside/docs/manage-table-of-contents.html">Reorder topics in the TOC</a>
        <a href="https://plugins.jetbrains.com/plugin/20158-writerside/docs/local-build.html">Build and publish</a>
        <a href="https://plugins.jetbrains.com/plugin/20158-writerside/docs/configure-search.html">Configure Search</a>
    </category>
</seealso>