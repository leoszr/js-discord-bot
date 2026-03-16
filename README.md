# Call of Cthulhu Discord Bot

Bot para Discord focado em sessões de RPG de **Call of Cthulhu**. Inclui rolagem de dados, verificação de habilidades, tabelas aleatórias, gerenciamento de personagens e controle de sessões — tudo via comandos no chat.

## Tecnologias

- Node.js
- discord.js v14
- dotenv

## Pré-requisitos

- Node.js 18+
- Bot criado no [Discord Developer Portal](https://discord.com/developers/applications) com token gerado

## Instalação

1. Instale as dependências:

```bash
npm install
```

2. Crie o arquivo `.env` na raiz do projeto:

```env
DISCORD_TOKEN=seu_token_aqui
```

## Como executar

```bash
npm start
```

O bot ficará online e exibirá a mensagem de login no terminal.

## Comandos disponíveis

### Rolagem de dados

| Comando                     | Descrição                                       | Exemplo           |
| --------------------------- | ----------------------------------------------- | ----------------- |
| `!roll d100`                | Rola 1d100                                      | `!roll d100`      |
| `!roll NdN`                 | Rola N dados de N lados, exibe parciais e total | `!roll 3d6`       |
| `!check <habilidade> [mod]` | Teste de habilidade contra porcentagem (1d100)  | `!check 65 5`     |
| `!table <tabela>`           | Rola em uma tabela aleatória                    | `!table insanity` |

**Tabelas disponíveis:** `insanity`, `encounter`

### Personagens

| Comando                              | Descrição                           |
| ------------------------------------ | ----------------------------------- |
| `!createchar <nome>`                 | Cria um novo personagem             |
| `!setstat <nome> <atributo> <valor>` | Define um atributo do personagem    |
| `!showchar <nome>`                   | Exibe os atributos de um personagem |

### Sessões

| Comando                    | Descrição                            |
| -------------------------- | ------------------------------------ |
| `!newsession <nome>`       | Cria uma nova sessão                 |
| `!addnote <sessão> <nota>` | Adiciona uma nota à sessão           |
| `!listsessions`            | Lista todas as sessões               |
| `!showsession <nome>`      | Exibe detalhes e notas de uma sessão |

## Persistência

Os dados de personagens e sessões são armazenados em arquivos JSON locais:

- `characters.json` — personagens e atributos
- `sessions.json` — sessões e notas

## Observações

- Habilite os intents `GUILDS`, `GUILD_MESSAGES` e `MESSAGE_CONTENT` no painel do desenvolvedor Discord.
- As tabelas aleatórias podem ser expandidas editando `tables.js`.
