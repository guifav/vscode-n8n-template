# n8n Workflow Development with Claude Code

## Contexto
Este projeto contém workflows do n8n gerenciados via MCP Server.
Use as ferramentas MCP disponíveis para criar, editar e gerenciar workflows.

## Processo de Desenvolvimento

### Fase 1: Discovery (Descoberta)
1. Use ferramentas MCP para buscar nodes relevantes para a tarefa
2. Revise as propriedades e operações disponíveis em cada node

### Fase 2: Validation (Validação)
1. Valide configurações ANTES de construir o workflow
2. Verifique campos obrigatórios e tipos de dados esperados

### Fase 3: Building (Construção)
1. Crie a estrutura do workflow com os nodes necessários
2. Conecte os nodes na ordem correta
3. Prefira nodes nativos do n8n ao invés de Code nodes quando possível

### Fase 4: Deployment (Implantação)
1. Salve o workflow na instância n8n
2. Teste a execução manualmente
3. Verifique os outputs de cada node

## Melhores Práticas
- Sempre valide a estrutura antes de construir
- Documente lógica complexa com comentários
- Nomeie workflows e nodes de forma descritiva
- Teste workflows antes de ativar em produção