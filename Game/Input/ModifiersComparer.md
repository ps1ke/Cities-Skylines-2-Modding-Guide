# Game.Input.ModifiersComparer

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IComparer<System.Single>`  

## Code

```csharp
public sealed struct ModifiersComparer : System.Collections.Generic.IComparer<System.Single>
{
    public System.Int32 Compare(System.Single x, System.Single y);
}
```


## Methods

- `public Compare(System.Single x, System.Single y) : System.Int32`  

```csharp
public int Compare(float x, float y)
	{
		if (float.IsNaN(x))
		{
			return 1;
		}
		if (float.IsNaN(y))
		{
			return -1;
		}
		float num = Math.Abs(x);
		float num2 = Math.Abs(y);
		if (num > num2)
		{
			return -1;
		}
		if (!(num < num2))
		{
			return 0;
		}
		return 1;
	}
```


