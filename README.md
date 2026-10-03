# Clube 3D Brasília

Calculadora de custos e gestão de impressão 3D para a 3D Brasília. Versão web personalizada do [Open3DCalc](https://github.com/ils15/open3dcalc), baseada no commit 0fa0619 (2.0.0-beta.9).

Destino escolhido: **https://clube.3dbrasilia.com.br**. Loja: [3dbrasilia.com.br](https://3dbrasilia.com.br). O endereço do aplicativo ainda depende da publicação e do DNS.

## Executar

Node.js 24.15+ (ou 22.22.2+) e npm. Para a web não é necessário compilar os módulos nativos do Electron:

```sh
npm ci --ignore-scripts
npm run dev:web
```

Desenvolvimento: http://localhost:3000.

## Validar e gerar a versão web

```sh
npm run typecheck
npm run lint
npm run test:run
npm run build:web
npm run preview:web
```

A saída de produção está em **dist-web/**. Os comandos padrão npm run dev e npm run build também selecionam a versão web.

## Publicação

Publique o conteúdo de dist-web/ em um serviço de hospedagem estática com HTTPS e aponte apenas o subdomínio clube.3dbrasilia.com.br para esse serviço. Configure o fallback de rotas para index.html. Não altere o DNS da loja principal. O build usa caminhos relativos e o PWA tem escopo próprio.

Consulte [DEPLOY.md](DEPLOY.md) para as configurações e integração com a loja.

## Dados e recursos

Calculadoras FDM e resina, visualização 3D, catálogo, estoque, clientes, histórico e orçamentos. Dados locais ficam no navegador; dados pessoais seguem o cofre criptografado herdado do projeto. Não existe backend de contas ou sincronização entre dispositivos nesta adaptação. A interface de assistente herdada é apenas uma demonstração, sem serviço de IA conectado.

A base upstream é beta e já documenta falhas de testes no shell Studio. O estado verificado desta adaptação será registrado em VALIDATION.md.

## Origem e licença

Código original: Open3DCalc, copyright (c) 2026 Open3DCalc, licença MIT. O arquivo [LICENSE](LICENSE) foi preservado integralmente. A licença permite uso comercial, modificação e redistribuição com preservação do aviso de copyright e da licença. As dependências e os exemplos têm seus próprios avisos; consulte [docs/CREDITS.md](docs/CREDITS.md).

Alterações desta versão: identidade Clube 3D Brasília, metadados web/PWA, ícones próprios, documentos de publicação e ligação à loja. A documentação original e o histórico de versões estão preservados em [README.upstream.md](README.upstream.md) e CHANGELOG.md.
