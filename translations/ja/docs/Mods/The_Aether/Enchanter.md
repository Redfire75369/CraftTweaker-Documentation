# Enchanter

## Package

```zenscript
import mods.aether_legacy.Enchanter;Enchanter;
```
## Usage

```zenscript
Enchanter.registerEnchantment(IItemStack input, IItemStack output, int timeRequired);
// repairing tools and stuff
Enchanter.registerEnchantment(IItemStack repair, int timeRequired);
Enchanter.registerEnchanterFuel(IItemStack input, int timeGiven);
```