# Game.UI.InGame.ChirpLinkSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ChirpLinkSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_CreatedChirpQuery;
    private Unity.Entities.EntityQuery m_AllChirpsQuery;
    private Unity.Entities.EntityQuery m_DeletedChirpQuery;
    private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery;
    private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData;

    public ChirpLinkSystem();

    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void Initialize();
    private System.Boolean LinkExists(Unity.Entities.DynamicBuffer<Game.Triggers.ChirpLink> links, Unity.Entities.Entity link);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RegisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Boolean TryGetData(Unity.Entities.Entity chirp, Game.UI.InGame.ChirpLinkSystem+CachedChirpData& data);
    private System.Void UnregisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity);
}
```


## Fields

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_AllChirpsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllChirpsQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLinkEntityQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedLinkEntityQuery;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.UI.InGame.ChirpLinkSystem+CachedChirpData> m_CachedChirpData;
```


## Constructors

- `public ChirpLinkSystem()`  

```csharp
public ChirpLinkSystem();
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private Initialize() : System.Void`  

```csharp
private System.Void Initialize();
```

- `private LinkExists(Unity.Entities.DynamicBuffer<Game.Triggers.ChirpLink> links, Unity.Entities.Entity link) : System.Boolean`  

```csharp
private System.Boolean LinkExists(Unity.Entities.DynamicBuffer<Game.Triggers.ChirpLink> links, Unity.Entities.Entity link);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RegisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity) : System.Void`  

```csharp
private System.Void RegisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public TryGetData(Unity.Entities.Entity chirp, Game.UI.InGame.ChirpLinkSystem+CachedChirpData& data) : System.Boolean`  

```csharp
public System.Boolean TryGetData(Unity.Entities.Entity chirp, Game.UI.InGame.ChirpLinkSystem+CachedChirpData& data);
```

- `private UnregisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity) : System.Void`  

```csharp
private System.Void UnregisterLink(Unity.Entities.Entity linkEntity, Unity.Entities.Entity chirpEntity);
```


## Nested types

- `Game.UI.InGame.ChirpLinkSystem+CachedChirpData`  
- `Game.UI.InGame.ChirpLinkSystem+CachedEntityName`  

