# Template: Integração VS Code/Cursor com N8N via MCP

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![N8N](https://img.shields.io/badge/n8n-v1.50.0+-orange)](https://n8n.io/)
[![VS Code](https://img.shields.io/badge/VS%20Code-1.85+-blue)](https://code.visualstudio.com/)

Template pronto para uso que permite conectar o **VS Code** ou **Cursor** à sua instância **N8N** usando o **MCP Server** (Model Context Protocol). Com esta configuração, você pode criar, editar e gerenciar workflows diretamente da sua IDE, aproveitando assistentes de IA como o Claude.

**Artigo completo:** [Integre o VS Code ou Cursor com o N8N](https://guifav.dev/blog/integrar-vscode-cursor-n8n-automacao-workflows/)

---

## Benefícios

- **Versionamento com Git** — Histórico completo de alterações nos workflows
- **Redundância** — Workflows salvos na instância e no repositório local
- **Controle** — Revise alterações antes de aplicá-las
- **Compartilhamento** — Exporte e compartilhe workflows com sua equipe
- **Produtividade com IA** — Crie workflows complexos usando linguagem natural

---

## Pré-requisitos

| Ferramenta | Versão Mínima | Observações |
|------------|---------------|-------------|
| VS Code ou Cursor | 1.85+ | Cursor é um fork do VS Code focado em IA |
| Extensão Claude Code | Mais recente | Disponível na marketplace do VS Code |
| Instância N8N | 1.50.0+ | Self-hosted ou cloud, com suporte a MCP |
| Git | Qualquer versão | Para versionamento dos workflows |

---

## Instalação

### 1. Clone este repositório

```bash
git clone https://github.com/guifav/n8n-vscode-template.git
cd n8n-vscode-template
```

### 2. Configure as variáveis de ambiente

Copie o arquivo de exemplo e edite com suas credenciais:

```bash
cp .env.example .env
```

Edite o arquivo `.env` com seus tokens:

```bash
# Token de API para chamadas REST diretas ao n8n
N8N_API_KEY=seu_token_api_aqui

# URL do MCP Server
SERVER_URL=https://sua-instancia.com/mcp-server/http

# Token de acesso MCP
ACCESS_TOKEN=seu_token_mcp_aqui
```

### 3. Configure o MCP Server

Edite o arquivo `meu-projeto-n8n/.vscode/mcp.json` com a URL e token da sua instância:

```json
{
  "mcpServers": {
    "n8n-mcp": {
      "type": "http",
      "url": "https://sua-instancia.com/mcp-server/http",
      "headers": {
        "Authorization": "Bearer seu_token_mcp_aqui"
      },
      "description": "n8n MCP Server for workflow automation"
    }
  }
}
```

### 4. Abra o projeto no VS Code

```bash
code meu-projeto-n8n
```

### 5. Reinicie o VS Code

Feche e reabra o VS Code para carregar as configurações do MCP.

---

## Estrutura do Projeto

```
.
├── .env.example                    # Exemplo de variáveis de ambiente
├── .gitignore                      # Arquivos ignorados pelo Git
├── LICENSE                         # Licença MIT
├── README.md                       # Este arquivo
└── meu-projeto-n8n/
    ├── .claude/
    │   └── instructions.md         # Instruções para assistentes de IA
    ├── .vscode/
    │   └── mcp.json                # Configuração do MCP Server
    └── workflows/
        └── .gitkeep                # Pasta para armazenar workflows exportados
```

### Descrição dos arquivos

| Arquivo | Descrição |
|---------|-----------|
| `.env.example` | Template para variáveis de ambiente (copie para `.env`) |
| `.gitignore` | Protege credenciais e arquivos sensíveis |
| `mcp.json` | Configuração de conexão com o MCP Server do N8N |
| `instructions.md` | Contexto e boas práticas para assistentes de IA |
| `workflows/` | Armazene seus workflows exportados em JSON |

---

## Gerando os Tokens

Você precisará de **dois tokens** da sua instância N8N:

### Token MCP (Access Token)

1. Acesse **Settings > Instance-level MCP** na sua instância N8N
2. Ative o toggle **"Enable MCP access"**
3. Clique em **"Create Access Token"**
4. Copie o token gerado

### Token API (N8N_API_KEY)

1. Acesse **Settings > API** na sua instância N8N
2. Clique em **"Create API Key"**
3. Selecione **Full Access**
4. Copie o token gerado

> **Importante:** Os tokens são exibidos apenas uma vez. Salve-os em local seguro.

---

## Exemplos de Uso

Após configurar, use o Claude Code (ou outro assistente) para gerenciar workflows:

### Listar workflows

```
Liste todos os workflows ativos na minha instância n8n
```

### Criar workflow

```
Crie um workflow que:
1. Receba dados via webhook HTTP
2. Adicione um timestamp automático
3. Salve em uma planilha Google Sheets
```

### Editar workflow existente

```
Encontre o workflow "Processamento de Leads" e adicione 
tratamento de erros com notificação no Slack
```

### Exportar workflow

```
Exporte o workflow "Automação de Emails" para a pasta workflows/
```

---

## Segurança

- O arquivo `.env` está no `.gitignore` e **nunca será versionado**
- Use tokens dedicados para cada projeto
- Rotacione tokens periodicamente (a cada 3-6 meses)
- Revogue tokens comprometidos imediatamente

---

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas alterações (`git commit -m 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abrir um Pull Request

---

## Recursos

- [Artigo completo com tutorial detalhado](https://guifav.dev/blog/integrar-vscode-cursor-n8n-automacao-workflows/)
- [Documentação oficial do N8N MCP](https://docs.n8n.io/advanced-ai/accessing-n8n-mcp-server/)
- [N8N Public API](https://docs.n8n.io/api/api-reference/)
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/)

---

## Licença

Este projeto está licenciado sob a **MIT License** - veja o arquivo [LICENSE](LICENSE) para detalhes.

---

## Autor

**Guilherme Favaron**

- Site: [guifav.dev](https://guifav.dev/)
- LinkedIn: [/in/guilhermefavaron](https://www.linkedin.com/in/guilhermefavaron)

---

<p align="center">
  Feito com ☕ e 🤖 por <a href="https://guifav.dev/">Guilherme Favaron</a>
</p>
