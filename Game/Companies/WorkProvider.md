# Game.Companies.WorkProvider

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WorkProvider : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_MaxWorkers;
    public System.Int16 m_UneducatedCooldown;
    public System.Int16 m_EducatedCooldown;
    public Unity.Entities.Entity m_UneducatedNotificationEntity;
    public Unity.Entities.Entity m_EducatedNotificationEntity;
    public System.Int16 m_EfficiencyCooldown;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_MaxWorkers`  

```csharp
public System.Int32 m_MaxWorkers;
```

- `public System.Int16 m_UneducatedCooldown`  

```csharp
public System.Int16 m_UneducatedCooldown;
```

- `public System.Int16 m_EducatedCooldown`  

```csharp
public System.Int16 m_EducatedCooldown;
```

- `public Unity.Entities.Entity m_UneducatedNotificationEntity`  

```csharp
public Unity.Entities.Entity m_UneducatedNotificationEntity;
```

- `public Unity.Entities.Entity m_EducatedNotificationEntity`  

```csharp
public Unity.Entities.Entity m_EducatedNotificationEntity;
```

- `public System.Int16 m_EfficiencyCooldown`  

```csharp
public System.Int16 m_EfficiencyCooldown;
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


