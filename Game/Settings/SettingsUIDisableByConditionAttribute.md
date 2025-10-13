# Game.Settings.SettingsUIDisableByConditionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIDisableByConditionAttribute : System.Attribute
{
    public readonly System.Type checkType;
    public readonly System.String checkMethod;
    public readonly System.Boolean invert;

    public SettingsUIDisableByConditionAttribute(System.Type checkType, System.String checkMethod);
    public SettingsUIDisableByConditionAttribute(System.Type checkType, System.String checkMethod, System.Boolean invert);

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

- `public readonly System.Boolean invert`  

```csharp
public readonly System.Boolean invert;
```


## Constructors

- `public SettingsUIDisableByConditionAttribute(System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUIDisableByConditionAttribute(Type checkType, string checkMethod, bool invert)
	{
		this.checkType = checkType;
		this.checkMethod = checkMethod;
		this.invert = invert;
	}
```

- `public SettingsUIDisableByConditionAttribute(System.Type checkType, System.String checkMethod, System.Boolean invert)`  

```csharp
public SettingsUIDisableByConditionAttribute(Type checkType, string checkMethod, bool invert)
	{
		this.checkType = checkType;
		this.checkMethod = checkMethod;
		this.invert = invert;
	}
```


