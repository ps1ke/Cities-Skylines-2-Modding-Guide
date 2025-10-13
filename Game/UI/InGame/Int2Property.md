# Game.UI.InGame.Int2Property

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Int2Property : Colossal.UI.Binding.IJsonWritable
{
    public System.String labelId;
    public Unity.Mathematics.int2 value;
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

- `public Unity.Mathematics.int2 value`  

```csharp
public Unity.Mathematics.int2 value;
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
		writer.TypeBegin("Game.UI.Common.Number2Property");
		writer.PropertyName("labelId");
		writer.Write(labelId);
		writer.PropertyName("value");
		writer.Write(value);
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


