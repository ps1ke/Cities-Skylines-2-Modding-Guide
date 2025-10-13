# Game.Settings.SettingsUIWarningAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIWarningAttribute : System.Attribute
{
    public readonly System.Type checkType;
    public readonly System.String checkMethod;

    public SettingsUIWarningAttribute(System.Type checkType, System.String checkMethod);

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

- `public SettingsUIWarningAttribute(System.Type checkType, System.String checkMethod)`  

```csharp
public SettingsUIWarningAttribute(System.Type checkType, System.String checkMethod);
```


