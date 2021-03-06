# PlayerInteract

The PlayerInteract Event is fired whenever a player interacts with a block.

## Класс события

You will need to cast the event in the function header as this class:  
`crafttweaker.event.PlayerInteractEvent`  
You can, of course, also [import](/AdvancedFunctions/Import/) the class before and use that name then.

## Наследование от интерфейсов событий

PlayerInteract Events implement the following interfaces and are able to call all of their methods/getters/setters as well:

- [IEventCancelable](/Vanilla/Events/Events/IEventCancelable/)
- [IPlayerEvent](/Vanilla/Events/Events/IPlayerEvent/)
- [IEventPositionable](/Vanilla/Events/Events/IEventPositionable/)

## ZenGetters

Следующая информация может быть получена от события:

| ZenGetter    | Возвращаемый тип                     |
| ------------ | ------------------------------------ |
| `canceled`   | boolean                              |
| `usingItem`  | boolean                              |
| `usingBlock` | boolean                              |
| `x`          | int                                  |
| `y`          | int                                  |
| `z`          | int                                  |
| `player`     | [IPlayer](/Vanilla/Players/IPlayer/) |
| `world`      | [IWorld](/Vanilla/World/IWorld/)     |
| `block`      | [IBlock](/Vanilla/Blocks/IBlock/)    |
| `dimension`  | int                                  |

## ZenMethods

- `event.cancel()` sets the event as cancelled
- `event.useBlock()` sets Block to true
- `event.useItem()` sets Item to true