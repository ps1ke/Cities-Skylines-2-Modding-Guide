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
public ScreenResolution(Resolution resolution)
	{
		width = resolution.width;
		height = resolution.height;
		refreshRate = resolution.refreshRateRatio;
	}
```


## Methods

- `public CompareTo(Game.Settings.ScreenResolution other) : System.Int32`  

```csharp
public int CompareTo(ScreenResolution other)
	{
		int num = width.CompareTo(other.width);
		if (num != 0)
		{
			return num;
		}
		int num2 = height.CompareTo(other.height);
		if (num2 != 0)
		{
			return num2;
		}
		return refreshRate.value.CompareTo(other.refreshRate.value);
	}
```

- `public Equals(Game.Settings.ScreenResolution other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is ScreenResolution other)
		{
			return Equals(other);
		}
		return false;
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is ScreenResolution other)
		{
			return Equals(other);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (width, height, refreshRate).GetHashCode();
	}
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public void Read(IJsonReader reader)
	{
		reader.ReadMapBegin();
		reader.ReadProperty("width");
		reader.Read(out width);
		reader.ReadProperty("height");
		reader.Read(out height);
		reader.ReadProperty("numerator");
		reader.Read(out refreshRate.numerator);
		reader.ReadProperty("denominator");
		reader.Read(out refreshRate.denominator);
		reader.ReadMapEnd();
	}
```

- `public Sanitize() : System.Void`  

```csharp
public void Sanitize()
	{
		if (refreshRate.numerator == 0 || refreshRate.denominator == 0 || double.IsNaN(refreshRate.value))
		{
			refreshRate = Screen.currentResolution.refreshRateRatio;
		}
	}
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static void SupportValueTypesForAOT()
	{
		JSON.SupportTypeForAOT<ScreenResolution>();
		JSON.SupportTypeForAOT<RefreshRate>();
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return $"{width}x{height}x{refreshRate.value}Hz";
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(ScreenResolution).FullName);
		writer.PropertyName("width");
		writer.Write(width);
		writer.PropertyName("height");
		writer.Write(height);
		writer.PropertyName("numerator");
		writer.Write(refreshRate.numerator);
		writer.PropertyName("denominator");
		writer.Write(refreshRate.denominator);
		writer.TypeEnd();
	}
```


