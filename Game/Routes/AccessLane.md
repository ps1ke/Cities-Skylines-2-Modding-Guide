# Game.Routes.AccessLane

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Routes.AccessLane>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AccessLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Routes.AccessLane>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public System.Single m_CurvePos;

    public AccessLane(Unity.Entities.Entity lane, System.Single curvePos);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Routes.AccessLane other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public System.Single m_CurvePos`  

```csharp
public System.Single m_CurvePos;
```


## Constructors

- `public AccessLane(Unity.Entities.Entity lane, System.Single curvePos)`  

```csharp
public AccessLane(Unity.Entities.Entity lane, System.Single curvePos);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Routes.AccessLane other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Routes.AccessLane other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


