# Game.Simulation.CitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.ICitySystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitySystem : Game.GameSystemBase, Game.Simulation.ICitySystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.Entity m_City;
    private System.Int32 m_Money;
    private System.Int32 m_XP;

    public Unity.Entities.Entity City { get; }
    public System.Int32 moneyAmount { get; }
    public System.Int32 XP { get; }

    public CitySystem();

    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.Entity m_City`  

```csharp
private Unity.Entities.Entity m_City;
```

- `private System.Int32 m_Money`  

```csharp
private System.Int32 m_Money;
```

- `private System.Int32 m_XP`  

```csharp
private System.Int32 m_XP;
```


## Properties

- `public Unity.Entities.Entity City { get }`  

```csharp
public Unity.Entities.Entity City { get; }
```

- `public System.Int32 moneyAmount { get }`  

```csharp
public System.Int32 moneyAmount { get; }
```

- `public System.Int32 XP { get }`  

```csharp
public System.Int32 XP { get; }
```


## Constructors

- `public CitySystem()`  

```csharp
public CitySystem();
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


