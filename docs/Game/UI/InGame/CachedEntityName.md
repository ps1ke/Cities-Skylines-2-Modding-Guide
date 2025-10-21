# Game.UI.InGame.ChirpLinkSystem+CachedEntityName

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CachedEntityName : Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Entity;
    public Game.UI.NameSystem+Name m_Name;

    public CachedEntityName(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Game.UI.NameSystem+Name m_Name`  

```csharp
public Game.UI.NameSystem+Name m_Name;
```


## Constructors

- `public CachedEntityName(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity)`  

```csharp
public CachedEntityName(Game.UI.NameSystem nameSystem, Unity.Entities.Entity entity);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


