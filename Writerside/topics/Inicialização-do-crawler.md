# Inicialização do crawler

![banner_crawler_spring_1.png](banner_crawler_spring_1.png)

Ao inicializar o crawler, você terá a seguinte ação:

- O shell do crawler aparecerá e você poderá iteragir com o sistema.

![console_init_crawler_1.png](console_init_crawler_1.png)

```
start                     - Show the main menu
menu                      - Show the main menu
archive-logs              - Backup and compact log
cw menu                   - Show the main menu
cw list cache-url         - List the size of the cache URL
cw list url               - List all URLs
cw list proxy             - List all proxies
cw list user-agent        - List all user agents
cw config key=value       - Update configuration key with the given value
cw config show            - Show the configuration settings
cw url:url                - Access the directory corresponding to the given URL
cw url:url show           - Show the contents of the URL directory
cw notifications          - Show all notifications
cw audit                  - Show system audit information
cw search:<keyword>       - Search URLs containing the given keyword
cw help or cw -help       - Show this help message
cw exit                   - Exit the application
```

## Configuração do crawler

O arquivo de configuração (_"config"_) do crawler é um arquivo **TXT** que contém as configurações do comportamento do crawler quando ele for ativado.

- **URL**: URL do site que será coletado
- **Proxy**: Proxy que será utilizado para coletar os dados
- **User-Agent**: User-Agent que será utilizado para coletar os dados
- **Cache**: Cache que será utilizado para armazenar os dados coletados
- **Output**: Output que será utilizado para armazenar os dados coletados
- **Log**: Log que será utilizado para armazenar os logs do sistema