# SOC Intelligent Triage — V2.7.3

Protótipo acadêmico de triagem e priorização de alertas de cibersegurança. A aplicação organiza eventos, calcula e apresenta pontuações de risco, prioriza uma fila de incidentes e recomenda playbooks para apoiar a análise.

## Demonstração no GitHub Pages

A versão estática de demonstração fica na pasta [docs](./docs/). Depois de ativar o GitHub Pages nas configurações do repositório, o endereço público será:

**https://isacneves11.github.io/Socit/**

Para habilitar: **Settings → Pages → Build and deployment → Deploy from a branch → Branch: main → Folder: /docs → Save**.

> **Limites da demonstração:** o Pages executa apenas o frontend estático. Os alertas são dados sintéticos; simulações e alterações de status ficam no armazenamento local do navegador. Esta demonstração não se conecta ao backend Python, PostgreSQL ou Wazuh e não recebe eventos reais.

## Aplicativo completo

[Baixar o pacote SOCIT V2.7.3 revisado (ZIP)](./SOCIT-V2.7.3-REVISADO%20%281%29.zip)

O pacote completo contém frontend, backend, testes, integração preparada para Wazuh e arquivos de implantação local/Docker. Para executar o sistema integrado, extraia o ZIP e siga o README interno.

## Principais módulos

- Dashboard e fila priorizada de incidentes.
- Detalhes, evidências e playbooks orientativos.
- Motor de risco e classificação por severidade.
- Backend com autenticação e controle por papéis.
- Persistência local SQLite e configuração para PostgreSQL.
- Integração preparada para Wazuh via webhook autenticado.

## Revisão da V2.7.3

- 16/16 testes automatizados executados passaram.
- Verificação de sintaxe Python (compileall) passou.
- Verificação de sintaxe JavaScript (node --check) passou.
- Varredura do pacote não encontrou .env real, banco local, chave privada ou token de provedor conhecido.

Veja [AUDIT_REPORT_V2.7.3_VALIDATION.md](./AUDIT_REPORT_V2.7.3_VALIDATION.md) para a lista de testes e limitações.

## Limitações de validação

Os testes foram executados localmente com Python 3.13.5 e SQLite. Ainda precisam de validação no ambiente de destino: Docker/PostgreSQL, conexão com uma instalação real do Wazuh, TLS/proxy, backup/restore e controles operacionais. O protótipo não é uma plataforma homologada nem deve ser conectado a ambientes reais sem autorização.
