# Game.UI.Widgets.CustomFieldAttribute

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `UnityEngine.PropertyAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class CustomFieldAttribute : UnityEngine.PropertyAttribute
{
    private System.Type <Factory>k__BackingField;

    public System.Type Factory { get; set; }

    public CustomFieldAttribute(System.Type factory);

}
```


## Fields

- `private System.Type <Factory>k__BackingField`  

```csharp
private System.Type <Factory>k__BackingField;
```


## Properties

- `public System.Type Factory { get; set }`  

```csharp
public System.Type Factory { get; set; }
```


## Constructors

- `public CustomFieldAttribute(System.Type factory)`  

```csharp
public CustomFieldAttribute([NotNull] Type factory)
	{
		Factory = factory ?? throw new ArgumentNullException("factory");
	}
```


