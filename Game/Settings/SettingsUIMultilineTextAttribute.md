# Game.Settings.SettingsUIMultilineTextAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIMultilineTextAttribute : System.Attribute
{
    public readonly System.String icon;

    public SettingsUIMultilineTextAttribute(System.String icon);

}
```


## Fields

- `public readonly System.String icon`  

```csharp
public readonly System.String icon;
```


## Constructors

- `public SettingsUIMultilineTextAttribute(System.String icon = null)`  

```csharp
public SettingsUIMultilineTextAttribute(string icon = null)
	{
		this.icon = icon;
	}
```


