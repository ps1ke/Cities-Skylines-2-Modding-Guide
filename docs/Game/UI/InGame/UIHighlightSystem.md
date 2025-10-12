# Game.UI.InGame.UIHighlightSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  
- `private System.Boolean m_SkipUpdate`  
- `private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle`  

## Constructors

- `public UIHighlightSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public SkipUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.UIHighlightSystem+HighlightJob`  
- `Game.UI.InGame.UIHighlightSystem+TypeHandle`  

