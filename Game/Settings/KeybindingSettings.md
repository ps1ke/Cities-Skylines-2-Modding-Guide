# Game.Settings.KeybindingSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Code

```csharp
public class KeybindingSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean m_IsDefault;

    public System.Collections.Generic.List<Game.Input.ProxyBinding> bindings { get; set; }

    public KeybindingSettings(System.Boolean isDefault);

    public virtual System.Void SetDefaults();
}
```


## Fields

- `private System.Boolean m_IsDefault`  

```csharp
private System.Boolean m_IsDefault;
```


## Properties

- `public System.Collections.Generic.List<Game.Input.ProxyBinding> bindings { get; set }`  

```csharp
public System.Collections.Generic.List<Game.Input.ProxyBinding> bindings { get; set; }
```


## Constructors

- `public KeybindingSettings(System.Boolean isDefault = False)`  

```csharp
public KeybindingSettings(System.Boolean isDefault);
```


## Methods

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```


