# GitHub open source — shortlist verificada em 25-10-2026

As licenças abaixo foram verificadas pelo campo `license.spdx_id` no metadado de repositório GitHub via conexão. É uma triagem inicial, não auditoria legal completa. Confirmar tag/commit, LICENSE, conteúdo, dependências e direitos sobre assets no momento de incorporar.

| Repo | Licença | Último push visto (UTC) | Papel | Cuidado |
|---|---|---|---|---|
| https://github.com/DLinacre/slime-factory-tycoon | MIT | 2026-10-01 | template de idle/tycoon, UI mobile, receipt/persistência conforme descrição | auditar build e assets, não clonar o jogo |
| https://github.com/EnigmaDevelopmentGroup/Industry-Tycoon | MIT | 2024-02-16 | referência para jogo industrial | desatualizado, não adotar dependências cegamente |
| https://github.com/mauupa0/roblox-rojo-game-template | MIT | 2026-10-01 | Rojo, ProfileStore e testes conforme descrição | validar integração e versões |
| https://github.com/MadStudioRoblox/ProfileStore | Apache-2.0 | 2025-07-31 | perfis e persistência | session locking, migrações, concorrência |
| https://github.com/Sleitnick/RbxUtil | MIT | 2026-08-11 | utilitários de serviço/comunicação | selecionar módulos mínimos |
| https://github.com/dphfox/Fusion | MIT | 2026-02-02 | UI reativa | custo de adoção, testes mobile |
| https://github.com/Zyn-ic/Stoway | MIT | 2026-10-24 | sistema inventário | pode ser excesso de escopo |
| https://github.com/kpackk/roblox-gameplay-systems | MIT | 2026-07-11 | sistemas gameplay server-authoritative | implementação de referência, auditar |
| https://github.com/rojo-rbx/rojo | MPL-2.0 | verificar no release | bridge de desenvolvimento | licença MPL-2.0, redistribuição depende obrigações |

## Checklist por dependência
- Verificar existência de LICENSE e autor/proveniência.
- Revisar arquivos source, scripts e chamadas remotas/API.
- Verificar licenças transitivas e eventual cópia de conteúdo não autorizado.
- Registrar commit exato e controles de atualização.
- Evitar games completos sem demonstrar direito de reutilizar mapas, música e texturas.
- Manter avisos exigidos em THIRD_PARTY_NOTICES.md.
- Sem licença explícita, tratar código como NÃO reutilizável até esclarecer direitos.

Nunca incluir código do colega sem licença/autorização própria. MIT/Apache dão direitos mediante condições; não outorgam automaticamente marcas ou assets de terceiros.
