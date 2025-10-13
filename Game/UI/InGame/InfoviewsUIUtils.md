# Game.UI.InGame.InfoviewsUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class InfoviewsUIUtils
{
    public InfoviewsUIUtils();

    public static System.Void UpdateFiveSlicePieChartData(Colossal.UI.Binding.IJsonWriter binder, System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d, System.Int32 e);
}
```


## Constructors

- `public InfoviewsUIUtils()`  

```csharp
public InfoviewsUIUtils();
```


## Methods

- `public static UpdateFiveSlicePieChartData(Colossal.UI.Binding.IJsonWriter binder, System.Int32 a, System.Int32 b, System.Int32 c, System.Int32 d, System.Int32 e) : System.Void`  

```csharp
public static void UpdateFiveSlicePieChartData(IJsonWriter binder, int a, int b, int c, int d, int e)
	{
		binder.TypeBegin("infoviews.ChartData");
		binder.PropertyName("values");
		binder.ArrayBegin(5u);
		binder.Write(a);
		binder.Write(b);
		binder.Write(c);
		binder.Write(d);
		binder.Write(e);
		binder.ArrayEnd();
		binder.PropertyName("total");
		binder.Write(a + b + c + d + e);
		binder.TypeEnd();
	}
```


