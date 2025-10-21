# Game.Settings.SettingsUITabOrderAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUITabOrderAttribute : System.Attribute
{
    public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> tabs;
    public readonly System.Type checkType;
    public readonly System.String checkMethod;

    public SettingsUITabOrderAttribute(System.String[] tabs);
    public SettingsUITabOrderAttribute(System.Type checkType, System.String checkMethod);

}
```


## Fields

- `public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> tabs`  

```csharp
public readonly System.Collections.ObjectModel.ReadOnlyCollection<System.String> tabs;
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

- `public SettingsUITabOrderAttribute(System.String[] tabs)`  

```csharp
public SettingsUITabOrderAttribute(System.String[] tabs);
```

- `public SettingsUITabOrderAttribute(System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUITabOrderAttribute(System.Type checkType, System.String checkMethod);
```


