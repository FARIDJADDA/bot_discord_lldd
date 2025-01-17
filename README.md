# LlDd DiscordBot
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Discord.py](https://img.shields.io/badge/Framework-Discord.py-blue)
![Platform](https://img.shields.io/badge/platform-discord-blue)
![Code Quality](https://img.shields.io/badge/code%20quality-A-blue)



![Pull Requests](https://img.shields.io/badge/Contributions-Welcome-brightgreen)
![Tests](https://img.shields.io/badge/tests-passing-brightgreen)
![Dependencies](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Conventional Commits](https://img.shields.io/badge/commits-conventional-brightgreen)

![License](https://img.shields.io/badge/License-MIT-green)

![Lines of Code](https://img.shields.io/tokei/lines/github/USERNAME/REPO)
![Café](https://img.shields.io/badge/caffeine-needed-yellow)


<div align="left">
  <img src="img/llddbot_is_here.png" alt="Bot banner" width="400px">
</div>

A complete and customizable Discord bot designed to manage and engage community servers.  
This bot includes moderation tools, mini-games, advanced logging, activity statistics, and much more.

*(project under construction and only available in French version 🇫🇷)*


<div align="center">
<br>
  <img src="img/divider.png" alt="Bot banner" width="100%">
</div>

## Table of Contents

1. [Project Description](#project-description)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Project Structure](#project-structure)
5. [Available Commands](#available-commands)
6. [Adding Features](#adding-features)
7. [Contributions](#contributions)

---

## Project Description

This Discord bot offers several key features:
- **Moderation**: Commands for banning, kicking, and managing warnings.
- **Mini-games**: Gaming quizzes, dice rolls.
- **Advanced logging**: Tracks message edits/deletions and role changes.
- **Statistics**: Provides server activity data and Call of Duty stats.
- **Role assignment**: Automatically assigns roles to new members.
- **Twitch notifications**: Alerts for live streams.

---

## Requirements
📚
- **Python 3.8+**: [Download Python](https://www.python.org/downloads/)
- **Discord API Key**: Create your bot on the [Discord Developer Portal](https://discord.com/developers/applications).
- *(Optional)* Twitch and Call of Duty API keys for advanced features.

---

## Installation
🛠️
1. Clone this repository:
   ```bash
   git clone <REPO_URL>
   cd project/

    ```
   
2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
   ```
   
3. Configure your API keys

⚠️ **Important**: Never share your `.env` file containing API keys in public repositories. Make sure to add `.env` or `config` to your `.gitignore`.

Create a `config` file in the root directory:

    DISCORD_TOKEN=your_token

    LOG_FILE=bot_logs.log
    LOG_LEVEL=INFO
    LOG_BACKUP_COUNT=5
    DISCORD_LOG_LEVEL=WARNING

    TWITCH_CLIENT_ID=your_client_id
    TWITCH_CLIENT_SECRET=your_clent_secret

    COD_API_KEY=your_cod_api_key
    OPENAI_API_KEY=your-openai_api_key
    HUGGINGFACE_API_KEY=your_hugginface_api_key

    OPENWEATHER_API_KEY=your_openweather_api_key
    NEWS_API_KEY=your_news_api_key

    BLAGUES_API_TOKEN=ta_clef_blaguesapi

*Ensure all necessary API keys are added and keep this file secure.*

   
4. Run the bot:
    ```bash
   python main.py
    ```

## Project Structure
🧩
```
    project/
    ├── assets/
    ├── cogs/
    │   ├── filters.py         # Gestion des mots interdits et du spam
    │   ├── games.py           # Commandes pour les mini-jeux (quiz, lancer de dés)
    │   ├── message_log.py         # Logs des messages modifiés/supprimés et des rôles
    │   ├── moderation.py      # Commandes de modération
    │   ├── roles.py           # Attribution automatique de rôles
    │   ├── stats.py           # Commande pour les statistiques du serveur
    │   ├── twitch.py          # Notifications pour les streamers Twitch
    │   ├── warnings.py        # Gestion des avertissements
    │   ├── welcome.py         # Messages de bienvenue
    ├── data/                  # data on json
    ├── logs/                  # bot logs
    ├── utils/
    │   ├── logger.py          # Gestion des logs globaux
    ├── config                 # Clés API et secrets
    ├── main.py                # Point d'entrée principal
    ├── requirements.txt       # Dépendances nécessaires
```

## Available Commands
📜
### **Utility Commands**
* **`/status`**  
  ➡️ Displays the bot's current status (uptime, loaded cogs, etc.).  
* **`/restart`** *(Admin only)*  
  ➡️ Restarts the bot.

---

### **Moderation Commands**
* **`/ban`** @User [reason] *(Requires `ban_members` permission)*  
  ➡️ Bans a user with an optional reason.  
* **`/kick`** @User [reason] *(Requires `kick_members` permission)*  
  ➡️ Kicks a user with an optional reason.  
* **`/banned_list`**  
  ➡️ Lists all banned users in the server.


---

### **Warning Commands**
* **`/warn`** @User [reason] *(Requires `manage_messages` permission)*  
  ➡️ Warns a user for a given reason.  
* **`/warnings`** @User  
  ➡️ Displays all warnings for a user.  
* **`/clear_warnings`** @User  
  ➡️ Clears all warnings for a user.  
* **`/set_max_warnings`** <number>  
  ➡️ Sets the maximum number of warnings before applying a sanction.
<div align="left">
  <img src="img/warnings.jpg" alt="warnings preview" width="250px">
</div>

---

### **Role Commands**
* **`/set_default_roles`** role1, role2 *(Admin only)*  
  ➡️ Sets default roles to be assigned automatically to new members.  
* **`/show_default_roles`**  
  ➡️ Displays the current default roles configuration.

---

### **Mini-Game Commands**
* **`/trivia`**  
  ➡️ Starts a gaming trivia quiz using the OpenTDB API.  
* **`/my_trivia_score`**  
  ➡️ Shows the trivia leaderboard.
<div align="left">
  <img src="img/trivia.jpg" alt="trivia question and response preview" width="250px">
</div>


* **`/roll`** [faces=6]  
  ➡️ Rolls a die with the specified number of faces (default: 6).  
* **`/rps`** `@opponent [difficulty: Easy|Normal|Hard]`  
  ➡️ Play rock-paper-scissors against a bot or another player. You can set the bot's difficulty level.
<div align="left">
  <img src="img/chifoumi.jpg" alt="chifoumi preview" width="250px">
</div>

* **`morpion`** `[opponent: @user|LlddBot] [difficulty: Facile|Normale|Difficile]`
* ➡️ Start a Tic-Tac-Toe game against another user or LlddBot. Choose difficulty for bot opponents.  
<div align="left">
  <img src="img/morpion.jpg" alt="morpion preview" width="250px">
</div>

* **`/bingo start`**  
  ➡️ Start a Bingo game.
* **`/bingo stop`** 
  ➡️ End the current Bingo game.
<div align="left">
  <img src="img/bingo.jpg" alt="bingo preview" width="250px">
</div>

* **`/pendu random`**  
  ➡️ Starts a Hangman game with a randomly chosen word from the file `word_list.txt`.

* **`/pendu custom`**  
  ➡️ Starts a Hangman game where a player chooses the word via DM.

<div align="left">
  <img src="img/hangman_game.jpg" alt="hangman game preview" width="250px">
</div>

---

### **Statistics Commands**
* **`/server_stats`**  
  ➡️ Displays server statistics such as member count, roles, and channels.  
<div align="left">
  <img src="img/stats_server.jpg" alt="stats server preview" width="250px">
</div>

*(server test on picture)*

* **`/codstats`** [username] [platform]  
  ➡️ Fetches Call of Duty player stats.

---

## **Poll Commands**
The poll module allows you to create, manage, and display interactive polls directly in your Discord channels.

### **Commands**
#### **`/create_poll`**
➡️ Creates a new poll with a question and up to 15 options.

➡️ **Usage**:
  ```bash
  /create_poll question:"Your question?" options:"Option 1;Option 2;Option 3"
  ```

<div align="left">
  <img src="img/polls.jpg" alt="polls preview" width="250px">
</div>

thx to [JohnnyJayJay](https://github.com/JohnnyJayJay) for inspiration.

#### **`/poll_results`**
 ➡️ Displays the current results of an active poll in the channel.

#### **`/end_poll`**
 ➡️ Ends an active poll in the channel and displays the final results.

---

### Concours Commands

* **`/concours_creer`** `type:<argent|expérience|item|personnalisé|rôle> name:<name> winners:<number> duration:<seconds> prize:<prize>`  
  ➡️ Create a new giveaway with a specific reward.

* **`/concours_terminer`**  
  ➡️ End an ongoing giveaway and announce the winners.

* **`/concours_relancer`**  
  ➡️ Reroll the giveaway to designate a new winner.

* **`/concours_participants`**  
  ➡️ Show the list of participants in the ongoing giveaway.
<div align="left">
  <img src="img/giveaway.jpg" alt="giveaway preview" width="250px">
</div>
---

### **Hugging Face Commands**
* **`/ask_hf`** [question]  
  ➡️ Ask a question to Hugging Face models like Bloom or Falcon.
<div align="left">
  <img src="img/hf.jpg" alt="response pf hf preview" width="250px">
</div>

---

### **Welcome Commands**
* **`/set_rules_channel`** <#channel>  
  ➡️ Configures the rules channel.  
* **`/set_welcome_channel`** <channel_name>  
  ➡️ Configures the welcome channel.

---

### **ChatGPT Commands**
* **`/ask`** [question]  
  ➡️ Ask a question to ChatGPT using the OpenAI API.

---

### **Twitch Commands**
* **`/add_twitch_streamer`** [streamer_name]  
  ➡️ Add a Twitch streamer to monitor.  
* **`/list_twitch_streamers`**  
  ➡️ Display the list of monitored streamers.  
* **`/set_twitch_channel`** <#channel>  
  ➡️ Set the channel for Twitch live notifications.
<div align="left">
  <img src="img/twitch_example.jpg" alt="twitch preview" width="250px">
</div>

---

## Joke Commands
## Joke Commands
* **`/joke`**  
  ➡️ Get a random joke using the Joke API. Jokes are interactive, allowing users to reveal the punchline by clicking a button.

### JokeAPI Categories
The jokes from JokeAPI are filtered to exclude inappropriate content. Categories include:
- **Programming**
- **Miscellaneous**
- **Pun**
- **Spooky**
- **Christmas**

*No explicit, racist, or sexist jokes are allowed.*

<div align="left">
  <img src="img/joke_punchline.jpg" alt="jokes preview" width="250px">
</div>


## Commandes Blagues
* **`/blague`**  
  ➡️ Obtenez une blague aléatoire en utilisant l'API Blagues. Les blagues sont interactives et permettent aux utilisateurs de révéler la réponse en cliquant sur un bouton.

* **`/autoriser_blague <categorie>`**  
  ➡️ Configurez les catégories de blagues autorisées sur votre serveur. Activez ou désactivez des catégories telles que `Tout public`, `Humour noir`, `Développeur`, `18+`, `Beauf` ou `Blondes`.  
  Exemple : `/autoriser_blague Tout public`

### Catégories de Blagues
- **Tout public**
- **Humour noir**
- **Développeur**
- **18+**
- **Beauf**
- **Blondes**

<div align="left">
  <img src="img/blague.jpg" alt="blague preview" width="250px">
</div>
<div align="left">
  <img src="img/blague_reponse.jpg" alt="blague réponse preview" width="250px">
</div>


---

### Others API:
* **`/weather`** `<city>`
  ➡️ Displays the current weather for a specified city.

* **`/news`**
  ➡️ Shows the latest gaming news.
<div align="left">
  <img src="img/meteo.jpg" alt="weather preview" width="250px">
</div>

<div align="left">
  <img src="img/actus_gaming.jpg" alt="news gaming preview" width="250px">
</div>

---

### **🚀 Recent Updates**
- **Hugging Face integration** for NLP models like Bloom and Falcon.
- **Improved polling system**: Dynamic timers and automatic results display.
- **ChatGPT refactor**: Compatibility with OpenAI v1.0.0.
- **Structured JSON Handling**: Moved all JSON files to the `/data/` directory with auto-creation and validation.
- **Improved Logging**: Added advanced log checks and detailed errors.
- **Trivia Game**: Integrated with **OpenTDB API** for gaming-related questions.
- **Leaderboard**: New command `/leaderboard` to view trivia scores.
- **RPS Mini-Game**: Added `/rps` (rock-paper-scissors) game.
- **Automatic Role Assignment**: Default roles are now assigned to new members.
- **Enhanced Moderation**: Improved `/warn` and warning clearing logic.
- **Twitch Integration**: Added live notifications with `/set_twitch_channel` and `/add_twitch_streamer`.
- **Performance Optimization**: Refactored cogs for modularity and scalability.

---

### **Étapes pour tester**
1. **Lance ton bot et utilise les commandes listées.**
2. Assure-toi que chaque fonctionnalité répond correctement et affiche les informations dans des embeds cohérents.


---

## Exemple de Commandes Avancées
🛠️
### Modération :
 ```
/ban @Player1 Comportement inapproprié /kick @Player2 Inactivité prolongée
 ```

### Mini-Jeux :
 ```
 /quiz /roll 20
 ```

## Adding Features
🔧
### Create a New Command :
1. **Create a file in the `cogs/` folder**  
   Example : `my_feature.py`.

2. **Add a class with hybrid or slash commands :**  
   Example ofhybride command :
   ```python
   from discord.ext import commands

   class MyFeature(commands.Cog):
       def __init__(self, bot):
           self.bot = bot

       @commands.hybrid_command(name="ma_commande", description="Ma nouvelle commande")
       async def ma_commande(self, ctx):
           if isinstance(ctx, discord.Interaction):
               await ctx.response.send_message("Ceci est une nouvelle commande Slash !")
           else:
               await ctx.send("Ceci est une nouvelle commande classique !")
   ```
   
3. **Add a `setup` function to integrate the cog.**
   ```python
   async def setup(bot):
       await bot.add_cog(MyFeature(bot))
   ```
   
4. **Reload or restart the bot to apply the changes.**
   ```
   !reload_cog cogs.my_feature
   ```


<div align="center">
<br>
  <img src="img/divider.png" alt="Bot banner" width="100%">
</div>

## Contributions
🤝
Contributions are welcome! To contribute:

1. Fork this repository.
2. Create a branch for your feature (e.g., `feat/ajout-sondage`).
3. Test your changes locally.
4. Open a pull request with detailed explanations.

### ☑️ Pull Request Checklist: :
- [ ] Added a feature or bug fix.
- [ ] Tested locally to avoid regressions.
- [ ] Updated documentation if necessary.

## ⚖️ Licence

This project is licensed under the **MIT License**. You are free to use, modify, and distribute it.
See the [LICENSE](bot/LICENSE) file for more details.


⭐ If you like this project, consider giving it a star! ⭐
