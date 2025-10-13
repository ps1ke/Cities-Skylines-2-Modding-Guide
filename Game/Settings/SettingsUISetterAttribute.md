# Game.Settings.SettingsUISetterAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUISetterAttribute : System.Attribute
{
    public readonly System.Type setterType;
    public readonly System.String setterMethod;

    public SettingsUISetterAttribute(System.Type setterType, System.String setterMethod);

}
```


## Fields

- `public readonly System.Type setterType`  

```csharp
public readonly System.Type setterType;
```

- `public readonly System.String setterMethod`  

```csharp
public readonly System.String setterMethod;
```


## Constructors

- `public SettingsUISetterAttribute(System.Type setterType, System.String setterMethod)`  

```csharp
public SettingsUISetterAttribute(Type setterType, string setterMethod)
	{
		this.setterType = setterType;
		this.setterMethod = setterMethod;
	}
```


