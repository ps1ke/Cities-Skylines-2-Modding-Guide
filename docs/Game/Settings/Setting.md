# Game.Settings.Setting

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Fields

- `private Game.Settings.OnSettingsAppliedHandler onSettingsApplied`  
- `protected static Colossal.Logging.ILog log`  

## Properties

- `protected static Game.Settings.SharedSettings settings { protected get }`  
- `private System.Boolean builtIn { private get }`  

## Constructors

- `protected Setting()`  

## Methods

- `public virtual Apply() : System.Void`  
- `public ApplyAndSave() : System.Void`  
- `public Equals(Game.Settings.Setting obj) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  
- `internal RegisterInOptionsUI(System.String name, System.Boolean addPrefix = False) : System.Void`  
- `internal static RegisterInOptionsUI(Game.Settings.Setting instance, System.String name, System.Boolean addPrefix) : System.Boolean`  
- `public abstract SetDefaults() : System.Void`  
- `protected TryGetGameplayCamera(UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData& cameraData) : System.Boolean`  
- `protected TryGetGameplayCamera(UnityEngine.Camera& camera) : System.Boolean`  
- `protected TryGetGameplayCameraController(Game.CameraController& controller) : System.Boolean`  
- `protected TryGetSunLight(UnityEngine.Light& sunLight) : System.Boolean`  
- `protected TryGetSunLightData(UnityEngine.Rendering.HighDefinition.HDAdditionalLightData& sunLightData) : System.Boolean`  
- `internal static UnregisterInOptionsUI(System.String name) : System.Boolean`  

## Events

- `onSettingsApplied` : `Game.Settings.OnSettingsAppliedHandler`  

## Nested types

- `Game.Settings.Setting+<ApplyAndSave>d__16`  

