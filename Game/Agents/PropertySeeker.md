# Game.Agents.PropertySeeker

**Assembly:** `Game`  
**Namespace:** `Game.Agents`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Unity.Entities.IEnableableComponent`  

## Code

```csharp
public sealed struct PropertySeeker : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, Unity.Entities.IEnableableComponent
{
    public Unity.Entities.Entity m_TargetProperty;
    public Unity.Entities.Entity m_BestProperty;
    public System.Single m_BestPropertyScore;
    public System.UInt32 m_LastPropertySeekFrame;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetProperty`  

```csharp
public Unity.Entities.Entity m_TargetProperty;
```

- `public Unity.Entities.Entity m_BestProperty`  

```csharp
public Unity.Entities.Entity m_BestProperty;
```

- `public System.Single m_BestPropertyScore`  

```csharp
public System.Single m_BestPropertyScore;
```

- `public System.UInt32 m_LastPropertySeekFrame`  

```csharp
public System.UInt32 m_LastPropertySeekFrame;
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


