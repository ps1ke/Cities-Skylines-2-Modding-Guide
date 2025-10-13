# Game.City.PlayerMoney

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PlayerMoney : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    private System.Int32 m_Money;
    public System.Boolean m_Unlimited;
    public static const System.Int32 kMaxMoney;

    public System.Int32 money { get; }

    public PlayerMoney(System.Int32 amount);

    public System.Void Add(System.Int32 value);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void Subtract(System.Int32 amount);
}
```


## Fields

- `private System.Int32 m_Money`  

```csharp
private System.Int32 m_Money;
```

- `public System.Boolean m_Unlimited`  

```csharp
public System.Boolean m_Unlimited;
```

- `public static const System.Int32 kMaxMoney`  

```csharp
public static const System.Int32 kMaxMoney;
```


## Properties

- `public System.Int32 money { get }`  

```csharp
public System.Int32 money { get; }
```


## Constructors

- `public PlayerMoney(System.Int32 amount)`  

```csharp
public PlayerMoney(System.Int32 amount);
```


## Methods

- `public Add(System.Int32 value) : System.Void`  

```csharp
public System.Void Add(System.Int32 value);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public Subtract(System.Int32 amount) : System.Void`  

```csharp
public System.Void Subtract(System.Int32 amount);
```


