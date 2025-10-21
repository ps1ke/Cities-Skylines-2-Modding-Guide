# Game.Settings.SettingsUIHideByConditionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIHideByConditionAttribute : System.Attribute
{
    public readonly System.Type checkType;
    public readonly System.String checkMethod;
    public readonly System.Boolean invert;

    public SettingsUIHideByConditionAttribute(System.Type checkType, System.String checkMethod);
    public SettingsUIHideByConditionAttribute(System.Type checkType, System.String checkMethod, System.Boolean invert);

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

- `public SettingsUIHideByConditionAttribute(System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUIHideByConditionAttribute(System.Type checkType, System.String checkMethod);
```

- `public SettingsUIHideByConditionAttribute(System.Type checkType, System.String checkMethod, System.Boolean invert)`  

```csharp
public SettingsUIHideByConditionAttribute(System.Type checkType, System.String checkMethod, System.Boolean invert);
```


