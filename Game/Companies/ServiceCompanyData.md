# Game.Companies.ServiceCompanyData

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ServiceCompanyData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_MaxService;
    public System.Int32 m_WorkPerUnit;
    public System.Single m_MaxWorkersPerCell;
    public System.Int32 m_ServiceConsuming;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_MaxService`  

```csharp
public System.Int32 m_MaxService;
```

- `public System.Int32 m_WorkPerUnit`  

```csharp
public System.Int32 m_WorkPerUnit;
```

- `public System.Single m_MaxWorkersPerCell`  

```csharp
public System.Single m_MaxWorkersPerCell;
```

- `public System.Int32 m_ServiceConsuming`  

```csharp
public System.Int32 m_ServiceConsuming;
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


