# PlayerlyAPI
request anything that should be implemented **OR** fixed in PlayerlyAPI
# Todo-List
- [X] Auth-System [BETA]
- [X] Ban-System [BETA] [NEW]
- [X] Mute-System
- [X] StatsAPI
- [ ] Level-System
- [ ] Rank-System
- [X] Coins-System [BETA] [NEW]
- [ ] Points-System
- [ ] Friends-System
- [ ] Guild-System
- [ ] Clan-System
- [ ] Party-System
- [ ] Credits-System [GOES WITH Tiers-System]
- [ ] Tiers-System [GOES WITH Credits-System]
- [ ] Souls-System
- [X] Mysql
# Config
enter the mysql data in config.yml
# How to Use the api
Get & Set
```php
// to get or set something thats already in the api easily by

use Toxic\Statics\Stats;

public Stats $stats;

$stats = $this->getServer()->getPluginManager()->getPlugin("PlayerlyAPI")

$this->stats->getKills($player); // $player
$this->stats->setWins($player, 1); // $player & an number/int/integar

```
Add & Remove
```php
$this->stats->getDataBase()->addKill($player); // $player, only adds 1 kill
$this->stats->getDataBase()->addKills($player, 5); // $player, add any amount of kills
$this->stats->getDataBase()->removeWins($player, 1); // $player & an number/int/integar
```

Website
```php
include "config.php"; // where the database connection is (seperated from main)
// NOTE: that some things in this code you will have to handle your self (such as the $username)
$result = mysqli_query($conn, "SELECT * FROM stats WHERE username='$username'"); // $username must be handled by you & $conn is in the config.php
// check for query execution errors
if (!$result) {
     echo "Error executing query: " . mysqli_error($conn);
     exit();
}

while($row = mysqli_fetch_assoc($result)){
echo " - Name: " . $row["username"]. "<br>" ." - Kills: " . $row["kills"]. "<br>" . "- Wins:" . $row["wins"]. "<br>" . "- Deaths:" . $row["deaths"]. "<br>";
}
mysqli_close($conn);

?>
```
# Tests
**SOON

**SOON
