# Game.UI.Widgets.NumberUnitAttribute

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class NumberUnitAttribute : UnityEngine.PropertyAttribute
{
    private System.String <Unit>k__BackingField;

    public System.String Unit { get; set; }

    public NumberUnitAttribute(System.String unit);

}
```


## Fields

- `private System.String <Unit>k__BackingField`  

```csharp
private System.String <Unit>k__BackingField;
```


## Properties

- `public System.String Unit { get; set }`  

```csharp
public System.String Unit { get; set; }
```


## Constructors

- `public NumberUnitAttribute(System.String unit)`  

```csharp
public NumberUnitAttribute(string unit)
	{
		Unit = unit;
	}
```


