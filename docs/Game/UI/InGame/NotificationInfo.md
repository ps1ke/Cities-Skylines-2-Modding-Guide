# Game.UI.InGame.NotificationInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Game.UI.InGame.NotificationInfo>`  

## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  
- `private readonly Unity.Entities.Entity <target>k__BackingField`  
- `private readonly System.Int32 <priority>k__BackingField`  
- `private readonly System.Collections.Generic.List<Unity.Entities.Entity> m_Targets`  

## Properties

- `public Unity.Entities.Entity entity { get }`  
- `public Unity.Entities.Entity target { get }`  
- `public System.Int32 priority { get }`  
- `public System.Int32 count { get }`  

## Constructors

- `public NotificationInfo(Game.UI.InGame.Notification notification)`  

## Methods

- `public AddTarget(Unity.Entities.Entity otherTarget) : System.Void`  
- `public CompareTo(Game.UI.InGame.NotificationInfo other) : System.Int32`  

