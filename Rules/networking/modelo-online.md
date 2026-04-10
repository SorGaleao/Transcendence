# Modelo Online

## Abordagem

O jogo deve ser server-authoritative: o servidor valida as acoes e define o estado oficial da partida.

## Responsabilidades

### Servidor

- validar movimento;
- resolver perigo e pesca;
- aplicar dano;
- controlar cartas e mercado;
- publicar eventos para todos os clientes.

### Cliente

- enviar intencao do jogador;
- exibir estado da partida;
- reagir aos eventos recebidos.

## Eventos sugeridos

- lobby:update
- game:start
- turn:begin
- player:move
- hazard:result
- fishing:result
- market:sell
- card:played
- player:sunk
- game:end

## Ideia complementar

Como o jogo tem rodadas curtas, o sistema de rede deve priorizar resposta rapida e reconexao simples. Isso evita que uma queda de conexao destrua a experiencia da partida.