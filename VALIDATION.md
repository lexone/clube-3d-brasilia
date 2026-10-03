# Validação da personalização

Em Windows, com Node 24.13.0 e dependências do lockfile:

- TypeScript: aprovado.
- ESLint: aprovado na personalização.
- Build web/PWA: aprovado; saída em dist-web.
- Testes focados de marca, empacotamento, idiomas, compartilhamento e privacidade: 198 aprovados.
- Conferência visual local: calculadoras FDM e resina, marca, acesso à loja e modo demonstração.

A suíte completa inicial executou 4.236 testes: 4.176 aprovados e 60 falhas. Comparando os arquivos com falhas contra o upstream sem modificações, 57 falhas foram reproduzidas pelo mesmo nome, incluindo incompatibilidades com caminhos/processos Windows e testes de layout existentes. Duas expectativas de marca/URL foram atualizadas e aprovadas na suíte focada. Uma integração SQLite excedeu o tempo na suíte completa e passou isoladamente no upstream; sua causa não foi determinada.

O build avisou sobre bundles grandes, especialmente o gerador de PDF. Não foi feita uma auditoria de segurança ou de todas as licenças de dependências. O projeto de origem está em beta. Recursos desktop/Electron não foram validados para distribuição.

O cofre exige senha escolhida pelo próprio usuário. A conferência em demonstração não comprova persistência do cofre nem exportação PDF com perfil desbloqueado.
