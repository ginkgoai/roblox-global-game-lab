# Prompts acionáveis

## A: Pesquisa antes do código
Analise `docs/01_MARKET_EVIDENCE.md` e `docs/02_CONCEPT_LAB.md`. Sem gerar código, monte matriz crítica dos dois finalistas com: 10 concorrentes cada (fontes e data), diferenças reais, teste rápido com 10 jogadores, riscos de engenharia, prova de diversão da primeira sessão e decisão provisória com confiança. Não invente métricas nem entrevistas.

## B: Planejamento do MVP (somente após Gate 0)
Leia a decisão aprovada, `AGENTS.md` e o GDD final. Crie PRD de vertical slice de 3 minutos, sequência UX por segundo, estados do jogador, casos de erro, critérios de aceite verificáveis, tarefas independentes e plano mobile. Não modifique arquivos src/ nesta tarefa.

## C: Codex engineering (somente após Gate 0)
Implemente SOMENTE o ticket E-XX aprovado usando Luau e Rojo, sem APIs inexistentes e sem código externo não licenciado. Cliente solicita intenção; servidor valida e decide. Adicione testes e checklist com 4 clientes no Studio. Antes de editar, liste arquivos afetados e riscos. Ao concluir, informe testes executados e pendências, e faça PR sem merge automático.

## D: Auditoria open-source
Para os repos indicados em `docs/08_OPEN_SOURCE_AUDIT.md`, verifique licença por commit, autoria/proveniência, dependências, scripts ofuscados, integrações inseguras, modelos e assets. Classifique ADOPT, STUDY_ONLY ou REJECT. Forneça evidências e obrigações de notices. Não copie nenhum asset sem licença.
