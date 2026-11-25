# Revisão de entrega — SOC Intelligent Triage V2.7.3

**Data:** 25 de novembro de 2026  
**Escopo:** inspeção do pacote, compilação Python, validação de scripts e testes automatizados locais.

## Resultado

- **16 de 16 testes automatizados executados passaram.**
- `python -m compileall -q backend integrations`: passou.
- `node --check` nos arquivos JavaScript do frontend: passou.
- `ast.parse` no integrador customizado do Wazuh: passou.
- A varredura não encontrou arquivo `.env` real, banco de dados local, chave privada ou token de provedor conhecido. Os arquivos de exemplo contêm apenas marcadores de configuração.

## Testes executados

1. `pilot_config_test.py`
2. `replay_idempotency_test.py`
3. `login_throttle_persistence_test.py`
4. `self_test.py`
5. `full_audit_test.py`
6. `migration_test.py`
7. `wazuh_test.py`
8. `wazuh_bridge_test.py`
9. `wazuh_bridge_retry_test.py`
10. `v27_test.py`
11. `v27_http_test.py`
12. `v27_regression_test.py`
13. `v27_security_test.py`
14. `deep_audit_test.py`
15. `v271_deep_audit_test.py`
16. `v273_scope_test.py`

## Ajustes feitos no pacote revisado

- README ajustado para descrever o projeto como protótipo acadêmico para demonstração controlada, sem alegar homologação ou prontidão produtiva.
- Lista de testes atualizada para incluir `v273_scope_test.py`.
- Adicionado `backend/requirements-dev.txt` com `httpx==0.28.1`, dependência usada pelos testes HTTP com FastAPI TestClient.
- `.gitignore` ampliado para ignorar bancos locais, caches, logs e artefatos de build.
- Caches Python removidos do pacote.

## Limitações que permanecem

- A bateria foi executada localmente em CPython 3.13.5, com SQLite e cliente HTTP de teste; não foi uma validação completa em Windows.
- Não foi possível comprovar a execução de uma stack Docker/PostgreSQL nem a conexão com uma instalação real do Wazuh neste ambiente.
- O `psycopg` exigido pelo modo PostgreSQL está declarado em `backend/requirements.txt`, mas não estava instalado no ambiente de revisão.
- Integração Wazuh, TLS, proxy confiável, backup/restore, gestão de segredos e controles organizacionais precisam de validação no ambiente de destino antes de uso real.

**Conclusão:** o pacote está coerente para demonstração local com dados sintéticos e passou nos testes incluídos. Isso não representa certificação de segurança, homologação ou autorização para uso em produção.
