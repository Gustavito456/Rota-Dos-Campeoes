# Fontes e notas de dados — 19/09/2026

## Competição e participantes
- CBF — página oficial do Brasileirão Série A 2026 e tabela.
- Sofascore — Brasileirão 2026, clubes participantes e páginas de elenco.

## Elencos
Os nomes e posições do banco inicial foram compilados a partir das páginas públicas de elenco do Sofascore para:
Flamengo, Palmeiras, Athletico, Bahia, Fluminense, Cruzeiro, Atlético-MG, Coritiba,
RB Bragantino, Santos, Botafogo, São Paulo, Vitória, Corinthians, Mirassol, Grêmio,
Vasco, Internacional, Remo e Chapecoense.

Os IDs públicos de equipe do Sofascore permanecem em `data.js`, permitindo que o navegador tente atualizar
data de nascimento/idade e valor de mercado sem alterar o banco local. Essa chamada pode ser bloqueada por CORS,
antibot, indisponibilidade ou mudança da API; por isso o jogo não depende dela para funcionar.

## OVR e potencial
Pesquisamos páginas públicas de ratings da EA e bases de FC, mas elas não formam uma base pública consistente
que mapeie todos os jogadores reais dos 20 elencos brasileiros atuais. Em alguns bancos, clubes brasileiros aparecem
com atletas genéricos por questões de licenciamento.

Por esse motivo, o jogo usa OVR RC/POT RC autorais. Não são apresentados como números oficiais de terceiros.

## Títulos brasileiros
A aba Competição usa a seguinte convenção até a temporada 2025:
Palmeiras 12; Flamengo 9; Santos 8; Corinthians 7; São Paulo 6;
Cruzeiro, Vasco e Fluminense 4; Internacional, Atlético-MG e Botafogo 3;
Bahia e Grêmio 2; Athletico, Coritiba, Guarani e Sport 1.

Observação: contagens históricas do Campeonato Brasileiro podem variar conforme a convenção usada para 1987.
O jogo adota Flamengo com 9 títulos, seguindo fontes esportivas que contabilizam 1987 para o clube.


## Idades dos jogadores
O jogo prioriza idades confirmadas por bases públicas de elenco. Quando a consulta externa não retorna um jogador ou é bloqueada pelo navegador, a interface usa temporariamente uma idade estimada pelo próprio jogo, marcada com `~`.

Esse marcador é intencional: uma idade estimada não deve ser confundida com um dado factual confirmado. À medida que dados verificados forem incorporados ao banco local, o símbolo deixa de aparecer para esses atletas.

Também foram consultadas páginas de elenco detalhado do Transfermarkt para conferir idades de referência em jogadores presentes na base.
