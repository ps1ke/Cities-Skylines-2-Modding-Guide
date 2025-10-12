# Game.UI.InGame.LevelSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_SpawnableBuildingQuery`  
- `private Unity.Entities.EntityQuery m_CityQuery`  
- `private System.Int32 <level>k__BackingField`  
- `private System.Int32 <maxLevel>k__BackingField`  
- `private System.Boolean <isUnderConstruction>k__BackingField`  
- `private System.Single <progress>k__BackingField`  
- `private Unity.Entities.Entity <zone>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Int32> m_Result`  
- `private Game.UI.InGame.LevelSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 level { private get; private set }`  
- `private System.Int32 maxLevel { private get; private set }`  
- `private System.Boolean isUnderConstruction { private get; private set }`  
- `private System.Single progress { private get; private set }`  
- `private Unity.Entities.Entity zone { private get; private set }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  

## Constructors

- `public LevelSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.LevelSection+CalculateMaxLevelJob`  
- `Game.UI.InGame.LevelSection+TypeHandle`  

