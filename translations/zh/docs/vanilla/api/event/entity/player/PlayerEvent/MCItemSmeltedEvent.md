# MCItemSmeltedEvent

这个类由mod-id为`crafttweaker`的模组添加. 因此，如果要使用此功能，则需要安装此mod。

## 导入相关包
如果遇到任何问题（例如强制转换数组），则可能需要导入软件包，因此，最好的方式就是导入包支持。
```zenscript
crafttweaker.api.event.entity.player.PlayerEvent.MCItemSmeltedEvent
```

## Constructor #构造函数
```zenscript
new crafttweaker.api.event.entity.player.PlayerEvent.MCItemSmeltedEvent(handler as function.Consumer<crafttweaker.api.event.entity.player.PlayerEvent.MCItemSmeltedEvent>);
```
| 参数      | 类型                                                                                                                                                        | 描述                      |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| handler | function.Consumer<[crafttweaker.api.event.entity.player.PlayerEvent.MCItemSmeltedEvent](/vanilla/api/event/entity/player/PlayerEvent/MCItemSmeltedEvent)> | No description provided |



## 方法
### getEntityPlayer

Returns [crafttweaker.api.entity.player.MCPlayerEntity](/vanilla/api/entity/player/MCPlayerEntity)

```zenscript
myMCItemSmeltedEvent.getEntityPlayer();
```

### getPlayer

Returns: `Player`

Returns [crafttweaker.api.entity.player.MCPlayerEntity](/vanilla/api/entity/player/MCPlayerEntity)

```zenscript
myMCItemSmeltedEvent.getPlayer();
```

### getSmelting

Returns [crafttweaker.api.item.IItemStack](/vanilla/api/items/IItemStack)

```zenscript
myMCItemSmeltedEvent.getSmelting();
```

### hasResult

Determines if this event expects a significant result value. Note: Events with the HasResult annotation will have this method automatically added to return true.

返回为布尔值

```zenscript
myMCItemSmeltedEvent.hasResult();
```

### isCancelable

Determine if this function is cancelable at all. Returns: `If access to setCanceled should be allowed
 Note:
 Events with the Cancelable annotation will have this method automatically added to return true.`

返回为布尔值

```zenscript
myMCItemSmeltedEvent.isCancelable();
```

### isCanceled

Determine if this event is canceled and should stop executing. Returns: `The current canceled state`

返回为布尔值

```zenscript
myMCItemSmeltedEvent.isCanceled();
```

### setCanceled

```zenscript
myMCItemSmeltedEvent.setCanceled(cancel as boolean);
```

| 参数     | 类型      | 描述                      |
| ------ | ------- | ----------------------- |
| cancel | boolean | No description provided |


