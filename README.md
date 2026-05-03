# Supertecnicos · Cartola 2026

Site single-file da liga. HTML+CSS+JS, zero build.

## CSV

```csv
rodada,time,pontos
1,Sons of Númenor,87.45
1,Ironverdict,102.30
```

Header opcional. Vírgula ou ponto como decimal. Nomes aceitos: `dados.csv`, `resultados.csv`, `Resultados_do_Campeonato.txt`, `Resultados do Campeonato.txt`.

## Deploy

```bash
git add . && git commit -m "init" && git push
```

GitHub → Settings → Pages → Deploy from branch → `main` / root.

## Atualizar rodada

Edita `dados.csv`, commit + push. Atualiza em ~30s.

## Config (no topo do `<script>` em `index.html`)

- `MITOU_THRESHOLD = 80` — limite de mitada
- `TOTAL_ROUNDS = 38` — total da temporada
