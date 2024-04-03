This is a comprehensive list of supported addons, integrations as well as other bits of content relating to Farmer's Delight Fabric or Refabricated.

The provided links through the mod names will be the Modrinth pages for each individual mod, or the CurseForge page if there is no Modrinth page.

`*` means that Refabricated partially supports it through its compat layer. This may be because of mixins into the other codebase, or other bits.

# Addons
|Mod Name|Farmer's Delight Fabric|Farmer's Delight Refabricated|Extra Information|
|---|---|---|---|
|[Crate Delight](https://modrinth.com/mod/crate-delight) | Always | Always |
|[Chef's Delight](https://modrinth.com/mod/chefs-delight)|Always|Supported through compat layer|
|[End's Delight](https://modrinth.com/mod/ends-delight/)|Has specific FDF versions|Has specific FDRF versions|
|[Fabric Seasons: Delight Compat](https://modrinth.com/mod/fabric-seasons-delight-compat)|Always|Supported through compat layer `*`|The developer has been contacted, but has not responded.|
|[Farmer's Knives](https://modrinth.com/mod/farmers-knives)|Always|Supported through compat layer|
|[Fright's Delight](https://modrinth.com/mod/frights-delight/version/fabric-1.20.1-1.0.2)|Always|As of 1.0.2|
|[More Delight](https://modrinth.com/mod/more-delight)|Always|Supported through compat layer| 
|[Nether's Delight (Fabric)](https://legacy.curseforge.com/minecraft/mc-mods/nethers-delight-fabric/)|Always|Supported through compat layer|
|[Expanded Delight](https://modrinth.com/mod/expanded-delight)|Always|Supported through compat layer|
|[Ocean's Delight](https://modrinth.com/mod/oceans-delight)|Has specific FDF version|Has specific FDRF versions|

# Integrations
|Mod Name|Farmer's Delight Fabric|Farmer's Delight Refabricated|
|---|---|---|
|[Every Compat (Wood Good)](https://modrinth.com/mod/supplementaries/)|Prior to 2.6.40|Since 2.6.40|
|[Fruitful Fun](https://modrinth.com/mod/fruitful-fun)|Always|Since 7.3.1|
|[Hearty Meals](https://modrinth.com/mod/hearty-meals/)|Always|Since 1.20-6|
|[Supplementaries](https://modrinth.com/mod/supplementaries/)|Prior to 2.8.8|Since 2.8.8|

# Planned
## Addons
- [Autochef's Delight](https://modrinth.com/mod/autochefs-delight)
    - I think they're working on it? There are branches for `fabric` and `nhoryzon`. Please correct me if I am wrong.
- [Create Central Kitchen](https://modrinth.com/mod/create-central-kitchen/)
    - Was blocked by the class structure being different, now wants to multiloader the mod.
- [Brewin' And Chewin' (Fabric)](https://modrinth.com/mod/brewin-and-chewin-fabric)
    - Dev will get to it, MrSterner_ has just been busy.
- [Farmer's Respite (Fabric)](https://modrinth.com/mod/farmers-respite-fabric)
    - Same as Brewin' And Chewin' (Fabric)
- [Cultural Delights (Fabric)](https://modrinth.com/mod/cultural-delights-fabric)
    - Same as Brewin' And Chewin' (Fabric)

# Flaked
These mods have authors that are either not present, or have not responded to anybody regarding their stance on Farmer's Delight Refabricated support.
## Addons
- [Cake Delight](https://modrinth.com/mod/cakedelight)
- [Casualness Delight](https://modrinth.com/mod/casualness-delight)
    - [Linked Issue](https://github.com/TsukimiRen/Casualness-Delight/issues/11)
- [Coffee Delight](https://modrinth.com/mod/coffee-delight)
- [Corn Delight [Fabric/Quilt]](https://legacy.curseforge.com/minecraft/mc-mods/corn-delight-fabric)
- [Create: Food](https://modrinth.com/mod/create-food/)
- [Create's Delight](https://modrinth.com/mod/creates-delight)
- [Cultural Creators](https://legacy.curseforge.com/minecraft/mc-mods/cultural-creators-fabric-create-and-cultural/)
- [Delightful Creators](https://modrinth.com/mod/delightful-creators-fabric/)
- [Kebab's Delight](https://legacy.curseforge.com/minecraft/mc-mods/kebabs-delight)
- [Respite Creators](https://modrinth.com/mod/respite-creators-fabric)
- [Shakshuka Delight](https://modrinth.com/mod/shakshuka-delight)
- [Ube's Delight](https://modrinth.com/mod/ubes-delight)

# Unsupported
Please do not harass anybody for their decision to not port their codebase over to Farmer's Delight Refabricated.
- Nobody!

# Invalid
These mods are considered unnecessary to port, because their functionality is included in Refabricated, please do not ask these devs to support Refabricated, at most, they can update their dependency block to make sure that it's not Refabricated, or use the version check mentioned below.
## Addons
- [Just Enough Farmer's Recipes](https://legacy.curseforge.com/minecraft/mc-mods/farmers-delight-jei-plugin)
- [Recipe Book Delight](https://modrinth.com/mod/recipe-book-delight)
## Integrations
- [EMI Addon: Extra Mod Integrations](https://modrinth.com/mod/extra-mod-integrations)

# Checking Which Farmer's Delight Fabric Port You Have.
As of 1.20.1-2.0.13+refabricated, you are able to check which version of Farmer's Delight you have by utilising a version check like so.

This is the safest way to do so, because codebase changes to Refabricated or Fabric will not be affected.

You can do whatever with this, you can crash the client, you can disable/enable certain things, whatever floats your boat...
```java
public static boolean isFDRefabricated() {
    // Use Objects#equals to make sure it's null safe for Farmer's Delight Fabric, which should not contain a +.
    return FabricLoader.getInstance().getModContainer("farmersdelight").map(container -> Objects.equals(container.getMetadata().getVersion().getFriendlyString().split("\\+")[1], "refabricated")).orElse(false);
}
```