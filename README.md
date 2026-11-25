# FriendSlop — Caçapa Russa

**Russian-roulette pool.** A first-person multiplayer party game made in Unity where every shot at the table comes with a revolver, a death risk and friends trying to sabotage you.

<p align="center">
  <img src="Docs/screenshots/shot.png" alt="Taking a shot: aim, power and spin HUD with the player list and revolver risk" width="100%">
</p>

[🇧🇷 Leia em português](#-português)

## The game

Players (humans and bots) take turns at a pool table inside an industrial arena. Each turn you aim, pull the cue back and shoot, while a **revolver** tracks your individual death risk. Pocketing balls earns coins; coins buy **Chaos**: sabotages and effects you throw at other players. When the round ends, the winner puts on the top hat and the room switches to free mode: everyone runs from the winner, and one shot knocks you down for a second.

| | |
| :---: | :---: |
| <img src="Docs/screenshots/wheel.png" alt="The wheel of fate with a DEATH slice" width="100%"> | <img src="Docs/screenshots/trigger.png" alt="A player holding the revolver to their head" width="100%"> |
| **The wheel:** fate decides what happens next | **The trigger:** every turn has a price |
| <img src="Docs/screenshots/arena.png" alt="The industrial arena" width="100%"> | <img src="Docs/screenshots/jukebox.png" alt="The shared jukebox" width="100%"> |
| **The arena:** props, vending machines and stands | **The jukebox:** the whole room listens to the same YouTube queue |

## Features

- **Real pool physics:** deterministic 2D simulation with time-of-impact collisions, friction, restitution and spin; accurate aim prediction (a cone instead of a line when a debuff makes it inaccurate).
- **Shot control:** mouse aim and pull-back power, horizontal aim adjustment while pulling, spin with **W/A/S/D** (diagonals included, **C** resets), fine mode and top-down view.
- **Multiplayer:** LAN or online through Unity Relay (Netcode for GameObjects), host-authoritative simulation, client reconnection that keeps your seat and balance, and bots to fill the table (minimum of 2 participants).
- **Chaos and sabotage:** server-confirmed purchases with per-target prices; effects such as Tunnel Vision, Myopia (depth-of-field blur) and Color Blindness (deuteranopia), each lasting three shots.
- **Characters:** toy-like customizable characters with square, round or triangular heads, outfits, glasses and hats (including a straw hat with a red band), emotes and chat.
- **Shared jukebox:** the official YouTube page inside an embedded browser, with a room-wide queue synced by server time.
- **Tested:** EditMode and PlayMode suites (139 tests in the last full round), runtime probes and end-to-end network matches with identical results on host and client.

## Tech

Unity 6 (6000.7.0b2) · C# · URP · Netcode for GameObjects · Unity Relay · Input System · WebView2 (YouTube jukebox) · Blender for models · Git LFS for binary assets

## Opening the project

1. Install [Git LFS](https://git-lfs.com/) and run `git lfs install`.
2. Clone the repository and run `git lfs pull` inside it if needed. On Windows, enable long paths (`git config --global core.longpaths true`), because some third-party plugin paths are very deep.
3. In Unity Hub, add the repository folder and open it with **Unity 6000.7.0b2**. The first import resolves packages and can take a while; it needs internet access.
4. Open `Assets/_Project/Scenes/Game.unity` and press Play.

To run the tests, open **Window > General > Test Runner** and choose EditMode or PlayMode. Build scenes are listed in Build Settings.

## Controls

**WASD** move · **mouse** look · **E** interact / pick up the cue · **click and pull back** to shoot · **Shift** fine aim · **Tab** top-down view while shooting / scoreboard and rematch in free mode · **1–4** emotes · **T** chat · **G** shoot (free mode) · **Esc** menu · **F1** hide HUD

## Project layout

- `Assets/_Project/`: scenes, code, resources and tests.
- `Packages/` and `ProjectSettings/`: Unity dependencies and settings.
- `Blender/`: model production tools and materials.
- `Docs/`: design decisions, technical notes, patch notes and these screenshots.

Unity-generated files, local builds and caches aren't versioned. Binary assets use Git LFS as set in `.gitattributes`. Some packages are fetched from the internet; check third-party dependencies and their licenses before redistributing the game.

## Known limitations

The match authority stays with the host: if the host leaves for good, the match ends (clients can rejoin, but there's no host migration). The cue stroke animation is still being polished.

---

## 🇧🇷 Português

# FriendSlop — Caçapa Russa

**Sinuca com roleta-russa.** Um party game multiplayer em primeira pessoa feito em Unity, em que cada tacada vem acompanhada de um revólver, um risco de morte e amigos tentando te sabotar.

### O jogo

Jogadores (humanos e bots) se revezam numa mesa de sinuca dentro de uma arena industrial. A cada vez, você mira, puxa o taco e dá a tacada, enquanto um **revólver** acompanha o seu risco individual de morte. Encaçapar bolas rende moedas; moedas compram **Caos**: sabotagens e efeitos que você joga nos outros. Quando a ronda acaba, o vencedor ganha a cartola e a sala entra no modo livre: todo mundo foge do vencedor, e um tiro deixa você no chão por um segundo.

Os prints acima mostram a tacada com a HUD de mira, força e efeito; a **roleta** do destino, com a fatia de MORTE; o **gatilho**, porque toda vez tem um preço; a **arena**, com máquinas e arquibancadas; e a **jukebox**, em que a sala toda ouve a mesma fila do YouTube.

### Recursos

- **Física de sinuca de verdade:** simulação 2D determinística com colisões por tempo de impacto, atrito, restituição e efeito; previsão de mira precisa (um cone em vez de uma linha quando um debuff a torna imprecisa).
- **Controle da tacada:** mira e força pelo mouse, ajuste horizontal da mira enquanto puxa o taco, efeito com **W/A/S/D** (com diagonais, **C** zera), modo fino e visão de cima.
- **Multiplayer:** LAN ou online pelo Unity Relay (Netcode for GameObjects), simulação com autoridade do anfitrião, reconexão do cliente preservando lugar e saldo, e bots para completar a mesa (mínimo de 2 participantes).
- **Caos e sabotagem:** compras confirmadas pelo servidor, com preço por alvo; efeitos como Visão de Túnel, Miopia (desfoque por profundidade) e Daltonismo (deuteranopia), cada um durando três tacadas.
- **Personagens:** bonecos personalizáveis com cabeça quadrada, redonda ou triangular, roupas, óculos e chapéus (incluindo o chapéu de palha com faixa vermelha), emotes e chat.
- **Jukebox compartilhada:** a página oficial do YouTube num navegador embutido, com fila da sala sincronizada pelo horário do servidor.
- **Testado:** suítes EditMode e PlayMode (139 testes na última rodada completa), probes em runtime e partidas de rede de ponta a ponta com resultado idêntico no anfitrião e no cliente.

### Tecnologias

Unity 6 (6000.7.0b2), C#, URP, Netcode for GameObjects, Unity Relay, Input System, WebView2 (jukebox do YouTube), Blender para os modelos e Git LFS para os assets binários.

### Abrir o projeto

1. Instale o [Git LFS](https://git-lfs.com/) e execute `git lfs install`.
2. Clone o repositório e, se necessário, execute `git lfs pull` na pasta clonada. No Windows, ative caminhos longos (`git config --global core.longpaths true`), porque alguns plugins de terceiros têm caminhos muito profundos.
3. No Unity Hub, adicione a pasta e abra com **Unity 6000.7.0b2**. A primeira abertura importa os assets e resolve os pacotes; pode demorar e precisa de internet.
4. Abra `Assets/_Project/Scenes/Game.unity` e pressione Play.

Para os testes, abra **Window > General > Test Runner** e escolha EditMode ou PlayMode. As cenas da build estão em Build Settings.

### Controles

**WASD** anda · **mouse** olha · **E** interage / pega o taco · **clique e puxe** para tacar · **Shift** mira fina · **Tab** visão de cima na tacada / placar e revanche no modo livre · **1–4** emotes · **T** chat · **G** atira (modo livre) · **Esc** menu · **F1** esconde a HUD

### Organização

- `Assets/_Project/`: cenas, código, recursos e testes.
- `Packages/` e `ProjectSettings/`: dependências e configurações do Unity.
- `Blender/`: ferramentas e materiais de produção dos modelos.
- `Docs/`: decisões de design, notas técnicas, patch notes e estes prints.

Arquivos gerados pelo Unity, builds locais e caches não são versionados. Assets binários usam Git LFS conforme o `.gitattributes`. Alguns pacotes vêm da internet; confira as dependências de terceiros e suas licenças antes de redistribuir o jogo.

### Limitações conhecidas

A autoridade da partida fica com o anfitrião: se ele sair de vez, a partida acaba (os clientes podem voltar, mas não há migração de host). A animação da tacada ainda está sendo refinada.
