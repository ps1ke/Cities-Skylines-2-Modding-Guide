# Game.Simulation.CollectedCityServiceFeeData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CollectedCityServiceFeeData : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_PlayerResource;
    public System.Single m_Export;
    public System.Single m_Import;
    public System.Single m_Internal;
    public System.Single m_ExportCount;
    public System.Single m_ImportCount;
    public System.Single m_InternalCount;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_PlayerResource`  

```csharp
public System.Int32 m_PlayerResource;
```

- `public System.Single m_Export`  

```csharp
public System.Single m_Export;
```

- `public System.Single m_Import`  

```csharp
public System.Single m_Import;
```

- `public System.Single m_Internal`  

```csharp
public System.Single m_Internal;
```

- `public System.Single m_ExportCount`  

```csharp
public System.Single m_ExportCount;
```

- `public System.Single m_ImportCount`  

```csharp
public System.Single m_ImportCount;
```

- `public System.Single m_InternalCount`  

```csharp
public System.Single m_InternalCount;
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


