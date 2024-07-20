# Como funciona

Nesse documento vamos apresentar como é o funcionamento do crawler.

## Comunicação entre os sistemas

O Crawler Genesis se comunica com o sistema de extração de dados por meio de **<tooltip term="Nostr">Nostr</tooltip>**.
Além disso, o crawler também faz uso do **<tooltip term="IPFS">IPFS</tooltip>** para armazenar os páginas coletadas e disponibilizar o acesso ao **Extractor**.

![comunicacao_entre_os_sistemas.png](comunicacao_entre_os_sistemas.png){ width=550 }

## Crawler

- Extrai os HTMLs das páginas e salva em um pasta chamada _pages_.

- Os arquivos são compactados em **<tooltip term="GZIP">GZIP</tooltip>**.

- Depois de compactado o arquivo é enviado para o gateway do **<tooltip term="IPFS">IPFS</tooltip>**, o **<tooltip term="IPFS">IPFS</tooltip>** gera um hash do arquivo e então, eu envio esse hash via **<tooltip term="Nostr">Nostr</tooltip>** para o Extractor. O Extractor desconhece essa informação do hash, então preciso informar do que se trata, pela mensagem que está sendo enviada via **<tooltip term="NOSTR">Nostr</tooltip>**.


> Saiba mais sobre como é organizado as [pastas dentro da Genesis](Organização-das-pastas.md).

<note>
Pensei em enviar uma mensagem com o hash do arquivo, tipo de arquivo, qual a origem da página, no caso o host, também adicionar a data de envio.
</note>

## Extractor

O extractor fica ligado à espera de uma mensagem do relay do **<tooltip term="Nostr">Nostr</tooltip>**, quando a informação chegar, ele é instruído a fazer algo.

- Baixar o arquivo do **<tooltip term="IPFS">IPFS</tooltip>**.
- Extrair o **<tooltip term="HTML">HTML</tooltip>** para um ficheiro **<tooltip term="CSV">CSV</tooltip>**.
