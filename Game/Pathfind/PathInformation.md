# Game.Pathfind.PathInformation

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PathInformation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Origin;
    public Unity.Entities.Entity m_Destination;
    public System.Single m_Distance;
    public System.Single m_Duration;
    public System.Single m_TotalCost;
    public Game.Pathfind.PathMethod m_Methods;
    public Game.Pathfind.PathFlags m_State;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Origin`  

```csharp
public Unity.Entities.Entity m_Origin;
```

- `public Unity.Entities.Entity m_Destination`  

```csharp
public Unity.Entities.Entity m_Destination;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```

- `public System.Single m_Duration`  

```csharp
public System.Single m_Duration;
```

- `public System.Single m_TotalCost`  

```csharp
public System.Single m_TotalCost;
```

- `public Game.Pathfind.PathMethod m_Methods`  

```csharp
public Game.Pathfind.PathMethod m_Methods;
```

- `public Game.Pathfind.PathFlags m_State`  

```csharp
public Game.Pathfind.PathFlags m_State;
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


