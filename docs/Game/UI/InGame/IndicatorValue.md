# Game.UI.InGame.IndicatorValue

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.UI.InGame.IndicatorValue>`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct IndicatorValue : System.IEquatable<Game.UI.InGame.IndicatorValue>, Colossal.UI.Binding.IJsonWritable
{
    private readonly System.Single <min>k__BackingField;
    private readonly System.Single <max>k__BackingField;
    private readonly System.Single <current>k__BackingField;

    public System.Single min { get; }
    public System.Single max { get; }
    public System.Single current { get; }

    public IndicatorValue(System.Single min, System.Single max, System.Single current);

    public static Game.UI.InGame.IndicatorValue Calculate(System.Single supply, System.Single demand, System.Single minRangeFactor, System.Single maxRangeFactor);
    public System.Boolean Equals(Game.UI.InGame.IndicatorValue other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Single <min>k__BackingField`  

```csharp
private readonly System.Single <min>k__BackingField;
```

- `private readonly System.Single <max>k__BackingField`  

```csharp
private readonly System.Single <max>k__BackingField;
```

- `private readonly System.Single <current>k__BackingField`  

```csharp
private readonly System.Single <current>k__BackingField;
```


## Properties

- `public System.Single min { get }`  

```csharp
public System.Single min { get; }
```

- `public System.Single max { get }`  

```csharp
public System.Single max { get; }
```

- `public System.Single current { get }`  

```csharp
public System.Single current { get; }
```


## Constructors

- `public IndicatorValue(System.Single min, System.Single max, System.Single current)`  

```csharp
public IndicatorValue(System.Single min, System.Single max, System.Single current);
```


## Methods

- `public static Calculate(System.Single supply, System.Single demand, System.Single minRangeFactor = -1, System.Single maxRangeFactor = 1) : Game.UI.InGame.IndicatorValue`  

```csharp
public static Game.UI.InGame.IndicatorValue Calculate(System.Single supply, System.Single demand, System.Single minRangeFactor, System.Single maxRangeFactor);
```

- `public Equals(Game.UI.InGame.IndicatorValue other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.InGame.IndicatorValue other);
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


