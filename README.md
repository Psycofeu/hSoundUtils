# hSoundUtils

Une librairie (virion) qui ajoute une énumération complète des sons disponibles
dans **Minecraft Bedrock / Pocket Edition**, directement utilisable avec PocketMine-MP.

Elle fournit un enum `SoundListEnum` qui contient tous les noms de sons valides
et une méthode pratique `sendTo()` pour envoyer un son à un joueur.

---

## ✨ Exemple d’utilisation

```php
SoundListEnum::BEACON_ACTIVATE->sendTo($player, volume: 2, pitch: 0.8);
```

```php
use hSoundUtils\Psycofeu\enum\SoundListEnum;
use pocketmine\player\Player;
use pocketmine\event\player\PlayerJoinEvent;

class MyPlugin extends PluginBase implements Listener {

    public function onEnable(): void {
        $this->getServer()->getPluginManager()->registerEvents($this, $this);
    }

    public function playerJoinEvent(PlayerJoinEvent $event): void {
        SoundListEnum::RANDOM_POP->sendTo($event->getPlayer(), volume: 1, pitch: 1.0);
    }
}
```
