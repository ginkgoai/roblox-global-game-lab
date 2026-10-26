# Arquitetura alvo (para depois de Gate 0)

Roblox Studio e Luau → Rojo → filesystem → Git → GitHub → Codex PRs. No MVP, preferir infraestrutura nativa Roblox (DataStore, MarketplaceService, Messaging quando necessário); Supabase/n8n externos não são dependência do core loop.

## Design previsto
`src/server/Services`: DataService, InventoryService, EconomyService, InteractionService, ProgressionService, PurchaseService, AnalyticsService.
`src/shared`: schemas tipados, configs comuns, IDs imutáveis de itens (preço sensível verificado no servidor).
`src/client/Controllers`: HUD, input mobile e apresentação visual.
`tests`: regras de economia, validação, persistência e permissões.

## Segurança
- Cliente solicita ação; server valida estado, distância, cooldown, limite, custo, propriedade, contexto e resultado.
- Rate limiting em todas as interações, incluindo remotes e proximity prompts.
- Persistência robusta: session lock/cache, schema versionado, retries/backoff, autosave e tratamento de falhas/privacidade.
- Compras: `ProcessReceipt` único, server side, idempotência por `PurchaseId`.
- Não importar plugins/modelos/anim scripts da Toolbox sem auditoria; inspecionar scripts ofuscados e chamadas de HttpService suspeitas.
- Nenhuma chave privada no client, place files ou repo.

## Critérios QA
- Teste de duas instâncias tentando o mesmo item.
- Teste 4 clientes no Studio; mobile Android/iOS e rede ruim.
- Exploits de requisições de moedas arbitrárias devem falhar.
- Reconexão durante compra não duplica recompensa.
- Falha simulada em DataStore não perde progresso silenciosamente.

Refs: https://create.roblox.com/docs/scripting/security/client-server-boundary ; https://create.roblox.com/docs/cloud-services/data-stores/best-practices
