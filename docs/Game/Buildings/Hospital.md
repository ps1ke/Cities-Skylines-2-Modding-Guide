# Game.Buildings.Hospital

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Hospital : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Buildings.HospitalFlags m_Flags;
    public System.Byte m_TreatmentBonus;
    public System.Byte m_MinHealth;
    public System.Byte m_MaxHealth;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Buildings.HospitalFlags m_Flags`  

```csharp
public Game.Buildings.HospitalFlags m_Flags;
```

- `public System.Byte m_TreatmentBonus`  

```csharp
public System.Byte m_TreatmentBonus;
```

- `public System.Byte m_MinHealth`  

```csharp
public System.Byte m_MinHealth;
```

- `public System.Byte m_MaxHealth`  

```csharp
public System.Byte m_MaxHealth;
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


