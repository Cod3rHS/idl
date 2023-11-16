<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fighting Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
  </style>
</head>
<body>

  <h1>Fighting Game</h1>
  <p>Choose your opponent:</p>
  <select id="opponentSelect">
    <option value="goblin">Goblin</option>
    <option value="skeleton">Skeleton</option>
    <option value="dragon">Dragon</option>
  </select>

  <button onclick="startGame()">Start Game</button>

  <div id="battleLog"></div>

  <script>
    function startGame() {
      var player = {
        name: "Player",
        health: 100,
        attack: 10
      };

      var opponentType = document.getElementById("opponentSelect").value;
      var opponent = createOpponent(opponentType);

      document.getElementById("battleLog").innerHTML = '';

      while (player.health > 0 && opponent.health > 0) {
        playerAttack(player, opponent);
        if (opponent.health <= 0) {
          logMessage(player.name + " defeated " + opponent.name + "!");
          break;
        }

        opponentAttack(player, opponent);
        if (player.health <= 0) {
          logMessage(player.name + " was defeated by " + opponent.name + ".");
          break;
        }
      }
    }

    function createOpponent(type) {
      var opponent;
      switch (type) {
        case "goblin":
          opponent = { name: "Goblin", health: 30, attack: 5 };
          break;
        case "skeleton":
          opponent = { name: "Skeleton", health: 40, attack: 8 };
          break;
        case "dragon":
          opponent = { name: "Dragon", health: 50, attack: 12 };
          break;
        default:
          opponent = { name: "Unknown", health: 0, attack: 0 };
      }
      return opponent;
    }

    function playerAttack(player, opponent) {
      var damage = Math.floor(Math.random() * player.attack) + 1;
      opponent.health -= damage;
      logMessage(player.name + " attacked " + opponent.name + " for " + damage + " damage.");
    }

    function opponentAttack(player, opponent) {
      var damage = Math.floor(Math.random() * opponent.attack) + 1;
      player.health -= damage;
      logMessage(opponent.name + " attacked " + player.name + " for " + damage + " damage.");
    }

    function logMessage(message) {
      var logElement = document.getElementById("battleLog");
      logElement.innerHTML += "<p>" + message + "</p>";
    }
  </script>

</body>
</html>
