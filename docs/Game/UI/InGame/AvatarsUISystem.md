# Game.UI.InGame.AvatarsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.NameSystem m_NameSystem`  
- `private Unity.Entities.EntityQuery m_ColorsQuery`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AvatarsBinding`  
- `private static const System.String kGroup`  
- `private static const System.Int32 kIconSize`  

## Constructors

- `public AvatarsUISystem()`  

## Methods

- `private BindAvatar(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `private GetColor(Unity.Entities.Entity entity) : UnityEngine.Color32`  
- `private GetPicture(Unity.Entities.Entity entity) : System.String`  
- `private GetRandomIndex(Unity.Entities.Entity entity) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

