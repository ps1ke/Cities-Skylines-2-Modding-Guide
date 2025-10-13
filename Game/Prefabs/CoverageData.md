# Game.Prefabs.CoverageData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CoverageData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Net.CoverageService m_Service;
    public System.Single m_Range;
    public System.Single m_Capacity;
    public System.Single m_Magnitude;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Net.CoverageService m_Service`  

```csharp
public Game.Net.CoverageService m_Service;
```

- `public System.Single m_Range`  

```csharp
public System.Single m_Range;
```

- `public System.Single m_Capacity`  

```csharp
public System.Single m_Capacity;
```

- `public System.Single m_Magnitude`  

```csharp
public System.Single m_Magnitude;
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


