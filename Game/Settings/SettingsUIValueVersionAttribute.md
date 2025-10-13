# Game.Settings.SettingsUIValueVersionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIValueVersionAttribute : System.Attribute
{
    public readonly System.Type versionGetterType;
    public readonly System.String versionGetterMethod;

    public SettingsUIValueVersionAttribute(System.Type versionGetterType, System.String versionGetterMethod);

}
```


## Fields

- `public readonly System.Type versionGetterType`  

```csharp
public readonly System.Type versionGetterType;
```

- `public readonly System.String versionGetterMethod`  

```csharp
public readonly System.String versionGetterMethod;
```


## Constructors

- `public SettingsUIValueVersionAttribute(System.Type versionGetterType, System.String versionGetterMethod)`  

```csharp
public SettingsUIValueVersionAttribute(Type versionGetterType, string versionGetterMethod)
	{
		this.versionGetterType = versionGetterType;
		this.versionGetterMethod = versionGetterMethod;
	}
```


