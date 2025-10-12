# Game.UI.InGame.StorageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.Entity m_CompanyEntity`  
- `private System.Int32 <stored>k__BackingField`  
- `private System.Int32 <capacity>k__BackingField`  
- `private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField`  
- `private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField`  
- `private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 stored { private get; private set }`  
- `private System.Int32 capacity { private get; private set }`  
- `private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set }`  
- `private Game.UI.InGame.UIResource+StorageType storageType { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set }`  

## Constructors

- `public StorageSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.StorageSection+StorageStatus`  

