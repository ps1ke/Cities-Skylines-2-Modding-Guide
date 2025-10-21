# Game.Settings.ScreenResolution

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Settings.ScreenResolution>`, `System.IComparable<Game.Settings.ScreenResolution>`, `Colossal.UI.Binding.IJsonReadable`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct ScreenResolution : System.IEquatable<Game.Settings.ScreenResolution>, System.IComparable<Game.Settings.ScreenResolution>, Colossal.UI.Binding.IJsonReadable, Colossal.UI.Binding.IJsonWritable
{
    public System.Int32 width;
    public System.Int32 height;
    public UnityEngine.RefreshRate refreshRate;

    public System.Double refreshRateDelta { get; }
    public System.Boolean isValid { get; }

    public ScreenResolution(UnityEngine.Resolution resolution);

    public System.Int32 CompareTo(Game.Settings.ScreenResolution other);
    public System.Boolean Equals(Game.Settings.ScreenResolution other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Sanitize();
    private static System.Void SupportValueTypesForAOT();
    public virtual System.String ToString();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Int32 width`  

```csharp
public System.Int32 width;
```

- `public System.Int32 height`  

```csharp
public System.Int32 height;
```

- `public UnityEngine.RefreshRate refreshRate`  

```csharp
public UnityEngine.RefreshRate refreshRate;
```


## Properties

- `public System.Double refreshRateDelta { get }`  

```csharp
public System.Double refreshRateDelta { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public ScreenResolution(UnityEngine.Resolution resolution)`  

```csharp
public ScreenResolution(UnityEngine.Resolution resolution);
```


## Methods

- `public CompareTo(Game.Settings.ScreenResolution other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Settings.ScreenResolution other);
```

- `public Equals(Game.Settings.ScreenResolution other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Settings.ScreenResolution other);
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

- `public Sanitize() : System.Void`  

```csharp
public System.Void Sanitize();
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static System.Void SupportValueTypesForAOT();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


