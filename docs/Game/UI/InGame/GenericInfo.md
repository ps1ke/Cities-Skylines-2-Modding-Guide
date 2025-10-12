# Game.UI.InGame.GenericInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.ISubsectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `private System.String <label>k__BackingField`  
- `private System.String <value>k__BackingField`  
- `private Unity.Entities.Entity <target>k__BackingField`  
- `private readonly System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> m_ShouldDisplay`  
- `private readonly System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> m_OnUpdate`  

## Properties

- `public System.String label { get; set }`  
- `public System.String value { get; set }`  
- `public Unity.Entities.Entity target { get; set }`  

## Constructors

- `public GenericInfo(System.Func<Unity.Entities.Entity, Unity.Entities.Entity, System.Boolean> shouldDisplay, System.Action<Unity.Entities.Entity, Unity.Entities.Entity, Game.UI.InGame.GenericInfo> onUpdate)`  

## Methods

- `public DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  
- `public OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

