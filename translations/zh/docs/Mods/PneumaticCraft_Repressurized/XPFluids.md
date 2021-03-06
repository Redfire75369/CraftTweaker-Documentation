# XP Fluids

XP Fluids are used in PneumaticCraft: Repressurized by the Aerial Interface, a powerful block which can remotely interface with a linked player. XP Fluids pumped into the Aerial Interface are converted to player experience levels, and XP Fluids pumped out are drawn from the player's experience.

By default, the following fluids are recognized by the Aerial Interface:

* XP Juice (EnderIO, Cyclic, Openblocks)
* Essence of Knowledge (Thermal Expansion)
* Mob Essence (Industrial Foregoing)

This package allows arbitrary other fluids to be used by the Aerial Interface as XP fluids, or for existing XP fluids to be deregistered.

## 导入包

You can call the XP Fluids package using `mods.pneumaticcraft.xpfluid`.

## 移除配方

This function deregisters the [ILiquidStack](/Vanilla/Liquids/ILiquidStack/) `fluid`:

```zenscript
mods.pneumaticcraft.xpfluid.removeXPFluid(ILiquidStack fluid);
// Example
mods.pneumaticcraft.xpfluid.removeXPFluid(<liquid:xpjuice>);
```

This function deregisters *all* known XP fluids:

```zenscript
mods.pneumaticcraft.xpfluid.removeAllXPFluids();
```

## 添加

This function can be used to register fluids as XP fluids:

```zenscript
// Register a liquid as an XP fluid. xpRatio defines the amount of player XP per millibucket of fluid.
mods.pneumaticcraft.xpfluid.addXPFluid(ILiquidStack fluid, double ratio);

// Example: register LPG as an XP fluid worth 10 XP per mB
mods.pneumaticcraft.xpfluid.addXPFluid(<liquid:lpg>, 10);
```