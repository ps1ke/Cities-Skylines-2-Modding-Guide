# Game.Prefabs.StackData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct StackData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Colossal.Mathematics.Bounds1 m_FirstBounds;
    public Colossal.Mathematics.Bounds1 m_MiddleBounds;
    public Colossal.Mathematics.Bounds1 m_LastBounds;
    public Game.Prefabs.StackDirection m_Direction;
    public Unity.Mathematics.bool3 m_DontScale;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_FirstBounds`  

```csharp
public Colossal.Mathematics.Bounds1 m_FirstBounds;
```

- `public Colossal.Mathematics.Bounds1 m_MiddleBounds`  

```csharp
public Colossal.Mathematics.Bounds1 m_MiddleBounds;
```

- `public Colossal.Mathematics.Bounds1 m_LastBounds`  

```csharp
public Colossal.Mathematics.Bounds1 m_LastBounds;
```

- `public Game.Prefabs.StackDirection m_Direction`  

```csharp
public Game.Prefabs.StackDirection m_Direction;
```

- `public Unity.Mathematics.bool3 m_DontScale`  

```csharp
public Unity.Mathematics.bool3 m_DontScale;
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


