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
public SimulationDateTime(int year, int month, int hour, int minute)
	{
		this.year = year;
		this.month = month;
		this.hour = hour;
		this.minute = minute;
	}
```


## Methods

- `public Equals(Game.Assets.SimulationDateTime other) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is SimulationDateTime other)
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
		if (obj is SimulationDateTime other)
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
		return (year, month, hour, minute).GetHashCode();
	}
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public void Read(IJsonReader reader)
	{
		reader.ReadMapBegin();
		reader.ReadProperty("year");
		reader.Read(out year);
		reader.ReadProperty("month");
		reader.Read(out month);
		reader.ReadProperty("hour");
		reader.Read(out hour);
		reader.ReadProperty("minute");
		reader.Read(out minute);
		reader.ReadMapEnd();
	}
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static void SupportValueTypesForAOT()
	{
		JSON.SupportTypeForAOT<SimulationDateTime>();
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("year");
		writer.Write(year);
		writer.PropertyName("month");
		writer.Write(month);
		writer.PropertyName("hour");
		writer.Write(hour);
		writer.PropertyName("minute");
		writer.Write(minute);
		writer.TypeEnd();
	}
```


