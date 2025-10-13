# Game.Settings.SettingsUISectionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUISectionAttribute : System.Attribute
{
    public readonly System.String tab;
    public readonly System.String simpleGroup;
    public readonly System.String advancedGroup;
    public static const System.String kGeneral;

    public SettingsUISectionAttribute(System.String tab, System.String simpleGroup, System.String advancedGroup);
    public SettingsUISectionAttribute(System.String tab, System.String group);
    public SettingsUISectionAttribute(System.String group);

}
```


## Fields

- `public readonly System.String tab`  

```csharp
public readonly System.String tab;
```

- `public readonly System.String simpleGroup`  

```csharp
public readonly System.String simpleGroup;
```

- `public readonly System.String advancedGroup`  

```csharp
public readonly System.String advancedGroup;
```

- `public static const System.String kGeneral`  

```csharp
public static const System.String kGeneral;
```


## Constructors

- `public SettingsUISectionAttribute(System.String tab, System.String simpleGroup, System.String advancedGroup)`  

```csharp
public SettingsUISectionAttribute(System.String tab, System.String simpleGroup, System.String advancedGroup);
```

- `public SettingsUISectionAttribute(System.String tab, System.String group)`  

```csharp
public SettingsUISectionAttribute(System.String tab, System.String group);
```

- `public SettingsUISectionAttribute(System.String group)`  

```csharp
public SettingsUISectionAttribute(System.String group);
```


