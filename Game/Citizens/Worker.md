# Game.Citizens.Worker

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Worker : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Workplace;
    public System.Single m_LastCommuteTime;
    public System.Byte m_Level;
    public Game.Companies.Workshift m_Shift;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Workplace`  

```csharp
public Unity.Entities.Entity m_Workplace;
```

- `public System.Single m_LastCommuteTime`  

```csharp
public System.Single m_LastCommuteTime;
```

- `public System.Byte m_Level`  

```csharp
public System.Byte m_Level;
```

- `public Game.Companies.Workshift m_Shift`  

```csharp
public Game.Companies.Workshift m_Shift;
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


