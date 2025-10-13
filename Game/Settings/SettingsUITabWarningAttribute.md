# Game.Settings.SettingsUITabWarningAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUITabWarningAttribute : System.Attribute
{
    public readonly System.String tab;
    public readonly System.Type checkType;
    public readonly System.String checkMethod;

    public SettingsUITabWarningAttribute(System.String tab, System.Type checkType, System.String checkMethod);

}
```


## Fields

- `public readonly System.String tab`  

```csharp
public readonly System.String tab;
```

- `public readonly System.Type checkType`  

```csharp
public readonly System.Type checkType;
```

- `public readonly System.String checkMethod`  

```csharp
public readonly System.String checkMethod;
```


## Constructors

- `public SettingsUITabWarningAttribute(System.String tab, System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUITabWarningAttribute(string tab, Type checkType, string checkMethod)
	{
		this.tab = tab;
		this.checkType = checkType;
		this.checkMethod = checkMethod;
	}
```


