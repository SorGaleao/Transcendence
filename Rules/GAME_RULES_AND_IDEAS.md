# Transcendence - Jogo de Tabuleiro Online (Concept)

## 1) Visao geral

Projeto de jogo online multiplayer com tema de navios pesqueiros e pirataria leve.

- Inspiracao: mistura de Quartz + King of Tokyo.
- Jogadores: 6 a 8 jogadores por partida.
- Objetivo: terminar a partida com mais dinheiro acumulado pela venda de peixes.
- Ponto central de decisao: risco vs recompensa entre mares mais seguros e mares mais perigosos.


## 2) Mapa e mares

O tabuleiro possui 5 mares:

- 1 mar central (mais calmo).
- 4 mares externos em volta do centro.

Regra de dificuldade (seguindo sentido horario a partir do canto superior direito):

1. Mar Externo A (mais facil)
2. Mar Externo B
3. Mar Externo C
4. Mar Externo D (mais dificil)

Quanto maior a dificuldade:

- maior o perigo ambiental,
- maior a qualidade/valor medio da pesca,
- maior a chance de eventos negativos.


## 3) Capacidade por mar

Cada mar tem limite de navios. Quando um mar esta lotado e alguem tenta entrar, ocorre batalha.

Capacidade sugerida para balanceamento (pode ajustar em testes):

- Mar Central: 4 vagas
- Externo A: 2 vagas
- Externo B: 2 vagas
- Externo C: 2 vagas
- Externo D: 2 vagas


## 4) Condicao de vitoria

- A partida dura numero fixo de rodadas (sugestao: 10 a 14).
- Ao final, vence quem tiver mais moedas.
- Desempate:
1. Maior valor de conjuntos de peixes completos.
2. Maior quantidade de peixes raros vendidos.
3. Maior vida restante.


## 5) Estrutura de turno

Cada rodada possui as fases abaixo:

1. Fase de Planejamento
- Jogador escolhe 1 acao principal (ou mais se cartas permitirem).

2. Fase de Movimento
- Jogador pode tentar mudar de mar.
- Se o mar de destino estiver cheio, inicia batalha de ocupacao.

3. Fase de Acoes
- Jogador usa cartas/efeitos ativos.
- Acoes ofensivas, defensivas ou economicas.

4. Fase de Perigo Ambiental
- Cada jogador no mar sofre teste de perigo conforme o nivel do mar.

5. Fase de Pesca (obrigatoria)
- Todo jogador deve pescar no fim do turno.
- Quantidade e qualidade dependem do mar e de buffs/debuffs.

6. Fase de Mercado
- Jogador pode vender parte ou total da carga.
- Sets de peixes garantem bonus de venda.


## 6) Acoes disponiveis antes de encerrar rodada

Lista base de acoes por turno (1 acao principal por padrao):

- Mover para outro mar.
- Reparar casco (recuperar vida).
- Fortificar navio (ganhar defesa temporaria).
- Saquear alvo (roubar 1 peixe aleatorio com chance de falha).
- Jogar carta de ataque/defesa/utilidade.
- Negociar (vender com bonus pequeno em mercado favoravel).


## 7) Sistema de combate

Combate acontece quando:

- jogador tenta entrar em mar lotado,
- carta ou habilidade cria conflito direto.

Formato sugerido para combate rapido online:

- Cada lado rola 1d6 + ataque do navio + modificadores de carta.
- Quem perder sofre dano igual a diferenca minima de 1.
- Melhor de 3 trocas, ou ate um lado desistir.

Resultado em disputa por vaga:

- Vencedor ocupa a vaga no mar disputado.
- Perdedor recua para mar adjacente valido.
- Se nao houver mar valido, vai para mar central.


## 8) Vida, dano e eliminacao

Vida base sugerida por navio:

- HP inicial: 10

Fontes de dano:

- Combate entre navios.
- Perigos do mar.
- Algumas cartas/eventos.

Quando HP chega a 0:

- Navio afunda.
- Jogador perde parte da carga (sugestao: 50% dos peixes aleatorios).
- Jogador volta no proximo turno no Mar Central com HP parcial (sugestao: 6).

Observacao de design:

- Evitar eliminacao permanente ajuda experiencia online (ninguem fica sem jogar por muito tempo).
- Modo hardcore opcional pode permitir morte definitiva.


## 9) Pesca e economia

Tipos de peixe (exemplo inicial):

- Comum: Sardinha, Anchova
- Incomum: Atum, Cavala
- Raro: Espadarte, Salmao Azul
- Epico: Peixe-Lua Dourado

Tabela simples por mar (exemplo):

- Mar Central: alta chance de comum, baixa chance de incomum
- Externo A: comum + incomum
- Externo B: incomum consistente, raro baixo
- Externo C: raro medio, risco alto
- Externo D: raro alto, chance epico, risco muito alto

Venda:

- Peixes vendidos geram moedas imediatas.
- Segurar peixe para completar set pode render mais no futuro.


## 10) Conjuntos de peixes (set collection)

Conjuntos sugeridos:

- Cardume Local: 3 peixes comuns diferentes -> bonus de venda fixo.
- Exportacao: 2 incomuns + 1 raro -> bonus alto.
- Trofeu do Oceano: 2 raros + 1 epico -> bonus muito alto.

Regras de set:

- Set pode ser vendido a qualquer momento na Fase de Mercado.
- Cada set consumido remove os peixes usados do inventario.


## 11) Cartas de acao

Deck inicial com cartas de uso rapido:

- Ataque Extra: +1 ataque nesta rodada.
- Canhao Pesado: +2 em uma unica troca de combate.
- Cortina de Fumaca: ignora 1 ataque recebido.
- Casco Reforcado: ignora dano ambiental nesta rodada.
- Roubo Oportunista: rouba 1 peixe aleatorio de um alvo no mesmo mar.
- Rede Especial: +1 peixe na pesca obrigatoria.
- Manobra Evasiva: cancela tentativa de saque contra voce.

Regras de cartas:

- Mao maxima sugerida: 3 cartas.
- Compra sugerida: 1 carta a cada 2 rodadas, ou por evento.
- Limite por turno: 1 carta (salvo efeitos especiais).


## 12) Perigos do mar

Cada mar externo tem tabela de risco. Exemplo:

- Externo A: 20% de chance de sofrer 1 dano.
- Externo B: 30% de chance de sofrer 1 dano.
- Externo C: 40% de chance de sofrer 1-2 dano.
- Externo D: 50% de chance de sofrer 2 dano.

Perigos podem incluir:

- Tempestade.
- Rochas ocultas.
- Correnteza.
- Monstro marinho.


## 13) Regras de sincronia para versao online

Como sera online, usar modelo server-authoritative:

- Servidor valida toda acao de jogo.
- Cliente apenas envia intencao (acao desejada).
- Estado final sempre decidido no servidor.

Eventos em tempo real (WebSocket) sugeridos:

- lobby:update
- game:start
- turn:begin
- player:move
- combat:start
- combat:result
- hazard:result
- fishing:result
- market:sell
- card:played
- player:sunk
- game:end

Requisitos de robustez:

- Reconexao com recuperacao de estado.
- Timeout de turno para evitar travamento.
- Log de eventos para auditoria e replay simples.


## 14) Fluxo de partida (alto nivel)

1. Lobby
- Criacao da sala.
- Entrada de 6 a 8 jogadores.
- Escolha de configuracoes (rodadas, modo normal/hardcore, seed opcional).

2. Preparacao
- Distribuicao de navios iniciais.
- Posicionamento inicial no mar central.
- Cartas iniciais (opcional).

3. Rodadas
- Executa fases de turno para todos os jogadores.
- Atualiza ranking parcial por moedas.

4. Encerramento
- Ultima venda de peixes.
- Bonus de sets.
- Desempates.
- Tela final com ranking e estatisticas.


## 14.1) Modo rapido para avaliacao

Modo pensado para partidas curtas e mais faceis de testar em sala.

Objetivo do modo:

- reduzir a duracao total da partida;
- manter o risco vs recompensa;
- simplificar cartas e tomadas de decisao;
- remover combate direto entre jogadores.

Regras principais:

- partida com 4 a 6 rodadas;
- sem limite rigido de navios por mar;
- a disputa entre jogadores acontece de forma indireta, pela pressao de lotacao no mesmo mar;
- cartas de acao sao mais simples e com efeitos imediatos.

Perigo por lotacao do mar:

- cada mar tem seu perigo base;
- a cada jogador extra no mesmo mar, o perigo aumenta;
- sugestao simples: para cada navio acima do primeiro no mesmo mar, todos ali recebem +1 de dano ou +1 no teste de perigo;
- o aumento pode ter teto para nao ficar exagerado, por exemplo +3 no maximo;
- isso faz mares cheios ficarem mais arriscados, mesmo sem batalha.

Estrutura resumida do turno:

1. Movimento
- o jogador escolhe um mar de destino;
- pode mudar ou ficar;
- mares cheios nao bloqueiam entrada.

2. Perigo do mar
- aplica o perigo base do mar;
- aplica o bonus de lotacao conforme o numero de navios presentes.

3. Pesca obrigatoria
- todo jogador pesca no fim do turno;
- mares mais perigosos oferecem pesca melhor, mas com mais risco.

4. Mercado
- o jogador pode vender peixes ou guardar para sets.

Cartas simplificadas:

- Movimento Rapido: move sem custo extra.
- Reparo Leve: recupera 1 ou 2 de vida.
- Escudo Naval: ignora 1 dano neste turno.
- Rede Melhorada: ganha +1 peixe na pesca.
- Venda Favoravel: vende com pequeno bonus.

O que esse modo ganha:

- partidas mais curtas;
- menos regras para explicar;
- menos tempo parado;
- mais foco em posicionamento e risco ambiental.

O que esse modo perde:

- menos confronto direto;
- menos imprevisibilidade entre jogadores;
- menos profundidade tática de combate.

Conclusao provisoria:

- para avaliacao do projeto, esse modo rapido parece uma boa escolha;
- ele preserva a identidade do jogo e simplifica o tempo de partida sem apagar a decisao principal de ir para um mar seguro ou arriscado.


## 14.2) Como suportar os dois modos sem duplicar trabalho

A melhor estrategia e compartilhar o nucleo do jogo e mudar apenas parametros e algumas regras especificas por modo.

Base comum dos dois modos:

- mesma estrutura de partida;
- mesmos mares e sistema de pesca;
- mesma economia de moedas e venda de peixes;
- mesmo sistema de cartas, com lista diferente conforme o modo;
- mesmo modelo de turno no servidor.

Diferenças por configuracao:

- numero de rodadas;
- presenca ou nao de limite de navios por mar;
- intensidade do perigo ambiental;
- existencia ou nao de combate direto entre jogadores;
- quantidade e complexidade das cartas.

Forma pratica de organizar:

- o modo rapido pode ser o padrao de avaliacao;
- o modo normal reaproveita as mesmas fases, mas com regras mais completas;
- sempre que possivel, a logica deve sair de uma configuracao do tipo `mode = quick` ou `mode = full`;
- assim evita-se criar dois jogos separados.

Vantagem dessa abordagem:

- menos codigo duplicado;
- menos risco de bug;
- balanceamento mais simples;
- mais facil demonstrar o projeto sem abandonar a ideia do modo completo.


## 15) Indicadores e estatisticas uteis

Para historico de partida e perfil do jogador:

- Moedas totais por partida.
- Peixes capturados por raridade.
- Sets completos.
- Dano causado/recebido.
- Numero de afundamentos sofridos.
- Taxa de vitoria.
- Mar mais visitado.


## 16) Pontos para prototipo MVP

Escopo minimo jogavel (MVP):

- Lobby com 6-8 jogadores.
- 5 mares com limites.
- Movimento + disputa de vaga por combate.
- Dano ambiental.
- Pesca obrigatoria no fim de cada turno.
- Venda de peixes e pontuacao por moedas.
- 10 cartas basicas.
- Fim de jogo com ranking.

Itens para iteracao 2:

- Balanco fino de economia.
- Mais tipos de carta.
- Match history detalhado.
- Spectator mode.


## 17) Decisoes abertas para alinhar em equipe

- Numero exato de rodadas.
- Valores finais de dano por mar.
- Curva de raridade por zona.
- Quantidade inicial de cartas por jogador.
- Regra final de afundamento (respawn vs eliminacao).
- Nivel de aleatoriedade desejado (mais estrategia vs mais caos).


## 18) Nome temporario do jogo

Sugestao de codinome interno:

- Five Seas: Fisher Clash

Pode ser alterado depois sem impacto tecnico.