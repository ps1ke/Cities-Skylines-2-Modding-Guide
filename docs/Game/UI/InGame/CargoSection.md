# Game.UI.InGame.CargoSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <cargo>k__BackingField`  
- `private System.Int32 <capacity>k__BackingField`  
- `private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField`  
- `private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 cargo { private get; private set }`  
- `private System.Int32 capacity { private get; private set }`  
- `private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set }`  
- `protected Unity.Entities.Entity selectedEntity { protected get }`  
- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

## Constructors

- `public CargoSection()`  

## Methods

- `private AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.CargoSection+CargoKey`  

