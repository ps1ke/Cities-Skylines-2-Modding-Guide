# Game.Assets.SimulationDateTime

**Assembly:** `Game`  
**Namespace:** `Game.Assets`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Assets.SimulationDateTime>`, `Colossal.UI.Binding.IJsonReadable`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct SimulationDateTime : System.IEquatable<Game.Assets.SimulationDateTime>, Colossal.UI.Binding.IJsonReadable, Colossal.UI.Binding.IJsonWritable
{
    public System.Int32 year;
    public System.Int32 month;
    public System.Int32 hour;
    public System.Int32 minute;

    public SimulationDateTime(System.Int32 year, System.Int32 month, System.Int32 hour, System.Int32 minute);

    public System.Boolean Equals(Game.Assets.SimulationDateTime other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    private static System.Void SupportValueTypesForAOT();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Int32 year`  

```csharp
public System.Int32 year;
```

- `public System.Int32 month`  

```csharp
public System.Int32 month;
```

- `public System.Int32 hour`  

```csharp
public System.Int32 hour;
```

- `public System.Int32 minute`  

```csharp
public System.Int32 minute;
```


## Constructors

- `public SimulationDateTime(System.Int32 year, System.Int32 month, System.Int32 hour, System.Int32 minute)`  

```csharp
public SimulationDateTime(System.Int32 year, System.Int32 month, System.Int32 hour, System.Int32 minute);
```


## Methods

- `public Equals(Game.Assets.SimulationDateTime other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Assets.SimulationDateTime other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static System.Void SupportValueTypesForAOT();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


