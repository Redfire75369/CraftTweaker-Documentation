# MaterialPartLocalizedNameSupplier

You can create a MaterialPartLocalizedNameSupplier form a [MaterialPart](/Mods/ContentTweaker/Materials/Materials/MaterialPart/) object, which will then be used whenever requested.

## Diese Klasse importieren

Should you need to import he class, here you go:

```zenscript
import mods.contenttweaker.MaterialPartLocalizedNameSupplier;
```

## Static methods

Static methods can be called upon the package, not upon instances of the class.

```zenscript
//mods.contenttweaker.MaterialPartLocalizedNameSupplier.create(IMaterialPart materialPart);
mods.contenttweaker.MaterialPartLocalizedNameSupplier.create(myMaterialPart);
```