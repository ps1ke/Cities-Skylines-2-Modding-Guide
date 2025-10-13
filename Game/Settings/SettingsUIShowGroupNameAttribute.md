# Game.Settings.SettingsUIShowGroupNameAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIShowGroupNameAttribute : System.Attribute
{
    public readonly System.Boolean showAll;
    public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> groups;

    public SettingsUIShowGroupNameAttribute();
    public SettingsUIShowGroupNameAttribute(System.String[] groups);

}
```


## Fields

- `public readonly System.Boolean showAll`  

```csharp
public readonly System.Boolean showAll;
```

- `public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> groups`  

```csharp
public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> groups;
```


## Constructors

- `public SettingsUIShowGroupNameAttribute()`  

```csharp
public SettingsUIShowGroupNameAttribute(params string[] groups)
	{
		this.groups = new ReadOnlyCollection<string>(groups);
	}
```

- `public SettingsUIShowGroupNameAttribute(System.String[] groups)`  

```csharp
public SettingsUIShowGroupNameAttribute(params string[] groups)
	{
		this.groups = new ReadOnlyCollection<string>(groups);
	}
```


