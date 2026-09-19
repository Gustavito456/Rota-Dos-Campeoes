# 🏆 Rota dos Campeões

> Um manager de futebol brasileiro para navegador, inspirado nos clássicos jogos de gestão esportiva e construído como uma aplicação web estática.

<p align="center">
  <strong>Escolha um clube da Série A, monte sua estratégia e percorra as 38 rodadas em busca do título.</strong>
</p>

<p align="center">
  <img alt="HTML5" src="https://img.shields.io/badge/HTML5-Frontend-E34F26?logo=html5&logoColor=white">
  <img alt="CSS3" src="https://img.shields.io/badge/CSS3-Interface-1572B6?logo=css3&logoColor=white">
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-Game%20Engine-F7DF1E?logo=javascript&logoColor=111">
  <img alt="Static" src="https://img.shields.io/badge/Arquitetura-100%25%20estática-2ea44f">
  <img alt="Temporada" src="https://img.shields.io/badge/Temporada-2026-7bd88f">
</p>

---

## ⚽ Sobre o projeto

**Rota dos Campeões** é um jogo de gerenciamento de futebol executado diretamente no navegador. A primeira versão concentra-se no **Campeonato Brasileiro Série A de 2026** e foi planejada para funcionar sem servidor, banco de dados ou instalação obrigatória.

O jogador escolhe um dos 20 clubes, administra o elenco, define formação e mentalidade, acompanha o calendário, simula partidas e tenta terminar as 38 rodadas no topo da classificação.

A proposta é preservar a simplicidade dos managers clássicos, porém com interface moderna e uma arquitetura preparada para receber novas competições, temporadas e sistemas de gestão.

## 🎮 Recursos desta versão

- ✅ 20 clubes da Série A 2026
- ✅ 717 jogadores na base inicial
- ✅ seleção de clube e criação de carreira
- ✅ campeonato completo com 38 rodadas
- ✅ turno e returno gerados automaticamente
- ✅ motor de simulação de partidas
- ✅ classificação atualizada a cada rodada
- ✅ pontos, vitórias, empates, derrotas, gols e saldo
- ✅ formações táticas
- ✅ mentalidade defensiva, equilibrada e ofensiva
- ✅ escalação automática por OVR RC
- ✅ pesquisa e filtro de jogadores
- ✅ índices próprios **OVR RC** e **POT RC**
- ✅ ranking histórico dos campeões brasileiros
- ✅ save automático com `localStorage`
- ✅ enriquecimento opcional de idade e valor de mercado por fonte pública
- ✅ interface responsiva

## 🧠 OVR RC e POT RC

Os atributos de jogadores usam um sistema próprio de **Rota dos Campeões**.

### OVR RC

O **Overall Rota dos Campeões** considera:

- força-base do clube;
- posição;
- variação determinística individual;
- idade, quando disponível;
- valor de mercado, quando a consulta externa consegue obtê-lo.

### POT RC

O **Potencial Rota dos Campeões** parte do OVR e adiciona margem de evolução, sobretudo para jogadores mais jovens.

> **Importante:** OVR RC e POT RC não são ratings oficiais da EA Sports, Football Manager ou qualquer outro jogo comercial. São índices autorais usados exclusivamente para o balanceamento deste projeto.

## 🏟️ Campeonato

A Série A segue o formato de pontos corridos:

- **20 clubes**
- **38 rodadas**
- **19 partidas em casa**
- **19 partidas fora**
- vitória: **3 pontos**
- empate: **1 ponto**
- derrota: **0 ponto**

No protótipo atual, os critérios de ordenação são:

1. pontos;
2. vitórias;
3. saldo de gols;
4. gols pró.

O calendário é gerado automaticamente pelo método circular e o segundo turno inverte os mandos.

## 🎲 Motor de partidas

Os resultados não são pré-definidos. Cada confronto considera fatores como:

- força média do onze inicial;
- força-base dos clubes;
- mando de campo;
- mentalidade escolhida;
- componente pseudoaleatório determinístico.

O resultado alimenta imediatamente a tabela da temporada.

## 🧩 Táticas

Formações disponíveis:

- `4-3-3`
- `4-4-2`
- `3-5-2`
- `4-2-4`
- `5-3-2`

Mentalidades:

- 🛡️ Defensiva
- ⚖️ Equilibrada
- ⚔️ Ofensiva

Nesta fase do projeto, a escalação escolhe automaticamente os jogadores com maior OVR RC em cada setor.

## 🏆 História da competição

A aba **Competição** apresenta um ranking histórico dos clubes com mais títulos brasileiros e destaca os participantes da edição de 2026.

A convenção usada na contagem histórica está documentada em [SOURCES.md](SOURCES.md).

## 💾 Save

A carreira é persistida no navegador usando:

```js
localStorage
```

Isso significa que:

- não é necessário criar conta;
- não existe backend;
- o save permanece no navegador utilizado;
- limpar os dados do navegador pode apagar a carreira.

## 🚀 Como executar

### Abrir diretamente

Clone ou baixe o repositório e abra:

```text
index.html
```

### Servidor local

Recomendado para reduzir restrições do navegador sobre requisições HTTP opcionais:

```bash
python -m http.server 8080
```

Depois abra:

```text
http://localhost:8080
```

## 📁 Estrutura

```text
Rota-Dos-Campeoes/
├── index.html       # estrutura da aplicação
├── styles.css       # identidade visual e responsividade
├── app.js           # motor da carreira e simulação
├── data.js          # clubes, jogadores e dados históricos
├── SOURCES.md       # metodologia e fontes
└── README.md
```

## 🏗️ Arquitetura

O projeto é deliberadamente **client-side**:

```text
HTML
  │
  ├── CSS → interface
  │
  └── JavaScript
       ├── carreira
       ├── calendário
       ├── motor de partidas
       ├── classificação
       ├── tática
       ├── elenco
       └── persistência local
```

Não há framework obrigatório e não existe dependência de backend para jogar.

## 🗺️ Roadmap

- [ ] escalação manual e banco de reservas
- [ ] substituições durante a partida
- [ ] eventos minuto a minuto
- [ ] cartões, lesões e suspensões
- [ ] artilharia e assistências
- [ ] mercado de transferências
- [ ] contratos e salários
- [ ] finanças e patrocínios
- [ ] categorias de base
- [ ] evolução e envelhecimento de jogadores
- [ ] múltiplas temporadas
- [ ] Série B, Série C e Série D
- [ ] Copa do Brasil
- [ ] Libertadores
- [ ] estaduais
- [ ] seleções
- [ ] exportar/importar saves
- [ ] PWA

## 📊 Dados

A base inicial foi organizada para a temporada de **2026**. Como transferências e empréstimos alteram elencos constantemente, partes do banco podem ficar desatualizadas com o tempo.

As fontes, ressalvas e decisões de modelagem estão descritas em **[SOURCES.md](SOURCES.md)**.

## ⚖️ Marcas e conteúdo

Rota dos Campeões é um projeto independente.

Nomes de clubes, competições e jogadores são empregados como referências factuais. O projeto não inclui escudos, fotografias nem assets proprietários do Brasfoot e não pretende reproduzir literalmente outro jogo.

## 🧑‍💻 Desenvolvimento

Projeto mantido por **Gustavito456**.

Sugestões e relatos de bugs podem ser registrados pelas Issues do repositório.

---

<p align="center">
  <strong>Rota dos Campeões</strong><br>
  <em>Do primeiro apito à taça.</em>
</p>
