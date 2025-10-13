# Game.Settings.SettingsUIGroupOrderAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIGroupOrderAttribute : System.Attribute
{
    public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> groups;
    public readonly System.Type checkType;
    public readonly System.String checkMethod;

    public SettingsUIGroupOrderAttribute(System.String[] groups);
    public SettingsUIGroupOrderAttribute(System.Type checkType, System.String checkMethod);

}
```


## Fields

- `public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> groups`  

```csharp
public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> groups;
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

- `public SettingsUIGroupOrderAttribute(System.String[] groups)`  

```csharp
public SettingsUIGroupOrderAttribute(System.String[] groups);
```

- `public SettingsUIGroupOrderAttribute(System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUIGroupOrderAttribute(System.Type checkType, System.String checkMethod);
```


