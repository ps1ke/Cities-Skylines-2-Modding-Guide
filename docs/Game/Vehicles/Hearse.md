# Game.Vehicles.Hearse

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Hearse : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.HearseFlags m_State;
    public Unity.Entities.Entity m_TargetCorpse;
    public Unity.Entities.Entity m_TargetRequest;
    public System.Single m_PathElementTime;

    public Hearse(Unity.Entities.Entity targetCorpse, Game.Vehicles.HearseFlags state);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.HearseFlags m_State`  

```csharp
public Game.Vehicles.HearseFlags m_State;
```

- `public Unity.Entities.Entity m_TargetCorpse`  

```csharp
public Unity.Entities.Entity m_TargetCorpse;
```

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```


## Constructors

- `public Hearse(Unity.Entities.Entity targetCorpse, Game.Vehicles.HearseFlags state)`  

```csharp
public Hearse(Unity.Entities.Entity targetCorpse, Game.Vehicles.HearseFlags state);
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


