# ICookingRecipeManager&LT;T : AbstractCookingRecipe&GT;

Default interface for Registry based handlers as they can all remove recipes by ResourceLocation.

## Importing the class

It might be required for you to import the package if you encounter any issues (like casting an Array), so better be safe than sorry and add the import at the very top of the file.
```zenscript
import crafttweaker.api.recipe.ICookingRecipeManager;
```


## Implemented Interfaces
ICookingRecipeManager implements the following interfaces. That means all methods defined in these interfaces are also available in ICookingRecipeManager

- [IRecipeManager](/vanilla/api/recipe/manager/IRecipeManager)&lt;T&gt;

## Methods

:::group{name=addJsonRecipe}

Adds a recipe based on a provided IData. The provided IData should represent a DataPack json, this effectively allows you to register recipes for any DataPack supporting RecipeType systems.

```zenscript
// ICookingRecipeManager.addJsonRecipe(name as string, mapData as MapData)

furnace.addJsonRecipe("recipe_name", {
 ingredient: <item:minecraft:gold_ore>,
 result: <item:minecraft:cooked_porkchop>.registryName,
 experience: 0.35 as float,
 cookingtime:100
 });
```

| Parameter |                 Type                 |           Description           |
|-----------|--------------------------------------|---------------------------------|
| name      | string                               | name of the recipe              |
| mapData   | [MapData](/vanilla/api/data/MapData) | data representing the json file |


:::

:::group{name=addRecipe}

Adds a recipe based on given params.

 Note: A `cookTime` of `0` will cause the recipe to never complete, it will burn and use fuel, but no progress will be made on the recipe, it needs to be at-least `1` or more.

 Saying that, if you would like to make a recipe that will never complete
 (for example being able to give the player an infinitely burning furnace for whatever reason), you can
 still use a `cookTime` of `0`.

```zenscript
// ICookingRecipeManager.addRecipe(name as string, output as IItemStack, input as IIngredient, xp as float, cookTime as int)

furnace.addRecipe("wool2diamond", <item:minecraft:diamond>, <tag:item:minecraft:wool>, 1.0, 30);
```

| Parameter |                        Type                        |           Description           |
|-----------|----------------------------------------------------|---------------------------------|
| name      | string                                             | Name of the new recipe          |
| output    | [IItemStack](/vanilla/api/item/IItemStack)         | IItemStack output of the recipe |
| input     | [IIngredient](/vanilla/api/ingredient/IIngredient) | IIngredient input of the recipe |
| xp        | float                                              | how much xp the player gets     |
| cookTime  | int                                                | how long it takes to cook       |


:::

:::group{name=addRecipe}

Adds a recipe based on given params.

 Note: A `cookTime` of `0` will cause the recipe to never complete, it will burn and use fuel, but no progress will be made on the recipe, it needs to be at-least `1` or more.

 Saying that, if you would like to make a recipe that will never complete
 (for example being able to give the player an infinitely burning furnace for whatever reason), you can
 still use a `cookTime` of `0`.

```zenscript
// ICookingRecipeManager.addRecipe(name as string, category as CookingBookCategory, output as IItemStack, input as IIngredient, xp as float, cookTime as int)

furnace.addRecipe("wool2diamond", <constant:minecraft:cookingbookcategory:misc>, <item:minecraft:diamond>, <tag:item:minecraft:wool>, 1.0, 30);
```

| Parameter |                              Type                              |                  Description                  |
|-----------|----------------------------------------------------------------|-----------------------------------------------|
| name      | string                                                         | Name of the new recipe                        |
| category  | [CookingBookCategory](/vanilla/api/recipe/CookingBookCategory) | The category of the recipe in the recipe book |
| output    | [IItemStack](/vanilla/api/item/IItemStack)                     | IItemStack output of the recipe               |
| input     | [IIngredient](/vanilla/api/ingredient/IIngredient)             | IIngredient input of the recipe               |
| xp        | float                                                          | how much xp the player gets                   |
| cookTime  | int                                                            | how long it takes to cook                     |


:::

:::group{name=getRecipeAsJson}

Return Type: [IData](/vanilla/api/data/IData)?

```zenscript
ICookingRecipeManager.getRecipeAsJson(name as string) as IData?
```

| Parameter |  Type  |
|-----------|--------|
| name      | string |


:::

:::group{name=getRecipeByName}

Return Type: [RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;?

```zenscript
ICookingRecipeManager.getRecipeByName(name as string) as RecipeHolder<T>?
```

| Parameter |  Type  |
|-----------|--------|
| name      | string |


:::

:::group{name=getRecipeMap}

Returns a map of all known recipes.

Returns: A Map of recipe name to recipe of all known recipes.  
Return Type: [RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;[[ResourceLocation](/vanilla/api/resource/ResourceLocation)]

```zenscript
// ICookingRecipeManager.getRecipeMap() as RecipeHolder<T>[ResourceLocation]

furnace.getRecipeMap();
```

:::

:::group{name=getRecipesByOutput}

Return Type: stdlib.List&lt;[RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;&gt;

```zenscript
ICookingRecipeManager.getRecipesByOutput(output as IIngredient) as stdlib.List<RecipeHolder<T>>
```

| Parameter |                        Type                        |
|-----------|----------------------------------------------------|
| output    | [IIngredient](/vanilla/api/ingredient/IIngredient) |


:::

:::group{name=getRecipesMatching}

Return Type: stdlib.List&lt;[RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;&gt;

```zenscript
ICookingRecipeManager.getRecipesMatching(predicate as Predicate<RecipeHolder<T>>) as stdlib.List<RecipeHolder<T>>
```

| Parameter |                                    Type                                    |
|-----------|----------------------------------------------------------------------------|
| predicate | Predicate&lt;[RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;&gt; |


:::

:::group{name=remove}

Remove a recipe based on it's output.

```zenscript
// ICookingRecipeManager.remove(output as IIngredient)

furnace.remove(<tag:item:minecraft:wool>);
```

| Parameter |                        Type                        |     Description      |
|-----------|----------------------------------------------------|----------------------|
| output    | [IIngredient](/vanilla/api/ingredient/IIngredient) | output of the recipe |


:::

:::group{name=removeAll}

Remove all recipes in this registry

```zenscript
// ICookingRecipeManager.removeAll()

furnace.removeAll();
```

:::

:::group{name=removeByInput}

Removes all recipes where the input contains the given IItemStack.

```zenscript
// ICookingRecipeManager.removeByInput(input as IItemStack)

furnace.removeByInput(<item:minecraft:iron_ingot>);
```

| Parameter |                    Type                    |      Description      |
|-----------|--------------------------------------------|-----------------------|
| input     | [IItemStack](/vanilla/api/item/IItemStack) | The input IItemStack. |


:::

:::group{name=removeByModid}

Remove recipe based on Registry name modid

```zenscript
ICookingRecipeManager.removeByModid(modid as string, exclude as Predicate<string>)
```

| Parameter |          Type           |          Description           | Optional |           Default Value           |
|-----------|-------------------------|--------------------------------|----------|-----------------------------------|
| modid     | string                  | modid of the recipes to remove | false    |                                   |
| exclude   | Predicate&lt;string&gt; |                                | true     | (name as string) as bool => false |


:::

:::group{name=removeByName}

Remove recipes based on Registry names

```zenscript
ICookingRecipeManager.removeByName(names as string[])
```

| Parameter |   Type   |             Description             |
|-----------|----------|-------------------------------------|
| names     | string[] | registry names of recipes to remove |


:::

:::group{name=removeByRegex}

Remove recipe based on regex with an added exclusion check, so you can remove the whole mod besides a few specified.

```zenscript
// ICookingRecipeManager.removeByRegex(regex as string, exclude as Predicate<string>)

furnace.removeByRegex("\\d_\\d", (name as string) => {return name == "orange_wool";});
```

| Parameter |          Type           |      Description       | Optional |           Default Value           |
|-----------|-------------------------|------------------------|----------|-----------------------------------|
| regex     | string                  | regex to match against | false    |                                   |
| exclude   | Predicate&lt;string&gt; |                        | true     | (name as string) as bool => false |


:::

:::group{name=removeMatching}

Removes all recipes that match the given predicate

```zenscript
// ICookingRecipeManager.removeMatching(predicate as Predicate<RecipeHolder<T>>)

furnace.removeMatching((holder) => "wool" in holder.id.path);
```

| Parameter |                                    Type                                    |                       Description                       |
|-----------|----------------------------------------------------------------------------|---------------------------------------------------------|
| predicate | Predicate&lt;[RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;&gt; | a predicate of RecipeHolder<T> to test recipes against. |


:::

:::group{name=removeRecipe}

Removes a recipe based on it's output and input.

```zenscript
// ICookingRecipeManager.removeRecipe(output as IItemStack, input as IIngredient)

furnace.removeRecipe(<item:minecraft:diamond>, <tag:item:minecraft:wool>);
```

| Parameter |                        Type                        |             Description              |
|-----------|----------------------------------------------------|--------------------------------------|
| output    | [IItemStack](/vanilla/api/item/IItemStack)         | IItemStack output of the recipe.     |
| input     | [IIngredient](/vanilla/api/ingredient/IIngredient) | IIngredient of the recipe to remove. |


:::


## Properties

|    Name    |                                                         Type                                                          | Has Getter | Has Setter |             Description             |
|------------|-----------------------------------------------------------------------------------------------------------------------|------------|------------|-------------------------------------|
| allRecipes | stdlib.List&lt;[RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;&gt;                                          | true       | false      |                                     |
| recipeMap  | [RecipeHolder](/vanilla/api/recipe/RecipeHolder)&lt;T&gt;[[ResourceLocation](/vanilla/api/resource/ResourceLocation)] | true       | false      | Returns a map of all known recipes. |

