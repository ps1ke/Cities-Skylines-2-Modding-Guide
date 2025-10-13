# Game.UI.Widgets.ColorGradient

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct ColorGradient : Colossal.UI.Binding.IJsonWritable
{
    public Game.UI.Widgets.GradientStop[] stops;

    public ColorGradient(Game.UI.Widgets.GradientStop[] stops);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.UI.Widgets.GradientStop[] stops`  

```csharp
public Game.UI.Widgets.GradientStop[] stops;
```


## Constructors

- `public ColorGradient(Game.UI.Widgets.GradientStop[] stops)`  

```csharp
public static explicit operator ColorGradient(Gradient gradient)
	{
		List<GradientStop> list = new List<GradientStop>();
		GradientColorKey[] colorKeys = gradient.colorKeys;
		for (int i = 0; i < colorKeys.Length; i++)
		{
			GradientColorKey gradientColorKey = colorKeys[i];
			list.Add(new GradientStop(gradientColorKey.time, gradientColorKey.color));
		}
		return new ColorGradient(list.ToArray());
	}
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("stops");
		int num = ((stops != null) ? stops.Length : 0);
		writer.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			writer.Write(stops[i]);
		}
		writer.ArrayEnd();
		writer.TypeEnd();
	}
```


