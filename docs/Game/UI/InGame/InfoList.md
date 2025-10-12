# Game.UI.InGame.InfoList

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.ISubsectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `private System.String <label>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> <list>k__BackingField`  
- `private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay`  
- `private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> m_OnUpdate`  
- `private System.Boolean <expanded>k__BackingField`  

## Properties

- `public System.String label { get; set }`  
- `private System.Collections.Generic.List<Game.UI.InGame.InfoList+Item> list { private get; private set }`  
- `private System.Boolean expanded { private get; private set }`  

## Constructors

- `public InfoList(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.InfoList> onUpdate)`  

## Methods

- `public Add(Game.UI.InGame.InfoList+Item item) : System.Void`  
- `public DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  
- `public OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.InGame.InfoList+Item`  

