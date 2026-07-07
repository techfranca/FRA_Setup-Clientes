# DESIGN.md — Franca Setup de Clientes (ferramenta interna)

> Marca da **Franca** (projeto interno). Herda o design system do
> `franca-contratos` para consistência entre as ferramentas internas.
> Fonte da verdade completa no vault: `internos/FRA_Identidade-Visual.md`
> (derivado do MIV 2.0). Consultar antes de criar/alterar telas.

## Direção visual (1 frase)
Ferramenta interna **premium, sóbria e centralizada** — geométrica e minimalista,
usando o *slant* do logotipo como grafismo (trama de fundo, marcadores de seção).

## Cores (tokens — oficiais do MIV)
- Primária (acento): `--green: #7DE08D` (hover `#71ca7f`, dark `#5ea86a`)
- Texto verde sobre claro: `--green-deep: #4b8655` (AA)
- Navy (âncora/texto/CTA): `--navy: #081534`
- Fundos suaves: `--green-tint: #f2fcf4` · `--green-soft: #d7f5dc`
- Neutros: papel `#fafcfa` · superfície `#ffffff` · texto `#0f1d3a` · linhas `#e7ecf3`
- Erro: `--danger: #e11d48`

## Tipografia
- Títulos: **Poppins** (600/700)
- Corpo: **Montserrat** (400/500/600)
- Escala: h1 ~2.4rem · section-title 1.05rem · body .95rem · eyebrow .72rem uppercase

## Bordas & raios
- Radius: sm 12px · md 18px. Bordas 1px `#e7ecf3`.

## Sombras
- sutil (cards) → média (card ativo) → forte (sucesso). Ver `--shadow-*`.

## Layout (painel operacional)
- **Tela de operação, não landing:** cabeçalho compacto alinhado à esquerda,
  hero enxuto, densidade voltada a preenchimento rápido.
- Container largo `max-w-[1100px]`. Cliente ocupa a largura total no topo do painel.
- **Desktop (lg+):** 2 colunas — `grid-cols-[minmax(0,1fr)_320px]`: dados
  operacionais na coluna principal, serviços na lateral. Objetivo: pouco/nenhum
  scroll em 1440×900.
- **Mobile:** empilhado (serviços abaixo dos dados); barra de ações **sticky** no
  rodapé da viewport.
- Campos compactos (~46px), gaps enxutos. Info do cliente = resumo horizontal.

## Componentes
- **Botão:** navy sólido, texto branco, brilho verde diagonal no hover, 1 linha só.
  Variante `.btn-green` para ações de WhatsApp; `.btn-ghost` para secundário.
- **Título de seção:** marcador diagonal verde (motivo do logo) antes do texto.
- **Inputs:** fundo branco, foco com anel verde `rgba(125,224,141,.22)`; `.error` rosa.
- **Serviços:** checkbox em card premium com check verde ao marcar; painel
  lateral (`.services-side`) no desktop, empilhado no mobile.
- **Info do cliente:** painel `green-tint` horizontal (label verde + valor).
- **Barra de ações (`.action-bar`):** "Limpar" (ghost) + "Criar setup" (navy),
  à direita no desktop; sticky no rodapé no mobile.
- **Header:** logo real (`logo.png`) + wordmark Poppins + chip "Setup Interno".

## Movimento
- Sutil: uma orquestração no load (stagger `.rise`). Respeitar `prefers-reduced-motion`.

## Estados de UI
- **Loading:** spinner escuro centralizado no card.
- **Vazio:** tela dedicada centralizada ("Nenhum cliente pendente" + "Atualizar lista").
- **Erro:** card com ícone vermelho + "Tentar novamente".
- **Sucesso:** selo verde + resumo das planilhas + ações de grupo.

## Rodapé
- "Feito por Franca Marketing" → WhatsApp `5521991097451` (padrão da agência).
