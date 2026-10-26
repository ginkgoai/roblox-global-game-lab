# Métricas, instrumentação e experimentos

Evento base sugerido: `session_started`, `onboarding_step`, `first_collect`, `first_upgrade`, `first_event`, `friend_join`, `shop_open`, `purchase_prompt`, `purchase_confirmed`, `session_end`. Não capturar PII fora do necessário, respeitando as políticas Roblox.

| KPI | Definição operacional | Decisão |
|---|---|---|
| PTR | início de sessão a partir de impressão relevante | avaliar thumbnail/título |
| First-play bounce | saída no intervalo curto após primeira entrada | analisar primeiro minuto |
| D1 / D7 / D30 | coorte de novos jogadores que retorna no dia correspondente | validar novidade, progressão e long game |
| Avg session | tempo médio por sessão, definido consistentemente | detectar tédio ou dificuldade |
| Co-play | sessões intencionais com amigos | avaliar profundidade social |
| Payer conversion | pagantes únicos / usuários elegíveis no período | revisar timing e percepção da oferta |
| ARPDAU | receita atribuída ao dia / DAU | acompanhar junto com retenção |
| Earned Robux eligible | saldo estimado para DevEx conforme portal | não confundir Robux comprados ou gastos brutos |

A Roblox oferece benchmarks comparáveis quando volume suficiente está disponível; não fixar 'D1 bom' arbitrário. https://create.roblox.com/docs/production/analytics

## Backlog de experimentos
E01 — 2 ícones com proposta diferente; mudar apenas o criativo, medir PTR + bounce.
E02 — explicar com dica versus animação contextual; medir conclusão de primeiro objetivo.
E03 — evento cooperativo opcional; medir co-play e D7, preservando experiência solo.
E04 — loja aberta após demonstração clara do loop versus loja no HUD desde início; medir retenção e conversão sem pressão.
