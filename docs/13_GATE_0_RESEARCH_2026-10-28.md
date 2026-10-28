# Gate 0 — Comparação competitiva e plano de validação (DRAFT)

**Coleta:** 2026-10-28 (America/Sao_Paulo)  
**Status:** DISCOVERY / NÃO APROVADO / nenhuma implementação autorizada.  
**Fonte de verdade:** README.md, AGENTS.md, PROJECT_INSTRUCTIONS.md, docs/00_DEEP_RESEARCH_REPORT_2026.md, docs/01_MARKET_EVIDENCE.md, docs/02_CONCEPT_LAB.md e docs/DECISIONS.md de ginkgoai/roblox-global-game-lab, branch main.  
**Classificação:** DADO VERIFICADO = fonte externa ou repo; HIPÓTESE = demanda ou performance não demonstrada; OPINIÃO = pontuação editorial; DECISÃO APROVADA = nenhuma sobre conceito.

## 1. Correção de rota documental

O relatório inicial (docs/00) prefere Anomaly Harvest Co., mas sua comparação foi feita antes de Lost & Found entrar no laboratório e trata como reaproveitáveis elementos de um jogo/protótipo de batatas. Isso conflita com a regra posterior de propriedade intelectual em AGENTS.md, docs/11_IP_AND_REFERENCE.md e DECISIONS.md. **Não reutilizar código, UI, mapas, arte ou outros assets de colega sem autorização e licença compatível.** O GDD de Anomaly continua DRAFT. Esta análise não altera nem aprova DECISIONS.md.

## 2. Demanda real: o que foi verificado

- Roblox Q2/2026: 123 milhões de DAUs, 29 bilhões de horas e 27 milhões de pagantes únicos mensais. Mercado da plataforma, **não** TAM de qualquer proposta. A Roblox informa cerca de 22 milhões de DAUs para **EUA + Canadá em conjunto** e não disponibiliza no recorte consultado a preferência por nossos três conceitos. Fontes: [shareholder letter SEC](https://www.sec.gov/Archives/edgar/data/1315098/000162828026051059/ex991-robloxq22026earnin.htm), [10-Q SEC](https://www.sec.gov/Archives/edgar/data/1315098/000162828026051082/rblx-20260630.htm).
- [Newzoo, 19/10/2026](https://newzoo.com/reports/roblox-grows-up): análise de preferências com sobre-indexação de arcade, co-op e survival-horror; **não** mede intenção de jogar Midnight Cleanup Crew. 
- [GameAnalytics 2026, publicado 01/09/2026](https://www.gameanalytics.com/reports/2026-roblox-report): amostra de mais de 500 jogos com >=1M MAU, agosto/2025-julho/2026. A mediana D1 de **10,3%** vale para essa seleção de jogos grandes; não transformar em meta automática para projeto novo. Os dados de uso multi-dispositivo não equivalem a participação das sessões mobile.
- [Roblox Charts, captura de outubro/2026](https://www.roblox.com/charts) traz títulos de tarefas simples (Fix My Phone!, Chop A Forest, Clean Crew) e horror/coop (99 Nights, Dandy's World), evidenciando que existem audiências para esses arquétipos — não que nossa abordagem obterá descoberta.
- A [documentação de discovery](https://create.roblox.com/docs/discovery) destaca PTR, bounce, play days, playtime, co-play e sinais de monetização. [Analytics](https://create.roblox.com/docs/production/analytics) recomenda acompanhar D1 e tempo de sessão antes de escalar aquisição e oferece benchmarking quando houver dados suficientes (100+ DAU para scorecards de similares).
- **Não foram coletadas** entrevistas independentes, intenção de compra, custo de aquisição, métricas de retenção dos três conceitos nem dados separados de EUA/Reino Unido/Canadá para o nicho.

## 3. Competitive scan: 10 títulos por conceito (SHORTLIST, NÃO AUDITORIA COMPLETA)

Legenda: D = concorrência mecânica próxima; A = adjacente / benchmark de loop. O nome e a existência são verificados em páginas Roblox, charts ou perfis listados nas fontes; classificação de sobreposição e atritos são análises editoriais. **Ainda faltam screenshots e gameplay observado para todos os dez de cada finalista**, portanto D-01 não está concluído.

### Anomaly Harvest Co. (coletar > processar > automação > incidente)

| Título | Tipo | Mecânica comparável / ameaça |
|---|---|---|
| [Grow a Garden](https://www.roblox.com/games/126884695634066/Grow-a-Garden) | D | Plantar-colher-progredir, produção offline, social-flex. Muito fácil confundir a promessa com mais uma fazenda. |
| [Farming and Friends](https://www.rolimons.com/game/2772610559) | D | Fazenda co-op, máquinas e expansão. Diferenciar autonomia de sistemas, não apenas estética. |
| [Farm Factory Tycoon](https://www.roblox.com/games/10198661638/Farm-Factory-Tycoon) | D | Evolução tycoon agrícola e compra de upgrades. |
| Prehistoric Farm | A | Outra exploração temática de fazenda; verificar profundidade mecânica. |
| Run Your Own Farmstead! | A | Gestão de uma fazenda; comparar first-time user experience. |
| Chop A Forest | A | Verbo claro de coleta e progressão; risco de loop repetitivo. |
| Bee Swarm Simulator | A | Progressão coletiva/colecionismo complexa; risco de grind. |
| Build An Ant Empire | A | Fabricação/expansão com fantasia imediatamente reconhecível. |
| [Sell Fries! (Anomaly)](https://www.roblox.com/games/94891079210424/Sell-Fries) | **D CRÍTICO** | Página descreve explicitamente batatas > fritas > clientes > upgrade > noite perigosa. Sobreposição da arquitetura dramática original. |
| [Dig & Clean](https://www.roblox.com/games/83038462357724/Dig-Clean) | A | Trabalho tátil, revelação surpresa e coleção/exibição. |

Fonte adicional de existência de títulos sem link direto acima: [charts Roblox](https://www.roblox.com/charts?SortFilter=default&TimeFilter=0&nl=true).

**Diferencial a testar (HIPÓTESE):** incidentes não são monstros genéricos; são alterações locais das regras da fábrica (esteira reversa, sombra que duplica recursos, solo com gravidade lateral), resolvidas com lógica simples e coop opcional. **Risco:** pode ainda parecer Sell Fries! com skin de laboratório. **Retenção:** coleções de espécies, máquinas combinatórias, desafios ambientais semanais, upgrades visuais, projetos cooperativos. **Monetização pós-fun:** bancadas decorativas, pinturas de máquinas, uniformes, emotes; upgrades econômicos pagos exigem avaliação de justiça. **Esforço hipotético para vertical slice após aprovação:** 2–4 semanas de uma pessoa; risco técnico médio-baixo, risco de saturação alto.

### Midnight Cleanup Crew (limpar > reagir a anomalia > extrair > upgrades)

| Título | Tipo | Mecânica comparável / ameaça |
|---|---|---|
| [Clean Crew](https://www.roblox.com/games/128637868413472/Clean-Crew) | **D CRÍTICO** | **Já é** survival-horror multiplayer de limpeza em apartamentos abandonados, com classes, upgrades, ameaças, solo difícil e ajudante. Diferença da proposta original é insuficiente. |
| [Wash The House](https://www.rolimons.com/game/130960835358983) | D | Amigos limpam, recolocam objetos e fazem upgrades. |
| [Carpet Cleaning Simulator](https://www.robloxapp.vnggames.com/games/124374448373637/Carpet-Cleaning-Simulator) | D | Prazer da limpeza e ampliação dos serviços, com pequenas surpresas. |
| Clean Everything | A | Satisfação de completar tarefas; título visto em charts. |
| Wash the Car | A | Microações satisfatórias de limpeza; título visto em charts. |
| [Dandy's World](https://www.roblox.com/games/16116270224/Dandys-World) | A | Completar máquinas com aliados sob ameaça; trinkets e personagens. |
| DOORS | A | Variação de ameaças por sala e onboarding acessível. |
| 99 Nights in the Forest | A | Compromisso co-op e sobrevivência; cuidado com complexidade. |
| [Sell Fries! (Anomaly)](https://www.roblox.com/games/94891079210424/Sell-Fries) | A | Tarefa cotidiana + evento noturno; potencial de clonagem de estrutura. |
| [Airport Security (Anomaly)](https://www.roblox.com/games/108334808788078/Airport-Security) | A | Trabalho noturno, triagem, tensão e decisões erradas. |

**Diferencial a testar (HIPÓTESE):** restaurar locais com histórias emergentes onde cada objeto limpo muda as regras da próxima tarefa, evitando apartamentos, classes, mascote-ajudante e combate semelhantes a Clean Crew. **Risco:** exige pivot material; combinação limpeza + horror co-op está ocupada. **Retenção:** contratos curtos com variações transparentes, equipamento cosmético, álbum de acontecimentos, crew achievements; não transformar em grind de classes. **Monetização pós-fun:** roupas, luvas, efeitos, equipamentos com skin, customização de van; sem revives pagos necessários. **Esforço hipotético após aprovação:** 3–6 semanas de uma pessoa; risco técnico médio-alto (sincronização de sujeira, rede, eventos). **Status proposto:** manter como challenger, bloquear avanço na forma atual até demostrar diferenciação substancial.

### Lost & Found: Impossible Items (inspecionar > deduzir > restaurar/encaminhar > coleção)

| Título | Tipo | Mecânica comparável / ameaça |
|---|---|---|
| [Fix My Phone!](https://www.roblox.com/games/139165770588984/Fix-My-Phone) | D | Reparos táteis, negociação, loja, decoração, itens raros. |
| [Toy Repair Shop (Anomaly)](https://www.roblox.com/games/113837625806960/Toy-Repair-Shop) | **D CRÍTICO** | Consertar objetos estranhos no turno da noite; sobreposição de fantasia. |
| [Airport Security (Anomaly)](https://www.roblox.com/games/108334808788078/Airport-Security) | D | Observar documentos e pistas, julgar casos e punir falhas. |
| Animal Hospital (Anomaly) | A | Profissão comum + inspeção sobrenatural; presente em charts/spotlight. |
| [Dig & Clean](https://www.roblox.com/games/83038462357724/Dig-Clean) | D | Revelar objeto, avaliar raridade e expor em coleção. |
| [Find the Markers](https://www.roblox.com/games/7896264844/Find-the-Markers) | A | Progressão via catálogo de itens descobertos. |
| Make Rugs! | A | Artesanato interativo e progressão; presente em charts. |
| Build a Keyboard! | A | Microtarefas físicas e customização; presente em charts. |
| Search For The Needle | A | Procura/discovery e satisfação da descoberta; presente em charts. |
| RoPair | A | Reparos como loop de tarefa; presente em charts. |

**Referência externa / risco de nome:** [Lost & Found (Steam)](https://store.steampowered.com/app/5218570/Lost__Found/) descreve loja de achados e perdidos com inspeção e atribuição de itens a donos. Não copiar esse conceito específico; **revisar nome e marca** antes da aprovação.

**Diferencial a testar (HIPÓTESE):** cada objeto tem uma regra absurda **observável**, duas interpretações plausíveis e uma decisão consequente. O jogador identifica a propriedade, executa microexperimento e decide devolver, conter ou exibir. Evitar rotina genérica de apertar botões; gerar variações combinatórias com regras legíveis. **Retenção:** catálogo de leis físicas impossíveis, visitas de clientes recorrentes, episódios curtos com pistas, vitrine social; conteúdo artesanal é gargalo. **Monetização pós-fun:** skins de bancada, prateleiras, iluminação, uniforme, vitrines temáticas; nenhum item que revele a solução do mistério pago. **Esforço hipotético após aprovação:** 3–5 semanas de uma pessoa; risco técnico médio, risco de volume de conteúdo alto.

## 4. Matriz de decisão ponderada — OPINIÃO, BAIXA CONFIANÇA

Escala 1–5 (5 melhor). Não são métricas Roblox nem dados de receita. Pesos obrigatórios de docs/02_CONCEPT_LAB.md.

| Critério (peso) | Anomaly | Midnight | Lost & Found |
|---|---:|---:|---:|
| Originalidade percebida (25%) | 1,5 | 1,5 | 3,5 |
| Viabilidade solo (20%) | 4,5 | 3,0 | 3,0 |
| Retenção potencial (20%) | 4,0 | 4,0 | 3,5 |
| Monetização sem P2W (15%) | 3,5 | 4,0 | 3,5 |
| Marketing orgânico (10%) | 3,5 | 4,0 | 3,5 |
| Moderação/segurança (10%) | 4,0 | 3,0 | 4,0 |
| **Total ponderado (/5)** | **3,35** | **3,08** | **3,45** |

Cálculo: soma(nota × peso decimal), arredondamento 2 casas. Em empate prático Anomaly vs Lost (0,10 ponto), usar pesquisa de preferência/diferenciação como desempate — diferença é menor que incerteza editorial.

**OPINIÃO provisória:** priorizar evidência para **Lost & Found** (primeira hipótese) e **Anomaly reformulado** (alternativa de escopo mais simples). **Midnight fica em observação** por concorrência quase direta com Clean Crew. **DECISÃO APROVADA: nenhuma.**

## 5. Vertical slices conceituais de 3 minutos (STORYBOARD, NÃO CÓDIGO)

### Anomaly Harvest — “The rules of farming are broken”
- 0:00–0:20: o jogador vê uma única planta impossível e aprende a colher com um toque grande.
- 0:20–1:00: colhe três frutos, coloca na máquina e recebe feedback claro do processamento.
- 1:00–1:50: escolhe uma de duas melhorias *gratuitas*, ambas alteram visualmente o fluxo.
- 1:50–2:30: um incidente inverte uma esteira; jogador gira uma válvula e reconecta a produção.
- 2:30–3:00: recupera o produto perdido, ganha amostra e vê uma regra impossível nova para futura visita.
- **3 minutos medem:** primeira ação sem instrução verbal, entendimento do incidente, vontade de descobrir outra regra; testar solo e co-op opcional.
- **1/10/30 minutos:** loop básico / primeira cadeia de máquinas / coleção de fenômenos com progressão visual.

### Midnight Cleanup — “Clean the evidence. Don't erase the truth.”
- 0:00–0:20: chegada à garagem surreal; painel mostra 3 focos de sujeira, sem HUD complexo.
- 0:20–1:00: limpeza direta de uma superfície por gesto simples no mobile; resultado satisfatório.
- 1:00–1:50: objeto limpo projeta um eco da sala, mudando um caminho; o jogador reorganiza objetos.
- 1:50–2:30: duas tarefas simultâneas; amigos dividem trabalho ou jogador solo alterna ferramentas.
- 2:30–3:00: saída e relatório de restauração; consequência visual de uma escolha irreversível.
- **3 minutos medem:** prazer de limpeza + surpresa genuína sem susto gratuito. Diferencial contra Clean Crew precisa ser julgado por 10 jogadores cegos.
- **1/10/30 minutos:** limpar / contrato com 2 regras / três contratos com variações e história coletiva.

### Lost & Found — “Every object has a secret.”
- 0:00–0:25: chega um guarda-chuva que pinga água para cima; duas etiquetas de procedência, uma suspeita.
- 0:25–1:00: toca o objeto, aproxima de uma lâmpada e observa a regra sem texto longo.
- 1:00–1:45: compara símbolos no recibo com reação do objeto; cliente faz afirmação contraditória.
- 1:45–2:30: decide devolver, conter ou catalogar; objeto responde de modo visual e determinístico, com consequência clara.
- 2:30–3:00: novo cliente chega e um segundo objeto reage ao primeiro — gancho para a próxima sessão.
- **3 minutos medem:** compreensão de pistas mobile, sensação de descoberta e agência, desejo de segundo caso.
- **1/10/30 minutos:** um caso / três regras distintas / vitrine, clientes recorrentes e dilemas cooperativos.

Em todos: zero Robux e zero implementação até Gate 0; todos os textos de interface do futuro jogo em inglês internacional. Arte de conceito deve ostentar “Concept art — not in-game”.

## 6. Backlog de validação e bloqueios

| Ticket | Prioridade | Entrega / aceite verificável | Bloqueia |
|---|---|---|---|
| D-01A | P0 | 10 jogos comparáveis de **Lost**, cada um com URL/ID, data, icon + screenshot próprio, 30–90s de gameplay observado, core loop, primeiro minuto, compras e 1 atrito específico com evidência | Gate 0 |
| D-01B | P0 | Mesmo protocolo de 10 jogos para **Anomaly reformulado**; comparação explícita com Sell Fries! | Gate 0 |
| D-01C | P1 | Estudo profundo Clean Crew e contrafactual de pivot Midnight (ideia realmente diferente ou arquivar) | Reentrada Midnight |
| D-02 | P0 | Dois criativos por cada um dos 2 finalistas + pitch de 1 linha; teste cego/randomizado de compreensão em 3 segundos; sem chamar thumbnail conceitual de in-game | Gate 0 |
| D-03 | P0 | 10–20 jogadores anglófonos **sem ligação com o projeto**, recrutamento e consentimento adequado, registro de respostas anônimas sem PII, perguntas neutras de docs/02, país/autodeclaração de faixa etária apenas quando apropriado | Gate 0 |
| D-04 | P0 | Jornada 1/10/30 min, diferencial social opcional e storyboard 0–180 s para cada finalista; teste de leitura de controles mobile em mockup | Gate 0 |
| D-05 | P0 | Matriz refeita com evidência por nota, análise de sensibilidade (+/-1 nas notas de originalidade e viabilidade) e ata de alternativa rejeitada | Gate 0 |
| D-06 | P0 | Revisar conflito de título/marca, licenças das bibliotecas/repos, assets e fontes; manter THIRD_PARTY_NOTICES conforme aplicável; **não usar assets de colega** | Gate 0 |
| D-07 | P0 | Threat model de compras, inventário, DataStore, remotes e sessões co-op; checklist de conteúdo e economia justa; sem implementação | Gate 0 |
| D-08 | P1 | Estimativa por ticket de esforço/risco para 1 e 2 pessoas, anti-features e critérios de corte para MVP. Nenhuma estimativa de receita sem medição. | Gate 0 |
| D-09 | P0 | Revisão final Go/No-Go; **assinatura explícita da escolha por responsável** em docs/DECISIONS.md, link para evidências e rejeições; só então liberar E-01 e Gate 1 | Engenharia |

**Limites de coleta:** avaliações públicas e comentários Reddit representam opinião auto-selecionada, não amostra representativa. Exemplo de sinal qualitativo de incômodo com grind: [Dandy's World Reddit, 04/03/2026](https://www.reddit.com/r/DandysWorld_/comments/1rknfap/dw_is_nothing_but_a_grindy_game_now/). Não extrapolar CTR, D1 ou disposição a pagar de comentários.

## 7. Estratégia ética, riscos e métricas após Gate 0

- Primeiro testar o loop grátis. Só avaliar catálogo de 3–5 cosméticos após evidência de diversão; sem lootboxes no MVP, urgência falsa, paywall da solução ou “comprar para vencer”. [Monetization policy](https://create.roblox.com/docs/production/monetization); [paid random items](https://create.roblox.com/docs/production/monetization/paid-random-items).
- Preços regionais devem ser apresentados por MarketplaceService de forma dinâmica, nunca hard-coded: [Regional pricing](https://create.roblox.com/docs/production/monetization/regional-pricing).
- O padrão DevEx consultado é US$0,0038 por **Earned Robux elegível**, não por Robux de gasto bruto, condicionado às regras do programa: [DevEx](https://create.roblox.com/docs/production/monetization/developer-exchange). **Nenhuma projeção de Robux ou lucro foi produzida.**
- Futuro implementation guardrail: cliente envia intenção, servidor valida tipos, contexto, distância, cooldown, inventário e economia; recibos ProcessReceipt server-side idempotentes; bibliotecas auditadas. [Roblox client-server](https://create.roblox.com/docs/scripting/security/client-server-boundary).
- Instrumentação pós-aprovação: PTR e first-play bounce (até 60s / 61–180s), conclusão de onboarding, tempo de sessão, co-play, D1/D7/D30, payer conversion, ARPDAU, ARPPU, CAC e estabilidade mobile. Nenhum resultado desses existe ainda para o projeto.

**CONCLUSÃO DO GATE 0 EM 28/10/2026:** **NO-GO para implementação.** A atual priorização de Lost & Found e Anomaly é uma **recomendação de quais hipóteses validar primeiro**, não uma seleção definitiva de jogo. Revisar Gate 0 após D-01A/B, D-02, D-03, D-04, D-05, D-06, D-07 e D-09.
