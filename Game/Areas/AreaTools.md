# Game.Areas.AreaTools

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AreaTools
{
    public AreaTools();

    public static System.String GetMapFeatureIconName(Game.Areas.MapFeature feature);
}
```


## Constructors

- `public AreaTools()`  

```csharp
public AreaTools();
```


## Methods

- `public static GetMapFeatureIconName(Game.Areas.MapFeature feature) : System.String`  

```csharp
public static string GetMapFeatureIconName(MapFeature feature)
	{
		return feature switch
		{
			MapFeature.None => "None", 
			MapFeature.Area => "Area", 
			MapFeature.BuildableLand => "Building", 
			MapFeature.FertileLand => "Fertility", 
			MapFeature.Forest => "Forest", 
			MapFeature.Oil => "Oil", 
			MapFeature.Ore => "Coal", 
			MapFeature.SurfaceWater => "Water", 
			MapFeature.GroundWater => "Water", 
			_ => "None", 
		};
	}
```


