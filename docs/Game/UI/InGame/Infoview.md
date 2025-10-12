# Game.UI.InGame.InfoviewsUISystem+Infoview

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.InfoviewsUISystem+Infoview>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  
- `private readonly System.String <id>k__BackingField`  
- `private readonly System.String <icon>k__BackingField`  
- `private readonly System.Boolean <locked>k__BackingField`  
- `private readonly System.String <uiTag>k__BackingField`  
- `private readonly System.Int32 <group>k__BackingField`  
- `private readonly System.Int32 <priority>k__BackingField`  
- `private readonly System.Boolean <editor>k__BackingField`  

## Properties

- `public Unity.Entities.Entity entity { get }`  
- `public System.String id { get }`  
- `public System.String icon { get }`  
- `public System.Boolean locked { get }`  
- `public System.String uiTag { get }`  
- `public System.Int32 group { get }`  
- `private System.Int32 priority { private get }`  
- `private System.Boolean editor { private get }`  

## Constructors

- `public Infoview(Unity.Entities.Entity entity, Game.Prefabs.InfoviewPrefab prefab, System.Boolean locked)`  

## Methods

- `public CompareTo(Game.UI.InGame.InfoviewsUISystem+Infoview other) : System.Int32`  
- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

