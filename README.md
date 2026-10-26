# Portfólio 3D — Pedro Passos

Código completo da versão com câmera próxima, terreno contínuo e nomes sempre visíveis abaixo dos ícones.

## Publicar na Vercel pelo GitHub

1. Extraia este ZIP.
2. Envie o conteúdo extraído para um repositório GitHub. Na raiz devem ficar `vercel.json`, `README.md` e a pasta `dist`.
3. Na Vercel, escolha Add New > Project e importe o repositório.
4. Framework Preset: Other. Root Directory: raiz do repositório. Build Command: vazio. Output Directory: dist.
5. Clique em Deploy.

O arquivo vercel.json já informa a pasta de saída. Não precisa de npm install, npm run build, chaves de API ou banco de dados.

## Rodar localmente

Com Python instalado, abra o terminal na pasta extraída:

```sh
python -m http.server 8000 --directory dist
```

Abra http://localhost:8000 no navegador. Não abra index.html por duplo clique: os módulos JavaScript e a leitura do JSON precisam de um servidor HTTP.

## Arquivos para editar

- dist/index.html: estrutura da página e menus.
- dist/style.css: cores, fontes, layout e nomes dos projetos.
- dist/app.js: mundo 3D, câmera, veículo, ícones, descrições e regras do jogo.
- dist/projects.json: nomes, categorias e links dos 24 projetos.
- dist/vendor/three.js: Three.js 0.170.0, incluído localmente.
- dist/vendor/THREE-LICENSE.txt: licença MIT da biblioteca.

Categorias em projects.json: 0 = Web; 1 = Jogos; 2 = Design; 3 = IA.
Mantenha os IDs existentes: eles vinculam ícones e progresso aos projetos.
Os textos descritivos dos projetos estão em descriptions, no arquivo app.js.

Na trilha de Jogos, Jornada EPT aborda o ensino de Educação Profissional e Tecnológica em um curso ministrado sobre o tema. Percurso: A História da Robótica apresenta uma jornada interativa sobre a evolução da robótica e foi apresentado no CBIE 2025.

## Controles

WASD ou setas para pilotar; E para abrir o projeto próximo; arraste para girar a câmera; roda do mouse ou pinça para zoom. Toque no terreno para navegar. Há controles na tela para celular.

## Observações

- O progresso é salvo no localStorage do navegador e é separado por domínio. O progresso no endereço antigo não migra automaticamente para a Vercel.
- Postify e App cardápio ainda não têm links públicos. Substitua seus valores url: null em projects.json quando tiver os endereços.
- O 3D requer WebGL. A coleção de projetos oferece acesso alternativo.
- Não há autenticação própria no código. O site publicado na Vercel não herda a restrição de acesso do ChatGPT Sites; use as configurações de acesso da Vercel se precisar restringi-lo.
