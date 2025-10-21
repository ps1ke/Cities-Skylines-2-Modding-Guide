# Game.Settings.SettingsUIConfirmationAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

## Code

```csharp
public class SettingsUIConfirmationAttribute : System.Attribute
{
    public readonly System.String confirmMessageValue;
    public readonly System.String confirmMessageId;

    public SettingsUIConfirmationAttribute(System.String overrideConfirmMessageId, System.String overrideConfirmMessageValue);

}
```


## Fields

- `public readonly System.String confirmMessageValue`  

```csharp
public readonly System.String confirmMessageValue;
```

- `public readonly System.String confirmMessageId`  

```csharp
public readonly System.String confirmMessageId;
```


## Constructors

- `public SettingsUIConfirmationAttribute(System.String overrideConfirmMessageId = null, System.String overrideConfirmMessageValue = null)`  

```csharp
public SettingsUIConfirmationAttribute(System.String overrideConfirmMessageId, System.String overrideConfirmMessageValue);
```


