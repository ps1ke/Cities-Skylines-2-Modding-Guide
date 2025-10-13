# Game.UI.InGame.IntRangeProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct IntRangeProperty : Colossal.UI.Binding.IJsonWritable
{
    public System.String labelId;
    public System.Int32 minValue;
    public System.Int32 maxValue;
    public System.String unit;
    public System.Boolean signed;
    public System.String icon;
    public System.String valueIcon;

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String labelId`  

```csharp
public System.String labelId;
```

- `public System.Int32 minValue`  

```csharp
public System.Int32 minValue;
```

- `public System.Int32 maxValue`  

```csharp
public System.Int32 maxValue;
```

- `public System.String unit`  

```csharp
public System.String unit;
```

- `public System.Boolean signed`  

```csharp
public System.Boolean signed;
```

- `public System.String icon`  

```csharp
public System.String icon;
```

- `public System.String valueIcon`  

```csharp
public System.String valueIcon;
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin("Game.UI.Common.NumberRangeProperty");
		writer.PropertyName("labelId");
		writer.Write(labelId);
		writer.PropertyName("minValue");
		writer.Write(minValue);
		writer.PropertyName("maxValue");
		writer.Write(maxValue);
		writer.PropertyName("unit");
		writer.Write(unit);
		writer.PropertyName("signed");
		writer.Write(signed);
		writer.PropertyName("icon");
		writer.Write(icon);
		writer.PropertyName("valueIcon");
		writer.Write(valueIcon);
		writer.TypeEnd();
	}
```


