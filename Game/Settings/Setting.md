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
public virtual void Apply()
	{
		log.VerboseFormat("Applying settings for {0}", GetType());
		this.onSettingsApplied?.Invoke(this);
	}
```

- `public ApplyAndSave() : System.Void`  

```csharp
public async void ApplyAndSave()
	{
		Apply();
		await AssetDatabase.global.SaveSettings();
	}
```

- `public Equals(Game.Settings.Setting obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj == null)
		{
			return false;
		}
		if (this == obj)
		{
			return true;
		}
		Type type = obj.GetType();
		if (!type.IsAssignableFrom(GetType()))
		{
			return false;
		}
		PropertyInfo property = type.GetProperty("enabled", BindingFlags.Instance | BindingFlags.Public);
		if (property != null && !(bool)property.GetValue(this) && object.Equals(property.GetValue(this), property.GetValue(obj)))
		{
			return true;
		}
		PropertyInfo[] properties = type.GetProperties(BindingFlags.Instance | BindingFlags.Public);
		foreach (PropertyInfo propertyInfo in properties)
		{
			if (ReflectionUtils.GetAttribute<IgnoreEqualsAttribute>(propertyInfo.GetCustomAttributes(inherit: false)) == null && propertyInfo.CanRead && !object.Equals(propertyInfo.GetValue(this), propertyInfo.GetValue(obj)))
			{
				return false;
			}
		}
		return true;
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj == null)
		{
			return false;
		}
		if (this == obj)
		{
			return true;
		}
		Type type = obj.GetType();
		if (!type.IsAssignableFrom(GetType()))
		{
			return false;
		}
		PropertyInfo property = type.GetProperty("enabled", BindingFlags.Instance | BindingFlags.Public);
		if (property != null && !(bool)property.GetValue(this) && object.Equals(property.GetValue(this), property.GetValue(obj)))
		{
			return true;
		}
		PropertyInfo[] properties = type.GetProperties(BindingFlags.Instance | BindingFlags.Public);
		foreach (PropertyInfo propertyInfo in properties)
		{
			if (ReflectionUtils.GetAttribute<IgnoreEqualsAttribute>(propertyInfo.GetCustomAttributes(inherit: false)) == null && propertyInfo.CanRead && !object.Equals(propertyInfo.GetValue(this), propertyInfo.GetValue(obj)))
			{
				return false;
			}
		}
		return true;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		int num = 0;
		PropertyInfo[] properties = GetType().GetProperties(BindingFlags.Instance | BindingFlags.Public);
		foreach (PropertyInfo propertyInfo in properties)
		{
			num = (num * 937) ^ propertyInfo.GetValue(this).GetHashCode();
		}
		return num;
	}
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public virtual AutomaticSettings.SettingPageData GetPageData(string id, bool addPrefix)
	{
		return AutomaticSettings.FillSettingsPage(this, id, addPrefix);
	}
```

- `internal RegisterInOptionsUI(System.String name, System.Boolean addPrefix = False) : System.Void`  

```csharp
internal static bool RegisterInOptionsUI(Setting instance, string name, bool addPrefix)
	{
		OptionsUISystem optionsUISystem = World.DefaultGameObjectInjectionWorld?.GetOrCreateSystemManaged<OptionsUISystem>();
		if (optionsUISystem != null)
		{
			optionsUISystem.RegisterSetting(instance, name, addPrefix);
			return true;
		}
		return false;
	}
```

- `internal static RegisterInOptionsUI(Game.Settings.Setting instance, System.String name, System.Boolean addPrefix) : System.Boolean`  

```csharp
internal static bool RegisterInOptionsUI(Setting instance, string name, bool addPrefix)
	{
		OptionsUISystem optionsUISystem = World.DefaultGameObjectInjectionWorld?.GetOrCreateSystemManaged<OptionsUISystem>();
		if (optionsUISystem != null)
		{
			optionsUISystem.RegisterSetting(instance, name, addPrefix);
			return true;
		}
		return false;
	}
```

- `public abstract SetDefaults() : System.Void`  

```csharp
public abstract System.Void SetDefaults();
```

- `protected TryGetGameplayCamera(UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData& cameraData) : System.Boolean`  

```csharp
protected bool TryGetGameplayCamera(ref Camera camera)
	{
		if (camera != null)
		{
			return true;
		}
		camera = Camera.main;
		if (camera != null)
		{
			return true;
		}
		return false;
	}
```

- `protected TryGetGameplayCamera(UnityEngine.Camera& camera) : System.Boolean`  

```csharp
protected bool TryGetGameplayCamera(ref Camera camera)
	{
		if (camera != null)
		{
			return true;
		}
		camera = Camera.main;
		if (camera != null)
		{
			return true;
		}
		return false;
	}
```

- `protected TryGetGameplayCameraController(Game.CameraController& controller) : System.Boolean`  

```csharp
protected bool TryGetGameplayCameraController(ref CameraController controller)
	{
		if (controller != null)
		{
			return true;
		}
		GameObject gameObject = GameObject.FindGameObjectWithTag("GameplayCamera");
		if (gameObject != null)
		{
			controller = gameObject.GetComponent<CameraController>();
			return true;
		}
		controller = null;
		return false;
	}
```

- `protected TryGetSunLight(UnityEngine.Light& sunLight) : System.Boolean`  

```csharp
protected bool TryGetSunLight(ref Light sunLight)
	{
		if (sunLight != null)
		{
			return true;
		}
		GameObject gameObject = GameObject.FindGameObjectWithTag("SunLight");
		if (gameObject != null)
		{
			sunLight = gameObject.GetComponent<Light>();
			return true;
		}
		sunLight = null;
		return false;
	}
```

- `protected TryGetSunLightData(UnityEngine.Rendering.HighDefinition.HDAdditionalLightData& sunLightData) : System.Boolean`  

```csharp
protected bool TryGetSunLightData(ref HDAdditionalLightData sunLightData)
	{
		if (sunLightData != null)
		{
			return true;
		}
		GameObject gameObject = GameObject.FindGameObjectWithTag("SunLight");
		if (gameObject != null)
		{
			sunLightData = gameObject.GetComponent<HDAdditionalLightData>();
			return true;
		}
		sunLightData = null;
		return false;
	}
```

- `internal static UnregisterInOptionsUI(System.String name) : System.Boolean`  

```csharp
internal static bool UnregisterInOptionsUI(string name)
	{
		OptionsUISystem optionsUISystem = World.DefaultGameObjectInjectionWorld?.GetOrCreateSystemManaged<OptionsUISystem>();
		if (optionsUISystem != null)
		{
			optionsUISystem.UnregisterSettings(name);
			return true;
		}
		return false;
	}
```


## Events

- `onSettingsApplied` : `Game.Settings.OnSettingsAppliedHandler`  

```csharp
public event Game.Settings.OnSettingsAppliedHandler onSettingsApplied;
```


## Nested types

- `Game.Settings.Setting+<ApplyAndSave>d__16`  

