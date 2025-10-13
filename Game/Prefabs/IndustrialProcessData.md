# Game.Prefabs.IndustrialProcessData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct IndustrialProcessData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.ResourceStack m_Input1;
    public Game.Prefabs.ResourceStack m_Input2;
    public Game.Prefabs.ResourceStack m_Output;
    public System.Int32 m_WorkPerUnit;
    public System.Single m_MaxWorkersPerCell;
    public System.Byte m_IsImport;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.ResourceStack m_Input1`  

```csharp
public Game.Prefabs.ResourceStack m_Input1;
```

- `public Game.Prefabs.ResourceStack m_Input2`  

```csharp
public Game.Prefabs.ResourceStack m_Input2;
```

- `public Game.Prefabs.ResourceStack m_Output`  

```csharp
public Game.Prefabs.ResourceStack m_Output;
```

- `public System.Int32 m_WorkPerUnit`  

```csharp
public System.Int32 m_WorkPerUnit;
```

- `public System.Single m_MaxWorkersPerCell`  

```csharp
public System.Single m_MaxWorkersPerCell;
```

- `public System.Byte m_IsImport`  

```csharp
public System.Byte m_IsImport;
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


