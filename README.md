# Roblox Global Game Lab

**Status (25-10-2026):** DISCOVERY / conceito em avaliação. **Nenhum jogo implementado ou publicado.**

## Missão
Criar uma experiência Roblox original, mobile-first, inicialmente em inglês (EUA/UK/Canadá), com sessões socialmente divertidas, progresso legível e monetização transparente em Robux. Primeiro validar a diversão e a retenção, depois escalar descoberta/receita.

## Candidatos a conceito
1. **Anomaly Harvest Co.** — fazenda + indústria de anomalias, máquinas e eventos cooperativos; recomendação inicial do relatório, porém sujeito a validação de originalidade e aquisição.
2. **Midnight Cleanup Crew** — contratos cooperativos de limpeza noturna com imprevistos paranormais; candidato forte a vídeos virais.
3. **Lost & Found: Impossible Items** — administrar loja de itens impossíveis: identificar, reparar, negociar e lidar com comportamentos inesperados dos objetos; hipótese nova a testar.
4. **DroneWorks: Scrap League** — criar drones e extrair sucata; mais complexo para primeira entrega.

**Decisão:** sem escolher o conceito final e passar o Gate 0, o Codex NÃO deve desenvolver o jogo. O relatório inicial avalia principalmente três conceitos, e a pontuação qualitativa não substitui teste real com jogadores.

## Gate 0: decisão de produto
- Confirmar diferenciação em relação aos 10 jogos comparáveis do mesmo gênero.
- Validar duas miniaturas + uma frase-promessa e entender qual chama atenção.
- Obter feedback de no mínimo 10 potenciais jogadores anglófonos, idealmente com teste cego.
- Criar especificação de vertical slice de 3 minutos, sem monetização agressiva.
- Revisar legalidade/licença de dependências, nome e assets.
- Só então abrir tarefas de código e definir a experiência Roblox.

## Fluxo de trabalho
ChatGPT Project (visão, pesquisa, decisões) -> GitHub Issues + docs (fonte de verdade) -> Codex (PRs pequenos, revisados) -> Rojo + Roblox Studio (mundo e testes) -> beta -> analytics -> novos sprints.

## Pastas
- `PROJECT_INSTRUCTIONS.md`: cole nas configurações de Projeto no ChatGPT.
- `AGENTS.md`: instruções permanentes para Codex.
- `docs/`: mercado, conceitos, GDD, segurança, economia, roadmap, métricas, compliance, backlog, licenças.
- `templates/`: instrumentos de pesquisa.

## Criar o workspace
1. No ChatGPT, barra lateral -> **Novo projeto**, título **Roblox Global Game Lab**.
2. Em **Configurações do projeto**, cole `PROJECT_INSTRUCTIONS.md`.
3. Adicione este pacote, especialmente os documentos `docs/` e o relatório original da pesquisa como fontes do Projeto.
4. No GitHub, crie repositório **privado** `roblox-global-game-lab` e envie esta estrutura. Não confunda Projeto ChatGPT com repositório GitHub.
5. Abra o repositório com o Codex (GitHub/IDE/CLI conforme acesso) e mantenha o arquivo `AGENTS.md` na raiz.

## Fontes prioritárias
- Roblox discovery https://create.roblox.com/docs/discovery
- Roblox analytics https://create.roblox.com/docs/production/analytics
- Roblox DevEx https://create.roblox.com/docs/production/monetization/developer-exchange
- Roblox Security https://create.roblox.com/docs/scripting/security/client-server-boundary
- ChatGPT projects https://help.openai.com/en/articles/10169521-projects-in-chatgpt
- Codex https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan

**Importante:** jogo compartilhado por colega é somente exemplo de referência. Sem permissão expressa e licença apropriada, não copiar código, mapa, modelos, nomes, interface ou outros assets desse jogo.