# Hide the Disaster! — Product blueprint (DRAFT)
Coleta documental: 2026-10-26. Responsável por aprovação: Product Owner do projeto. Status: CANDIDATE, Gate 0 NOT APPROVED. Sem implementação autorizada.
Idioma do produto: inglês internacional; documentação: português.
Fontes de verdade: main/README.md, AGENTS.md, docs/02_CONCEPT_LAB.md, docs/DECISIONS.md; mais documentação oficial Roblox 2026 ao final.

## 1. PRD — Proposta e objetivo
Hook: "Four friends. One destroyed house. 90 seconds to hide everything."
Premissa: arrumar/esconder situações absurdas antes que um fiscal com regras ridículas inspecione uma casa. É um jogo de CAOS SOCIAL COOPERATIVO, não um simulador de limpeza passiva. Uma falha deve produzir humor e vontade de nova partida, sem humilhação/perdas injustas.
Diferencial TESTÁVEL: regras de inspeção variáveis alteram como os mesmos objetos devem ser organizados. Jogadores frequentemente criam um problema novo ao resolver outro. O fiscal analisa violações e contradições, não apenas procura objetos.
Mercados de teste: EUA, UK, Canadá; global sem geobloqueio. Público inicial a determinar conforme alcance das classificações e requisitos de publicação Roblox de 2026. Não depender de chat/voz.
KPIs após lançamento: PTR, first-play bounce, first-object interaction, first-round completion, next-round rate, plays-with-friends, D1/D7/D30, session time, conversion, ARPDAU, ARPPU, ads cost/qualified play. Benchmarks oficiais somente quando habilitados por tráfego.
North-star experimental: % de novos jogadores que completam uma rodada e iniciam outra. Não há histórico ou meta validada.
Premissas NÃO validadas: partidas 1–4 jogadores; ~3 minutos por rodada; 1 cenário, 3 regras, 10 arquétipos de objeto no MVP.

## 2. GDD — Gameplay
### Loop
Spawn > mostrar uma regra absurda > fiscal vai chegar > 90s para reorganizar, esconder e mitigar riscos > fiscal inspeciona > revelações cômicas > recompensa sem P2W > revanche com regra/combinação diferente.
Estados autoritativos de rodada: WAITING -> BRIEFING (15s) -> PREPARE (90s) -> INSPECTION (45s) -> RESULTS (15s) -> INTERMISSION (15s). Total nominal 180s por rodada. Durações só hipótese para teste.
MVP: 1 pequena casa com 4 cômodos; 10 tipos e ~15–20 instâncias interativas; 3 regras que reutilizam mesmo mapa; 1 fiscal NPC previsível; 1-4 jogadores; 4 ferramentas contextuais (pegar, largar, posicionar, esconder/fechar); câmera terceiro-person; toque acessível; pontuação compartilhada com contribuição visível sem roubo de recompensa.
Regras MVP propostas: (A) No Ducks Allowed (ocultar patos, pilhas fazem barulho), (B) Quiet House (objetos barulhentos invalidam esconderijo), (C) Furniture Must Make Sense (itens pontuam melhor em cômodos semanticamente plausíveis). Inspector rules MUST be readable before player action and evaluated deterministically.
Funniest moment: reveal cam inspeciona um esconderijo ruim e desencadeia cadeia cômica (porta abre, patos caem, rádio liga, inspetor reage). Cutscene curta e pulável; física não decide pontos.
Falhas: desordem aumenta pontuação de multas cômicas, não bloqueia próxima rodada; não exigir vitória perfeita.
Solo: quantidade-alvo reduzida e cronograma ajustado, mesmas recompensas proporcionais; sem bot complexo no MVP. Multiplayer: um objetivo compartilhado e feedback de colaboração, sem grief irreversível.
Sessões: 1 minuto primeira interação; 10 min ~3 rodadas; 30 min variações, medalhas e coleção cosmética. Nenhum cronômetro falso para compra.
Acessibilidade: sem obrigatoriedade de áudio, pistas com cores+ícones+texto, controle por toque com hit area grande, UI testada em tela pequena; textos curtos; evitar luz piscante intensa e câmera motion exagerada.
Padrão de avaliação: 3 níveis (PASS, MESSY, DISASTER) em vez de morte/tela punitiva; animar fiscal contextual.

## 3. Arquitetura após Gate 0
Stack: Roblox Studio + Luau --!strict quando aplicável; Rojo + GitHub; GitHub Issues + Codex PRs curtos; testes em Studio 1, 2 e 4 clientes. Dependências somente após auditoria de licenças e THIRD_PARTY_NOTICES.md.
Estrutura futura:
src/shared/Config; src/shared/Types; src/shared/Rules
src/server/Services/RoundService, ObjectService, InteractionService, InspectionService, RewardService, DataService, CommerceService, SecurityService, TelemetryService
src/client/Controllers/InputController, CameraController, UIController, EffectsController, AccessibilityController
assets/manifest.md; tests/; docs/architecture/ADR-*.md.
Arquitetura: cliente manda intenção (objeto ID, ação, célula/ponto de destino), servidor valida jogador vivo, fase, posse/reserva, distância, posição finita, destino permitido, colisões relevantes, rate limit, duplicatas e estado; servidor decide estado e pontuação. Apenas efeitos visuais/sons simulados localmente.
Estratégia física DECISÃO PENDENTE: opção 1, physics-first pleno (mais humor emergente, mais custo/desync/exploits); opção 2, state-driven com snap-zones + ragdoll/impulsos cômicos locais (recomendado como HIPÓTESE para MVP por robustez). Não depender de colisões/Touched client-owned para recompensas.
Fiscal MVP: máquina de estados e regras determinísticas, caminho fixo com pontos de inspeção, verificação de tags, visibilidade/permissão; sem IA generativa, NLP, NPC autônomo caro ou pathfinding não essencial.
DataStore: salvar apenas cosméticos possuídos, moedas internas, estatísticas e versão de schema; round state temporário no servidor, não em DataStore. Autossalvamento, retry/backoff, session locking ou alternativa equivalente auditada, tratamento de desligamento e erasure. Isolar dados de Studio/produção.
ProcessReceipt: concessão idempotente com Receipt/PurchaseId em servidor; nunca dar mercadoria por evento de cliente; consultar preços atuais via MarketplaceService para UI.
Observabilidade: contadores agregados de falhas remotas, latency/heartbeat, tempo de spawn, fps/memória mobile, erro de save, decisões de inspeção, queda e tempo até primeira ação. Evitar coletar PII desnecessária.

## 4. Conteúdo e progressão
Não lançar com 10 casas. Piloto: 1 casa icônica; variação obtida por 3 regras, pesos diferentes de objeto, pontos de inspeção e combinação de evento visual.
Progressão leve: álbum de "inspection disasters", crachás cômicos, títulos, skins de uniforme/fiscal, adesivos de mala, emotes moderados; recompensas de jogabilidade NÃO compráveis por vantagem. Sem quests manipulativas, lootbox paga, FOMO falso, cronômetro comercial, trade no MVP.
Proposta de atualização posterior, condicionada a retenção: casa do vizinho, cozinha de restaurante absurda, museu de objetos proibidos, regras e inspetores novos. Trabalhar reutilizando lógica de inspeção.

## 5. Monetização ética (somente após divertido e testado)
Free-to-play; sem pagamento para jogar, vencer, ocultar melhor ou sobreviver ao fiscal.
A) Passes de posse permanente: uniformes visuais, tema de mala/van, animação decorativa de vitória, efeitos cômicos sem bloquear visão.
B) Developer Products se necessário para consumíveis puramente cosméticos e explícitos, com recibos idempotentes; evitar monetização de re-roll de regra e boosts.
C) Servidor privado opcional conforme suporte/viabilidade Roblox.
D) Creator Rewards podem existir por engajamento elegível, não garantidos.
Exemplos de faixas de preço para teste financeiro, NÃO preços aprovados: 29/79/149/249 Robux. UI nunca hardcodar preço exibido, usar MarketplaceService e Managed Pricing quando aplicável.
A maioria das vendas em jogo de passes/products resulta em ~70% de Robux para o criador (conforme modalidade); rendimentos elegíveis e taxa DevEx são coisas distintas.
DevEx padrão 2026: mínimo 30.000 Earned Robux e taxa US$0.0038 -> US$114 antes de taxas de provedor/impostos. Isso implica aproximadamente 42.858 Robux em compras brutas se TODOS os ganhos vierem de produtos com 70% de participação, ignorando arredondamento/pendências/estornos. Não é previsão de venda, usuários ou faturamento.
Não pressupor taxa especial de DevEx de US$0.0054 (só alguns gastos elegíveis por jogadores verificados 18+ dos EUA, em jogos elegíveis). 
DevEx: 13+, e-mail verificado, Robux ganhos disponíveis, dados legais corretos, formulário W-8 para contribuinte não EUA, portal de pagamento Tipalti, conformidade contínua, revisão individual. Primeiro payout tempo estimado de processamento após cadastro completo 10 dias úteis + repasse bancário; não garantido. CNPJ vs CPF, W-8BEN vs W-8BEN-E e tributação Brasil precisam de contador antes do primeiro saque.

## 6. Publicação 2026 — público e conformidade
Conta Roblox 2+ dias, boa situação, verificação de idade e questionário de maturidade/conformidade para alcançar 16+ (ver detalhes oficiais atuais). Para Kids/Select (5–15) há verificação de criador, 2FA, requisito de taxa reembolsável/assinatura válida de 2+ meses e avaliação adicional. A documentação Roblox Kids/Select atual descreve 250 plays únicos de usuários 16+ altamente engajados nos 60 dias anteriores como parte da avaliação. Não confundir publicação inicial 16+ com ampla distribuição a menores.
Maturidade alvo hipotética Minimal/Mild e inspeções sem gore, violência, álcool ou crimes. Responder questionário factual baseado no build final; configurar controles de comunicação corretos; jogadores não dependem de chat.
Criação após Gate 0: experiência privada no Studio com publicar; configurar owner individual ou grupo (decisão empresarial+DevEx); público limitado/playtesters quando elegível; beta controlado; público quando passe QA e classificação; experiência pode ter beta mode afetando recomendação.
Credenciais, backups, licença de sons/imagens, nomes e copyright revisados antes de usar assets Toolbox. Se repo continuar público, não armazenar segredos nem material licenciado de acesso restrito.

## 7. Comercial e crescimento
Tese viral: imagem clara de fiscal prestes a abrir guarda-roupa com 20 patos; falhas cômicas; clipes espontâneos. Testar sem botão de upload ou gravação de dados pessoais.
Criativos: duas thumbnails honestas + variação de promessa textual; sem fingir cena impossível de gameplay. Curta demonstração de 6–12 segundos mostrando caos, regra e consequência. SEO relevante sem keyword spam.
Lançamento: closed playtest -> soft public 16+ se elegível -> corrigir first-play bounce e D1 -> só então investimentos de aquisição (Ads Manager permite objetivos Plays/Earnings e orçamento). Não assumir CPM, CPI ou distribuição automática.
Analytics: primeiro a conclusão da primeira rodada/segunda rodada e D1; depois D7/D30, ARPDAU, conversão, ARPPU, custo por jogador que volta. Benchmarks Roblox por semelhantes disponíveis com 100+ DAU conforme docs.
Não alegar que 30.000 earned Robux serão alcançados. Taxa de conversão 0% é cenário possível. Gastos pagos com ads podem tornar receita inicial negativa.

## 8. Riscos e mitigação
P0 originalidade: Cleanup Crew, Hide the Body, Hide the Food, Mess Mission e DISGUSTING HOUSE! já exploram esconder/arrumar antes de retorno. Diferencial deve ser auditado por observação direta de gameplay, vídeos e teste cego. NÃO copiar mecânicas específicas, código ou arte.
P0 móvel: pegar/colocar ruim, FPS e memória, objetos clipping: snap-zones, poucos móveis dinâmicos, pooling, colliders simplificados, sem physics-based economy; perfilar Android baixo/médio e iOS.
P0 griefing: bloquear movimento de colegas, atirar objeto fora do mapa, travar armários: reset de item, tempo máximo de posse, zonas de segurança, anti-spam.
P0 repetição: 3 regras podem não sustentar >3 rodadas; testar sessões sequenciais sem progressão, medir divergência de momentos e gargalo conteúdo.
P0 economia/segurança: compras, moeda, perfis, duplicatas/lag e abuso de remote.
P1 chat/moderação: sistema deve ser divertido sem voice/chat, com ping de contexto.
P1 classificação/público: distribuição inicial 16+ pode ter menor acessibilidade que públicos 9–15; planejar revisão Kids/Select.
P1 ownership/IP: confirmar licença, marca/nome e titular de receita antes de lançar.
P2 custo de infraestrutura: Roblox hospeda a experiência; CDN externa, IA e servidor VPS não necessários no MVP.

## 9. Roadmap sugerido (não aprovado; pessoa-semanas)
Gate 0 DISCOVERY: concorrência, 6 criativos de concept art para trio ou 2 do selecionado, 10–20 entrevistas anglófonas, diferenciação, paper-playtest, quadro de riscos, ADR do responsável.
G1 vertical slice: 1 cômodo, 3 objetos distintos, 1 regra, timer, fiscal simplificado, resultado/revanche; 1 e 2 jogadores touch; 3 min.
G2 MVP: 4 cômodos, 10 arquétipos/15–20 objetos, 3 regras, solo/1–4 coop, scripts estáveis, proteção básica, telemetria e interface.
G3 private alpha: QA mobile (baixo/médio), segurança, perf, casos de grief e 10–20 playtesters documentados.
G4 limited/public beta: formulário de conteúdo, requisitos de publicação, materiais corretos, cohorts e métricas.
G5 launch: nova rodada e D1 saudáveis, exceções solucionadas; desbloquear monetização ética; acompanhar DevEx.
Estimativa editorial pós Gate0: 10–18 pessoa-semanas para MVP estável de equipe 1–2 pessoas; variância considerável, separar calendário e trabalho. Sem receita estimada.
Disciplina: atualizar PRD/GDD/ADR/roadmap/backlog/changelog a cada sprint, ticket Codex exige acceptance criteria, teste e risco, PR revisado, nenhum merge/publicação automáticos.

## 10. Gate 0 — CONTINUA BLOQUEADO
- [ ] Inspecionar ao menos 10 concorrentes relevantes (incluindo Cleanup Crew) com screenshots, gravações e avaliações de fricção.
- [ ] Criar 2 thumbnails novas, rotuladas concept art, de cada um dos candidatos em comparação.
- [ ] Coletar 10–20 opiniões reais anglófonas cegas, sem indução; documentar metodologia e resultados.
- [ ] Demonstrar em storyboard a diferença entre "Hide the Disaster!" e Cleanup Crew; registrar hipótese e refutação.
- [ ] Avaliar primeiros 1/10/30 minutos e diversão solo/co-op.
- [ ] Conferir IP, marca, fontes de assets, conteúdo e público da Roblox.
- [ ] Comparar concept contra Midnight Cleanup Crew e Lost & Found (tradeoffs esforço, risco, descoberta, segurança).
- [ ] Nova decisão formal e aceite em docs/DECISIONS.md, nomeando uma única vertical slice.
Não codificar até aceite registrado. Nenhuma entrevista, screenshot própria, KPI ou Robux de receita de nosso jogo foi obtida.

## Referências oficiais (coletadas 2026-10-26)
- Discovery: https://create.roblox.com/docs/production/promotion/discovery
- Creator analytics: https://create.roblox.com/docs/production/analytics
- Publishing: https://create.roblox.com/docs/production/publishing/publish-games-and-places
- Kids/Select: https://create.roblox.com/docs/production/publishing/kids-and-select
- Maturity: https://create.roblox.com/docs/production/promotion/content-maturity
- Network physics: https://create.roblox.com/docs/scripting/security/network-ownership
- Server boundary: https://create.roblox.com/docs/scripting/security/client-server-boundary
- DataStore: https://create.roblox.com/docs/cloud-services/data-stores
- Performance: https://create.roblox.com/docs/performance-optimization
- DevEx: https://create.roblox.com/docs/production/monetization/developer-exchange
- DevEx Terms: https://en.help.roblox.com/hc/en-us/articles/115005718246-Developer-Exchange-Terms-of-Use
- Managed Pricing: https://create.roblox.com/docs/production/monetization/regional-pricing
- Developer Products: https://create.roblox.com/docs/production/monetization/developer-products
- Creator Rewards: https://create.roblox.com/docs/creator-rewards
- Ads Manager: https://create.roblox.com/docs/production/promotion/ads-manager

## Exemplos públicos de concorrência (desk review, não playtest)
- https://devforum.roblox.com/t/feedback-on-wacky-crime-scene-cleanup-game-beta/3504706
- https://www.roblox.com/games/81239378558719/Hide-the-body
- https://www.roblox.com/games/8116526775/Mess-Mission
- https://www.roblox.com/games/125393996808318/DISGUSTING-HOUSE
- https://www.roblox.com/games/103549510760447/Hide-the-Food
- https://www.roblox.com/games/121834700527934/Clean-Streamer-House
