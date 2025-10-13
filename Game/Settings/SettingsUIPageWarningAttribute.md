# Game.Settings.SettingsUIPageWarningAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIPageWarningAttribute : System.Attribute
{
    public readonly System.Type checkType;
    public readonly System.String checkMethod;

    public SettingsUIPageWarningAttribute(System.Type checkType, System.String checkMethod);

}
```


## Fields

- `public readonly System.Type checkType`  

```csharp
public readonly System.Type checkType;
```

- `public readonly System.String checkMethod`  

```csharp
public readonly System.String checkMethod;
```


## Constructors

- `public SettingsUIPageWarningAttribute(System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUIPageWarningAttribute(Type checkType, string checkMethod)
	{
		this.checkType = checkType;
		this.checkMethod = checkMethod;
	}
```


