# Game.Settings.GameplaySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Code

```csharp
public class GameplaySettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private Game.CameraController m_CameraController;
    private System.Boolean <edgeScrolling>k__BackingField;
    private System.Single <edgeScrollingSensitivity>k__BackingField;
    private System.Boolean <dayNightVisual>k__BackingField;
    private System.Boolean <pausedAfterLoading>k__BackingField;
    private System.Boolean <showTutorials>k__BackingField;
    public static const System.String kName;

    public System.Boolean edgeScrolling { get; set; }
    public System.Single edgeScrollingSensitivity { get; set; }
    public System.Boolean dayNightVisual { get; set; }
    public System.Boolean pausedAfterLoading { get; set; }
    public System.Boolean showTutorials { get; set; }
    public System.Boolean resetTutorials { set; }

    public GameplaySettings();

    public virtual System.Void Apply();
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private Game.CameraController m_CameraController`  

```csharp
private Game.CameraController m_CameraController;
```

- `private System.Boolean <edgeScrolling>k__BackingField`  

```csharp
private System.Boolean <edgeScrolling>k__BackingField;
```

- `private System.Single <edgeScrollingSensitivity>k__BackingField`  

```csharp
private System.Single <edgeScrollingSensitivity>k__BackingField;
```

- `private System.Boolean <dayNightVisual>k__BackingField`  

```csharp
private System.Boolean <dayNightVisual>k__BackingField;
```

- `private System.Boolean <pausedAfterLoading>k__BackingField`  

```csharp
private System.Boolean <pausedAfterLoading>k__BackingField;
```

- `private System.Boolean <showTutorials>k__BackingField`  

```csharp
private System.Boolean <showTutorials>k__BackingField;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```


## Properties

- `public System.Boolean edgeScrolling { get; set }`  

```csharp
public System.Boolean edgeScrolling { get; set; }
```

- `public System.Single edgeScrollingSensitivity { get; set }`  

```csharp
public System.Single edgeScrollingSensitivity { get; set; }
```

- `public System.Boolean dayNightVisual { get; set }`  

```csharp
public System.Boolean dayNightVisual { get; set; }
```

- `public System.Boolean pausedAfterLoading { get; set }`  

```csharp
public System.Boolean pausedAfterLoading { get; set; }
```

- `public System.Boolean showTutorials { get; set }`  

```csharp
public System.Boolean showTutorials { get; set; }
```

- `public System.Boolean resetTutorials { set }`  

```csharp
public System.Boolean resetTutorials { set; }
```


## Constructors

- `public GameplaySettings()`  

```csharp
public GameplaySettings();
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```


