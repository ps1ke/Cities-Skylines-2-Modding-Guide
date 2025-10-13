# Game.UI.Widgets.NumberStepAttribute

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class NumberStepAttribute : UnityEngine.PropertyAttribute
{
    private System.Single <Step>k__BackingField;

    public System.Single Step { get; set; }

    public NumberStepAttribute(System.Single step);

}
```


## Fields

- `private System.Single <Step>k__BackingField`  

```csharp
private System.Single <Step>k__BackingField;
```


## Properties

- `public System.Single Step { get; set }`  

```csharp
public System.Single Step { get; set; }
```


## Constructors

- `public NumberStepAttribute(System.Single step)`  

```csharp
public NumberStepAttribute(float step)
	{
		Step = step;
	}
```


