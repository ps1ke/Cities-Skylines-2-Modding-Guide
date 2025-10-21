# Game.Citizens.CrimeVictim

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Unity.Entities.IEnableableComponent`  

## Code

```csharp
public sealed struct CrimeVictim : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, Unity.Entities.IEnableableComponent
{
    public System.Byte m_Effect;

    public CrimeVictim(System.Byte effect);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Byte m_Effect`  

```csharp
public System.Byte m_Effect;
```


## Constructors

- `public CrimeVictim(System.Byte effect)`  

```csharp
public CrimeVictim(System.Byte effect);
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


