# Supertecnicos — Cartola FC 2026

Site editorial enxuto da liga Supertecnicos · Cartola FC. Mobile-first, classificação + rodadas + estatísticas, com destaques fortes para **MVP**, **Mitada** (≥80 pts) e **Lanterna** — por rodada e acumulado.

## Estrutura

```
fantasy/
├── index.html      # site completo (HTML + CSS + JS, single-file)
├── dados.csv       # dados da temporada
└── README.md
```

## Formato do CSV

Três colunas. Header é opcional (o parser detecta automaticamente):

```csv
rodada,time,pontos
1,Sons of Númenor,87.45
1,Ironverdict,102.30
...
```

- **rodada**: número inteiro (1, 2, 3, …)
- **time**: nome exato do time (case-sensitive)
- **pontos**: aceita ponto ou vírgula como separador decimal

O loader tenta os arquivos nesta ordem (use o nome que preferir):
1. `Resultados_do_Campeonato.txt`
2. `Resultados do Campeonato.txt`
3. `resultados.csv`
4. `dados.csv`

## Times oficiais (com escudo e cor próprios)

Sons of Númenor · Ironverdict · Icebergteam · Andorinha Jr · Andorinha · CEEC · Varelitas · Otopatamá · Lobonegro

> Times fora dessa lista funcionam normalmente — recebem escudo dourado padrão com as 2 primeiras letras como monograma.

## Conceitos

- **MVP da rodada** → maior pontuação na rodada
- **Mitada** → qualquer pontuação ≥ **80 pts** (várias por rodada são possíveis)
- **Lanterna da rodada** → menor pontuação na rodada
- **Rei MVP / Rei Mitada / Rei Lanterna** → quem mais acumulou cada categoria

Para mudar o limite de mitada, edite `MITOU_THRESHOLD = 80` no script (linha logo após `'use strict'`).

## Deploy no GitHub Pages

```bash
# 1. Crie o repositório no GitHub
git init
git add .
git commit -m "Supertecnicos · Cartola 2026"
git branch -M main
git remote add origin https://github.com/SEU-USER/SEU-REPO.git
git push -u origin main

# 2. No GitHub: Settings → Pages → Source: "Deploy from a branch" → main / root → Save
# 3. URL fica em: https://SEU-USER.github.io/SEU-REPO/
```

## Atualizar dados a cada rodada

1. Edite `dados.csv` adicionando as linhas da nova rodada
2. `git add dados.csv && git commit -m "R06" && git push`
3. O GitHub Pages republica em ~30s · refresh no celular pega a versão nova (cache-bust automático no fetch)

## Recursos

- 📱 **Mobile-first**, layout até 560px (boa leitura para 45-50)
- 🌓 **Light/dark mode** com persistência (botão lua/sol no topo)
- 📲 **PWA**: pode ser "instalado" como app no iOS/Android (Add to Home Screen)
- 🎨 **Identidade editorial**: tipografia Oswald + Barlow + JetBrains Mono, paleta cream/gold/ink
- ⚡ **Zero dependências de build**: HTML estático puro
- 🛡️ **Cache-bust** no fetch do CSV — sem dor de cabeça com cache

## O que foi enxugado em relação à v3 anterior

Removido para deixar mais limpo e direto: heatmap de todas as rodadas, position tracker (gráfico SVG de posições), drawer lateral de perfil/comparador de clubes, "Notas da Temporada".

Mantido: identidade visual editorial, escudos SVG por time, light/dark, PWA, Hall of Fame.

Adicionado: destaque grande de **MVP/Mitada/Lanterna** em cada rodada, **Reis do Campeonato** acumulados, ranking de mitadas (≥80) por time, lista "Mitaram nesta rodada" com chips.

---

Liga Supertecnicos · Temporada 2026
