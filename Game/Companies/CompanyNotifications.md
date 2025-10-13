# Game.Companies.CompanyNotifications

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CompanyNotifications : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int16 m_NoInputCounter;
    public System.Int16 m_NoCustomersCounter;
    public Unity.Entities.Entity m_NoInputEntity;
    public Unity.Entities.Entity m_NoCustomersEntity;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int16 m_NoInputCounter`  

```csharp
public System.Int16 m_NoInputCounter;
```

- `public System.Int16 m_NoCustomersCounter`  

```csharp
public System.Int16 m_NoCustomersCounter;
```

- `public Unity.Entities.Entity m_NoInputEntity`  

```csharp
public Unity.Entities.Entity m_NoInputEntity;
```

- `public Unity.Entities.Entity m_NoCustomersEntity`  

```csharp
public Unity.Entities.Entity m_NoCustomersEntity;
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


