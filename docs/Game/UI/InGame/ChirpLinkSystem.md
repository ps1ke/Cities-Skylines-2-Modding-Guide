# Game.UI.InGame.ChirpLinkSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.NameSystem m_NameSystem`  
- `private Unity.Entities.EntityQuery m_CreatedChirpQuery`  
- `private Unity.Entities.EntityQuery m_AllChirpsQuery`  
- `private Unity.Entities.EntityQuery m_DeletedChirpQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery`  
- `private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData`  

## Constructors

- `public ChirpLinkSystem()`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private Initialize() : System.Void`  
- `private LinkExists(Unity.Entities.DynamicBuffer<Game.Triggers.ChirpLink> links, Unity.Entities.Entity link) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RegisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public TryGetData(Unity.Entities.Entity chirp, Game.UI.InGame.ChirpLinkSystem+CachedChirpData& data) : System.Boolean`  
- `private UnregisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity) : System.Void`  

## Nested types

- `Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  
- `Game.UI.InGame.ChirpLinkSystem+CachedEntityName`  

