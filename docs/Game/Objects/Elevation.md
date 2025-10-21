# Game.Objects.Elevation

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Elevation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Elevation;
    public Game.Objects.ElevationFlags m_Flags;

    public Elevation(System.Single elevation, Game.Objects.ElevationFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Elevation`  

```csharp
public System.Single m_Elevation;
```

- `public Game.Objects.ElevationFlags m_Flags`  

```csharp
public Game.Objects.ElevationFlags m_Flags;
```


## Constructors

- `public Elevation(System.Single elevation, Game.Objects.ElevationFlags flags)`  

```csharp
public Elevation(System.Single elevation, Game.Objects.ElevationFlags flags);
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


