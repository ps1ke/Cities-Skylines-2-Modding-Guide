# Game.Settings.SettingsUIDropdownAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIDropdownAttribute : System.Attribute
{
    public readonly System.Type itemsGetterType;
    public readonly System.String itemsGetterMethod;

    public SettingsUIDropdownAttribute(System.Type itemsGetterType, System.String itemsGetterMethod);

}
```


## Fields

- `public readonly System.Type itemsGetterType`  

```csharp
public readonly System.Type itemsGetterType;
```

- `public readonly System.String itemsGetterMethod`  

```csharp
public readonly System.String itemsGetterMethod;
```


## Constructors

- `public SettingsUIDropdownAttribute(System.Type itemsGetterType, System.String itemsGetterMethod)`  

```csharp
public SettingsUIDropdownAttribute(System.Type itemsGetterType, System.String itemsGetterMethod);
```


