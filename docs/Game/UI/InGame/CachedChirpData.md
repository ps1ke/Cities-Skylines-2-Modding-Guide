# Game.UI.InGame.ChirpLinkSystem+CachedChirpData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CachedChirpData : Colossal.Serialization.Entities.ISerializable
{
    public Game.UI.InGame.ChirpLinkSystem+CachedEntityName m_Sender;
    public Game.UI.InGame.ChirpLinkSystem+CachedEntityName[] m_Links;

    public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData);
    public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData, Unity.Entities.DynamicBuffer<Game.Triggers.ChirpEntity> chirpEntities);

    public System.Void Deserialize<TReader>(TReader reader);
    public Game.UI.InGame.ChirpLinkSystem+CachedChirpData Remove(Unity.Entities.Entity entity);
    public System.Void Serialize<TWriter>(TWriter writer);
    public Game.UI.InGame.ChirpLinkSystem+CachedChirpData Update(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.UI.InGame.ChirpLinkSystem+CachedEntityName m_Sender`  

```csharp
public Game.UI.InGame.ChirpLinkSystem+CachedEntityName m_Sender;
```

- `public Game.UI.InGame.ChirpLinkSystem+CachedEntityName[] m_Links`  

```csharp
public Game.UI.InGame.ChirpLinkSystem+CachedEntityName[] m_Links;
```


## Constructors

- `public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData)`  

```csharp
public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData);
```

- `public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData, Unity.Entities.DynamicBuffer<Game.Triggers.ChirpEntity> chirpEntities)`  

```csharp
public CachedChirpData(Game.UI.NameSystem nameSystem, Game.Triggers.Chirp chirpData, Unity.Entities.DynamicBuffer<Game.Triggers.ChirpEntity> chirpEntities);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Remove(Unity.Entities.Entity entity) : Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  

```csharp
public Game.UI.InGame.ChirpLinkSystem+CachedChirpData Remove(Unity.Entities.Entity entity);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public Update(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity) : Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  

```csharp
public Game.UI.InGame.ChirpLinkSystem+CachedChirpData Update(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity);
```


