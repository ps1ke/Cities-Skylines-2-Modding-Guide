# Game.Serialization.SerializerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private System.Int32 <totalSize>k__BackingField`  
- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  
- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  
- `private Game.Serialization.WriteSystem m_WriteSystem`  
- `private Game.Serialization.ReadSystem m_ReadSystem`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Colossal.Serialization.Entities.ComponentSerializerLibrary m_ComponentSerializerLibrary`  
- `private Colossal.Serialization.Entities.SystemSerializerLibrary m_SystemSerializerLibrary`  
- `private Unity.Entities.EntityQuery m_Query`  

## Properties

- `public Colossal.Serialization.Entities.ComponentSerializerLibrary componentLibrary { get }`  
- `public Colossal.Serialization.Entities.SystemSerializerLibrary systemLibrary { get }`  
- `public System.Int32 totalSize { get; set }`  

## Constructors

- `public SerializerSystem()`  

## Methods

- `private CreateQuery(System.Collections.Generic.IEnumerable<Unity.Entities.ComponentType> serializableComponents) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public SetDirty() : System.Void`  

