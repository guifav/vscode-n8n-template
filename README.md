# Projeto Exemplo n8n

Este repositório serve como um template para projetos n8n integrados com MCP.

## Como usar

1.  Clone este repositório.
2.  Copie o arquivo de exemplo de variáveis de ambiente:
    ```bash
    cp .env.example .env
    ```
3.  Edite o arquivo `.env` com suas credenciais.
4.  O arquivo `.vscode/mcp.json` já está configurado para usar o token definido no `.env` (se configurado via variáveis de ambiente) ou você pode precisar ajustá-lo manualmente.

## Estrutura

-   `meu-projeto-n8n/`: Diretório principal do projeto.
    -   `workflows/`: Armazene seus workflows do n8n aqui.
    -   `.claude/`: Instruções e contexto para o assistente AI.
    -   `.vscode/`: Configurações do MCP e do editor.
