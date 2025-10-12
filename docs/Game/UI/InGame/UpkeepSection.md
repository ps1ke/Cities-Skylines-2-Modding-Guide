# Game.UI.InGame.UpkeepSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField`  
- `private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField`  
- `private System.Int32 <total>k__BackingField`  
- `private System.Boolean <inactive>k__BackingField`  
- `private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set }`  
- `private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set }`  
- `private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set }`  
- `private System.Int32 total { private get; private set }`  
- `private System.Boolean inactive { private get; private set }`  
- `protected System.Boolean displayForUpgrades { protected get }`  

## Constructors

- `public UpkeepSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CalculateServiceUpkeepDatas(Unity.Entities.Entity entity, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity buildingOwnerEntity, Unity.Entities.DynamicBuffer<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, System.Boolean inactiveBuilding, System.Boolean inactiveUpgrade) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.UpkeepSection+UIUpkeepItem`  
- `Game.UI.InGame.UpkeepSection+TypeHandle`  

