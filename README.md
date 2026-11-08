# Frente da Panfletagem — Rio Grande do Sul

Webmap das ruas panfletadas. **A marcação de novas panfletagens está desativada:** o site é estático e somente leitura, sem banco de dados.

Arquivos:
- `index.html` — o mapa com as ruas panfletadas
- `distribuicao.html` — quanto cada pessoa já panfletou
- `data/panfletagens.json` — todos os registros, exportados do Supabase em 08/11/2026 (792 registros em 750 ruas)
- `vendor/streets/` — ruas do RS que eram usadas para selecionar novas marcações (o site não as carrega mais)
- `vercel.json` — configuração mínima da Vercel

Sempre que algo for enviado ao GitHub, a Vercel republica sozinha.

## Como usar

- Toque em uma rua colorida para ver as datas em que foi panfletada. Quanto mais escura a cor, mais vezes ela foi panfletada.
- O botão de **localização** pula direto para onde você está (bom no celular).

## Sobre os dados

Cada linha de `data/panfletagens.json` é um registro, com os mesmos campos da antiga tabela `panfletagens`: `id`, `ponto_id`, `rua`, `lat`, `lng`, `tipo`, `data`, `created_at`, `pessoa` (quem panfletou) e `geom` (traçado da rua, `[[lat,lng],...]`). A tabela `wind_banners` estava vazia e por isso não foi exportada.

O arquivo é público, assim como o repositório: os nomes em `pessoa` ficam visíveis para qualquer pessoa.

A versão com marcação pelo Supabase, incluindo o `supabase.sql` e o `config.js`, continua no histórico do git, até o commit `fe63e31`.
