# Game.UI.Editor.SeasonWheel+Season

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.Editor.SeasonWheel+Season>`  

## Code

```csharp
public sealed struct Season : Colossal.UI.Binding.IJsonWritable, System.IEquatable<Game.UI.Editor.SeasonWheel+Season>
{
    public Unity.Entities.Entity entity;
    public Colossal.Mathematics.Bounds1 startTimeOfYear;
    public System.Single temperature;

    public System.Boolean Equals(Game.UI.Editor.SeasonWheel+Season other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity entity`  

```csharp
public Unity.Entities.Entity entity;
```

- `public Colossal.Mathematics.Bounds1 startTimeOfYear`  

```csharp
public Colossal.Mathematics.Bounds1 startTimeOfYear;
```

- `public System.Single temperature`  

```csharp
public System.Single temperature;
```


## Methods

- `public Equals(Game.UI.Editor.SeasonWheel+Season other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Editor.SeasonWheel+Season other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


