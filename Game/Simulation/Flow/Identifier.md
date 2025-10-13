# Game.Simulation.Flow.Identifier

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Simulation.Flow.Identifier>`  

## Code

```csharp
public sealed struct Identifier : System.IEquatable<Game.Simulation.Flow.Identifier>
{
    public System.Int32 m_Index;
    public System.Int32 m_Version;

    public static Game.Simulation.Flow.Identifier Null { get; }

    public Identifier(System.Int32 index, System.Int32 version);

    public System.Boolean Equals(Game.Simulation.Flow.Identifier other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```

- `public System.Int32 m_Version`  

```csharp
public System.Int32 m_Version;
```


## Properties

- `public static Game.Simulation.Flow.Identifier Null { get }`  

```csharp
public static Game.Simulation.Flow.Identifier Null { get; }
```


## Constructors

- `public Identifier(System.Int32 index, System.Int32 version)`  

```csharp
public Identifier(System.Int32 index, System.Int32 version);
```


## Methods

- `public Equals(Game.Simulation.Flow.Identifier other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Simulation.Flow.Identifier other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


