# Diretrizes de UX/UI para o MTube

## Visão geral
- Objetivo: oferecer navegação de vídeo fluida, clara e acessível, mantendo consistência de marca em todas as telas (login, página inicial, upload, visualização de vídeo, clipes, categorias, busca e comentários).
- Tom visual: minimalista, inspirado em plataformas de streaming, com hierarquia forte de tipografia e cards.
- Identidade: logo com "MTube" em peso 700, cores principais Azul (#1A73E8) e Grafite (#202124) com neutros claros; modo escuro usando cinzas 900/800 para fundos e azul suavizado (#5C8FF5) para realces.

## Princípios de marca e acessibilidade
- Tipografia: família "Inter" ou "Roboto"; títulos 24–32 px; corpo 14–16 px; contrastes AA (texto principal 4.5:1, botões 3:1).
- Espaçamento: grid de 8 px com colunas responsivas (12 colunas ≥1200px, 6 colunas tablets, 2–3 colunas mobile).
- Estados: hover, foco e pressionado claramente diferenciados; foco visível (outline 2 px azul/white conforme modo).
- Componentes reutilizáveis: botões primários/secundários, chips de categorias, cards de vídeo, input com label flutuante, dropdowns, toasts.
- Acessibilidade: teclas de atalho para busca (/), pular para conteúdo (skip link), ARIA para controles de player e upload; suporte a leitores de tela em botões de ação e notificações.

## Navegação e fluxos principais
- Header persistente (home/watch) com logo que leva à home, campo de busca central, actions à direita (upload/notification/profile). Sidebar colapsável com categorias e seções (Início, Inscrições, Clipes, Biblioteca).
- Fluxo de novo cadastro/login: entrada de email → senha → preferências de modo de cor → chegada na home com onboarding (tour em tooltips destacando busca, upload e categorias). Recuperação de senha e login social opcionais.
- Fluxo de upload: clicar em "Criar" abre modal/overlay de upload → seleção de arquivo ou arrastar → preencher título/descrição/tags/categoria/miniatura → barra de progresso com feedback visual e estados (em envio, processando, concluído) → CTA para "Ver vídeo" ou "Criar clipe".
- Fluxo de navegação entre seções: sidebar/links em cartões de categoria; breadcrumb minimal na página de vídeo (Home / Categoria / Vídeo). Chips filtráveis em home e busca.

## Wireframes (descritos)
- **Login**: layout centrado, card 420–480 px; logo no topo, título e subtítulo; campos empilhados com labels flutuantes; links de ajuda abaixo; toggle de modo escuro e seletor de idioma no rodapé.
- **Página inicial**: header com busca; banner rotativo opcional; grid de cards de vídeo com miniatura 16:9, título em 2 linhas, autor, views e duração; chips horizontais de categorias; seção de clipes em carrossel; call-to-action para upload.
- **Upload**: overlay em fullscreen com stepper (Upload → Detalhes → Visibilidade → Resumo). Área de dropzone com ícone grande, botão "Selecionar arquivo" e legenda de formatos. Progresso linear e percentual; campo para miniatura custom; preview do card final à direita.
- **Visualização de vídeo**: player 16:9 fixo no topo da coluna esquerda; título + metadados + ações (like, dislike, compartilhar, salvar, clipar). Tabs abaixo do player para "Descrição", "Transcrição" e "Comentários". Sidebar direita com lista de próximos vídeos e clipes relacionados.
- **Clipes**: feed em cards verticais com duração curta; botão "Criar clipe" no player (selecionar intervalo com sliders) gerando preview e possibilidade de compartilhar ou salvar.
- **Categorias**: página com chips filtráveis e mosaico de playlists; cada categoria mostra destaque em hero pequeno e uma fileira de vídeos.
- **Busca**: campo fixo no header; resultados em lista com miniatura à esquerda e metadados à direita; filtros laterais (duração, tipo, upload date, live); empty state com ilustração e CTA para explorar categorias.
- **Comentários**: ordenação por relevância/recente; caixa de comentário com avatar e estado de foco claro; threads com indentação leve; ações de moderação (denunciar, bloquear) em menu kebab; contadores acessíveis.

## Modo escuro e personalização
- Toggle no header/profile com persistência local. Paleta escura usando tons #0F1115 (bg), #16181D (cards), texto #E8EAED. Bordas e divisores semi-transparentes. Destaques usam azul suave ou roxo opcional quando usuário escolhe acento personalizado (paleta predefinida acessível).
- Cartões e inputs ganham sombra suave e bordas mais claras no escuro para manter contraste. Ícones com 70–90% de opacidade e aumentam para 100% no hover.

## Animações e microinterações
- Transições de página/vídeo: fade-slide de 120–200 ms ao abrir um vídeo; mudança de miniaturas com scale-in leve. Player troca de fonte de vídeo com crossfade e spinner minimal.
- Upload: barra de progresso animada; ícone de check com micro bounce ao concluir; toast de sucesso/erro com cores consistentes com tema. Drag-over da dropzone muda borda para tracejado e cor de acento.
- Hover em cards: elevação + sombra sutil; indicador de duração no canto; botão rápido de "Adicionar à fila".

## Layout responsivo
- Mobile: header compacto com ícone de busca que expande em full width; cards em 1–2 colunas; player em proporção 16:9 antes dos detalhes; carrossel de clipes horizontal.
- Tablet: 2–3 colunas de cards; sidebar oculta por padrão com botão de menu; filtros de busca em bottom sheet.
- Desktop: sidebar fixa e colapsável; 4–6 colunas em grid; páginas de vídeo com layout de duas colunas (player + related).

## Feedback e estado do sistema
- Uploads e ações críticas exibem confirmações e estados (processando, agendado, público/privado). Erros com mensagens claras e ação recomendada. Skeleton loaders em listas de vídeo e comentários.
- Indicadores online para lives; badge de novo conteúdo em categorias e inscrições. Modo offline mostra aviso discreto e fila de ações pendentes.

## Próximos passos
- Criar protótipos de alta fidelidade no Figma com variações clara/escura.
- Construir biblioteca de componentes (Design System) com tokens de cor/typography/spacing compartilhados no CSS.
- Testar fluxos de onboarding, upload e criação de clipes com 5–7 usuários para validar clareza das interações.
