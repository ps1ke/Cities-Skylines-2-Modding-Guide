# Game.Settings.Setting

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public abstract class Setting : System.IEquatable<Game.Settings.Setting>
{
    private Game.Settings.OnSettingsAppliedHandler onSettingsApplied;
    protected static Colossal.Logging.ILog log;

    protected static Game.Settings.SharedSettings settings { protected get; }
    private System.Boolean builtIn { private get; }

    protected Setting();

    public virtual System.Void Apply();
    public System.Void ApplyAndSave();
    public System.Boolean Equals(Game.Settings.Setting obj);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    internal System.Void RegisterInOptionsUI(System.String name, System.Boolean addPrefix);
    internal static System.Boolean RegisterInOptionsUI(Game.Settings.Setting instance, System.String name, System.Boolean addPrefix);
    public abstract System.Void SetDefaults();
    protected System.Boolean TryGetGameplayCamera(UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData& cameraData);
    protected System.Boolean TryGetGameplayCamera(UnityEngine.Camera& camera);
    protected System.Boolean TryGetGameplayCameraController(Game.CameraController& controller);
    protected System.Boolean TryGetSunLight(UnityEngine.Light& sunLight);
    protected System.Boolean TryGetSunLightData(UnityEngine.Rendering.HighDefinition.HDAdditionalLightData& sunLightData);
    internal static System.Boolean UnregisterInOptionsUI(System.String name);
}
```


## Fields

- `private Game.Settings.OnSettingsAppliedHandler onSettingsApplied`  

```csharp
private Game.Settings.OnSettingsAppliedHandler onSettingsApplied;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```


## Properties

- `protected static Game.Settings.SharedSettings settings { protected get }`  

```csharp
protected static Game.Settings.SharedSettings settings { protected get; }
```

- `private System.Boolean builtIn { private get }`  

```csharp
private System.Boolean builtIn { private get; }
```


## Constructors

- `protected Setting()`  

```csharp
protected Setting();
```


## Methods

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `public ApplyAndSave() : System.Void`  

```csharp
public System.Void ApplyAndSave();
```

- `public Equals(Game.Settings.Setting obj) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Settings.Setting obj);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
```

- `internal RegisterInOptionsUI(System.String name, System.Boolean addPrefix = False) : System.Void`  

```csharp
internal System.Void RegisterInOptionsUI(System.String name, System.Boolean addPrefix);
```

- `internal static RegisterInOptionsUI(Game.Settings.Setting instance, System.String name, System.Boolean addPrefix) : System.Boolean`  

```csharp
internal static System.Boolean RegisterInOptionsUI(Game.Settings.Setting instance, System.String name, System.Boolean addPrefix);
```

- `public abstract SetDefaults() : System.Void`  

```csharp
public abstract System.Void SetDefaults();
```

- `protected TryGetGameplayCamera(UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData& cameraData) : System.Boolean`  

```csharp
protected System.Boolean TryGetGameplayCamera(UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData& cameraData);
```

- `protected TryGetGameplayCamera(UnityEngine.Camera& camera) : System.Boolean`  

```csharp
protected System.Boolean TryGetGameplayCamera(UnityEngine.Camera& camera);
```

- `protected TryGetGameplayCameraController(Game.CameraController& controller) : System.Boolean`  

```csharp
protected System.Boolean TryGetGameplayCameraController(Game.CameraController& controller);
```

- `protected TryGetSunLight(UnityEngine.Light& sunLight) : System.Boolean`  

```csharp
protected System.Boolean TryGetSunLight(UnityEngine.Light& sunLight);
```

- `protected TryGetSunLightData(UnityEngine.Rendering.HighDefinition.HDAdditionalLightData& sunLightData) : System.Boolean`  

```csharp
protected System.Boolean TryGetSunLightData(UnityEngine.Rendering.HighDefinition.HDAdditionalLightData& sunLightData);
```

- `internal static UnregisterInOptionsUI(System.String name) : System.Boolean`  

```csharp
internal static System.Boolean UnregisterInOptionsUI(System.String name);
```


## Events

- `onSettingsApplied` : `Game.Settings.OnSettingsAppliedHandler`  

```csharp
public event Game.Settings.OnSettingsAppliedHandler onSettingsApplied;
```


## Nested types

- `Game.Settings.Setting+<ApplyAndSave>d__16`  

