# Game.UI.InGame.ChirpLinkSystem+CachedChirpData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Game.UI.InGame.ChirpLinkSystem+CachedEntityName m_Sender`  
- `public Game.UI.InGame.ChirpLinkSystem+CachedEntityName[] m_Links`  

## Constructors

- `public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData)`  
- `public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData, Unity.Entities.DynamicBuffer<Game.Triggers.ChirpEntity> chirpEntities)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Remove(Unity.Entities.Entity entity) : Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public Update(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity) : Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  

