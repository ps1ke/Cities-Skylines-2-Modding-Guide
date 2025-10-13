# Game.Settings.SettingsUIDescriptionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIDescriptionAttribute : System.Attribute
{
    public readonly System.String id;
    public readonly System.String value;
    public readonly System.Type getterType;
    public readonly System.String getterMethod;

    public SettingsUIDescriptionAttribute(System.String overrideId, System.String overrideValue);
    public SettingsUIDescriptionAttribute(System.Type getterType, System.String getterMethod);

}
```


## Fields

- `public readonly System.String id`  

```csharp
public readonly System.String id;
```

- `public readonly System.String value`  

```csharp
public readonly System.String value;
```

- `public readonly System.Type getterType`  

```csharp
public readonly System.Type getterType;
```

- `public readonly System.String getterMethod`  

```csharp
public readonly System.String getterMethod;
```


## Constructors

- `public SettingsUIDescriptionAttribute(System.String overrideId = null, System.String overrideValue = null)`  

```csharp
public SettingsUIDescriptionAttribute(System.String overrideId, System.String overrideValue);
```

- `public SettingsUIDescriptionAttribute(System.Type getterType, System.String getterMethod)`  

```csharp
public SettingsUIDescriptionAttribute(System.Type getterType, System.String getterMethod);
```


