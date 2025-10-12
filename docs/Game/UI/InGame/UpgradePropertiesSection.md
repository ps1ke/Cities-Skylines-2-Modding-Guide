# Game.UI.InGame.UpgradePropertiesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.Entity <mainBuilding>k__BackingField`  
- `private Unity.Entities.Entity <upgrade>k__BackingField`  
- `private Game.UI.InGame.UpgradePropertiesSection+UpgradeType <type>k__BackingField`  
- `private static readonly System.String kMainBuildingName`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  
- `private Unity.Entities.Entity mainBuilding { private get; private set }`  
- `private Unity.Entities.Entity upgrade { private get; private set }`  
- `private Game.UI.InGame.UpgradePropertiesSection+UpgradeType type { private get; private set }`  

## Constructors

- `public UpgradePropertiesSection()`  

## Methods

- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.UpgradePropertiesSection+UpgradeType`  

