# Publicar o Clube 3D Brasília

Destino: https://clube.3dbrasilia.com.br.

## HostGator

Plano Turbo existente, servidor br122. O cPanel informou o IP 192.185.211.132. Foi criado o domínio clube.3dbrasilia.com.br com raiz exclusiva /home4/aguami55/clube.3dbrasilia.com.br, sem compartilhar public_html.

No Registro.br, adicionar somente A clube = 192.185.211.132. Preservar raiz, www e registros de email.

Compilar localmente e compactar o conteúdo de dist-web (index.html na raiz do ZIP). Enviar ao diretório do Clube pelo Gerenciador de arquivos do cPanel e extrair ali. O pacote inclui .htaccess para fallback de rotas e LICENSE.txt. Não publicar fontes, node_modules ou credenciais.

Após propagação DNS, emitir o certificado pelo SSL/TLS/AutoSSL e ativar redirecionamento HTTPS apenas para clube.3dbrasilia.com.br. Conferir a página, manifest e service worker em HTTPS. O cofre só funciona em contexto seguro.

## Rebuild e verificações

1. Conecte o fork lexone/clube-3d-brasilia à hospedagem estática escolhida. Use a branch com a personalização aprovada.
2. Instalação: npm ci --ignore-scripts. Build: npm run build:web. Pasta pública: dist-web. Node: 24.15+ ou 22.22.2+.
3. Na hospedagem, adicione clube.3dbrasilia.com.br como domínio personalizado e copie o registro DNS fornecido por ela.
4. No provedor de DNS atual, crie o registro para **clube**, sem modificar os registros da raiz, www, email ou loja. O valor exato depende da hospedagem e não deve ser inventado.
5. Ative HTTPS antes de disponibilizar: o cofre de dados pessoais e o PWA precisam de contexto seguro.
6. Configure fallback SPA para index.html; não substitua assets ausentes por HTML. Evite cache longo para index.html e sw.js; assets com hash podem usar cache imutável.
7. Valide cálculo FDM/resina, reload, cofre, exportação PDF e instalação PWA no domínio final.
8. Adicione na navegação da Nuvemshop um link **Clube 3D Brasília** para o endereço publicado.

O app é independente da Nuvemshop; não há login compartilhado, pedidos automáticos ou integração com o checkout. Uma ligação por menu é suficiente para esta versão.

O favicon e os ícones instaláveis estão em public/. A licença original permanece em LICENSE e os créditos são visíveis no aplicativo.
