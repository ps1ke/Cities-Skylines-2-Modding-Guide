# Game.UI.IconValuePairs

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class IconValuePairs
{
    private Game.UI.IconValuePairs+IconValuePair[] iconValuePairArray;

    public IconValuePairs(Game.UI.IconValuePairs+IconValuePair[] iconValuePairArray);

    public System.String GetIconFromValue(System.Single value);
}
```


## Fields

- `private Game.UI.IconValuePairs+IconValuePair[] iconValuePairArray`  

```csharp
private Game.UI.IconValuePairs+IconValuePair[] iconValuePairArray;
```


## Constructors

- `public IconValuePairs(Game.UI.IconValuePairs+IconValuePair[] iconValuePairArray)`  

```csharp
public IconValuePairs(IconValuePair[] iconValuePairArray)
	{
		this.iconValuePairArray = iconValuePairArray;
	}
```


## Methods

- `public GetIconFromValue(System.Single value) : System.String`  

```csharp
public string GetIconFromValue(float value)
	{
		if (iconValuePairArray == null || iconValuePairArray.Length == 0)
		{
			return string.Empty;
		}
		IconValuePair[] array = iconValuePairArray;
		for (int i = 0; i < array.Length; i++)
		{
			IconValuePair iconValuePair = array[i];
			if (value <= iconValuePair.stop)
			{
				return iconValuePair.icon;
			}
		}
		return iconValuePairArray[^1].icon;
	}
```


## Nested types

- `Game.UI.IconValuePairs+IconValuePair`  

