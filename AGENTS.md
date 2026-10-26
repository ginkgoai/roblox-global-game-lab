# AGENTS.md — instruções permanentes para Codex

## Estado
Projeto em discovery; não criar gameplay de produção até aprovação explícita de `Gate 0` no backlog.

## Stack após Gate 0
Roblox Studio, Luau `--!strict` onde aplicável, Rojo, GitHub. Escolher bibliotecas específicas somente após auditoria de licença/segurança e versão. Não instalar dependências sem justificar e atualizar THIRD_PARTY_NOTICES.md.

## Diretrizes
- Nunca incorporar arquivos/modelos do jogo do colega sem autorização documentada.
- Cliente NÃO decide quantias monetárias, itens, dano, distância, cooldown nem resultado de compras; servidor deve ser autoridade.
- Verificar interações ProximityPrompt/RemoteEvent/ClickDetector no servidor; validar dados e aplicar rate limiting.
- Nunca conceder developer product por evento do cliente; usar MarketplaceService.ProcessReceipt server-side e concessão idempotente.
- Persistência: perfil com schema versionado; autosave, session locking, retries, tratamento de conflitos e lifecycle/erasure. Não migrar dados silenciosamente.
- Segurança: não incluir credenciais, tokens, endpoints privados, telemetria pessoal, modelos com scripts ocultos, execução remota via HTTP ou código ofuscado.
- Projeto deve ser jogável em mobile básico; testar multitouch e desempenho de efeitos.
- Interface acessível, monetização transparente e compatível com Roblox policies.

## Como trabalhar em cada issue
1. Ler docs relevantes e descrever plano pequeno.
2. Implementar só o escopo aprovado, preferindo funções isoláveis/testáveis.
3. Adicionar testes automatizados quando possível e checklist de Roblox Studio com 1, 2 e 4 clientes.
4. Rodar testes/lint se as ferramentas estiverem configuradas; se não, declarar o que não rodou.
5. Criar PR com: resumo, riscos, screenshots/clipes caso haja UI, resultados de testes, impacto em dados/economia/licenças e rollback.
6. Não mesclar nem publicar automaticamente sem autorização.

## Convenções futuras
`src/server/Services`, `src/client/Controllers`, `src/shared`, `tests`, `docs/architecture/ADR-*.md`. Não presumir que scripts em ServerStorage executam automaticamente.
