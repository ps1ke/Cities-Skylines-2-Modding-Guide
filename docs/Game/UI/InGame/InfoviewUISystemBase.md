# Game.UI.InGame.InfoviewUISystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Game.UI.UIUpdateState m_UpdateState`  
- `private System.Boolean m_Clear`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `protected InfoviewUISystemBase()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `protected abstract PerformUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public RequestUpdate() : System.Void`  
- `protected ResetResults<T>(Unity.Collections.NativeArray<T> results) : System.Void`  

