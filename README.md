# SOC Intelligent Triage — V2.7.3

Protótipo acadêmico de triagem e priorização de alertas de cibersegurança. A aplicação organiza eventos, calcula um score explicável de risco (1–10), apresenta uma fila priorizada e recomenda playbooks para apoiar a decisão do analista.

## Download do aplicativo

**[Baixar SOCIT V2.7.3 revisado (ZIP)](./SOCIT-V2.7.3-REVISADO%20%281%29.zip)**

O pacote completo está anexado ao repositório. Para executar, baixe o ZIP, extraia todos os arquivos e siga as instruções deste pacote no `README.md` interno. Não execute o sistema em redes ou ambientes reais sem autorização e validação técnica.

## Principais módulos

- Dashboard web, fila e detalhes de incidentes.
- API/backend com autenticação e controle por papéis.
- Motor de risco com pontuação de 1 a 10 e fatores explicáveis.
- Persistência local SQLite e configuração para PostgreSQL.
- Integração preparada para Wazuh via webhook autenticado.
- Playbooks orientativos, atualização de status e exportação de relatórios.

## Revisão da V2.7.3

- 16/16 testes automatizados executados passaram.
- Verificação de sintaxe Python (`compileall`) passou.
- Verificação de sintaxe JavaScript (`node --check`) passou.
- Varredura do pacote não encontrou `.env` real, banco local, chave privada ou token de provedor conhecido.
- README do pacote, dependências de teste e `.gitignore` foram ajustados.

Veja [`AUDIT_REPORT_V2.7.3_VALIDATION.md`](./AUDIT_REPORT_V2.7.3_VALIDATION.md) para a lista dos testes e limitações.

## Limitações de validação

Os testes foram executados localmente com Python 3.13.5 e SQLite. Ainda precisam de validação no ambiente de destino: Windows ponta a ponta, Docker/PostgreSQL, conexão com uma instalação real do Wazuh, TLS/proxy, backup/restore e controles operacionais. O protótipo não é uma plataforma homologada nem deve ser conectado a ambientes reais sem autorização.
