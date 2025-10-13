# Game.Settings.GlobalQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.GlobalQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public class GlobalQualitySettings : Game.Settings.QualitySetting<Game.Settings.GlobalQualitySettings>, System.IEquatable<Game.Settings.Setting>
{
    private System.Collections.Generic.List<Game.Settings.QualitySetting> m_QualitySettings;
    protected static readonly System.Collections.Generic.Dictionary<System.Type, Game.Settings.QualitySetting+Level> s_DefaultsMap;

    public System.Collections.Generic.List<Game.Settings.QualitySetting> qualitySettings { get; set; }
    public System.Int32 countQualitySettings { get; }
    public Game.Settings.QualitySetting lastSetting { get; }

    public GlobalQualitySettings();

    public System.Void AddQualitySetting<T>(T setting);
    public System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting> EnumerateQualitySettings();
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public T GetQualitySetting<T>();
    public Game.Settings.QualitySetting GetQualitySetting(System.Type type);
    public virtual System.Void SetDefaults();
    public virtual System.Void SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply);
}
```


## Fields

- `private System.Collections.Generic.List<Game.Settings.QualitySetting> m_QualitySettings`  

```csharp
private System.Collections.Generic.List<Game.Settings.QualitySetting> m_QualitySettings;
```

- `protected static readonly System.Collections.Generic.Dictionary<System.Type, Game.Settings.QualitySetting+Level> s_DefaultsMap`  

```csharp
protected static readonly System.Collections.Generic.Dictionary<System.Type, Game.Settings.QualitySetting+Level> s_DefaultsMap;
```


## Properties

- `public System.Collections.Generic.List<Game.Settings.QualitySetting> qualitySettings { get; set }`  

```csharp
public System.Collections.Generic.List<Game.Settings.QualitySetting> qualitySettings { get; set; }
```

- `public System.Int32 countQualitySettings { get }`  

```csharp
public System.Int32 countQualitySettings { get; }
```

- `public Game.Settings.QualitySetting lastSetting { get }`  

```csharp
public Game.Settings.QualitySetting lastSetting { get; }
```


## Constructors

- `public GlobalQualitySettings()`  

```csharp
public GlobalQualitySettings();
```


## Methods

- `public AddQualitySetting<T>(T setting) : System.Void`  

```csharp
public System.Void AddQualitySetting<T>(T setting);
```

- `public EnumerateQualitySettings() : System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting>`  

```csharp
public IEnumerable<QualitySetting> EnumerateQualitySettings()
	{
		foreach (QualitySetting qualitySetting in m_QualitySettings)
		{
			yield return qualitySetting;
		}
	}
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (!(obj is GlobalQualitySettings globalQualitySettings))
		{
			return false;
		}
		bool result = base.Equals(obj);
		for (int i = 0; i < m_QualitySettings.Count; i++)
		{
			if (!m_QualitySettings[i].Equals(globalQualitySettings.m_QualitySettings[i]))
			{
				return false;
			}
		}
		return result;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		int num = base.GetHashCode();
		foreach (QualitySetting item in EnumerateQualitySettings())
		{
			num = (num * 937) ^ item.GetHashCode();
		}
		return num;
	}
```

- `public GetQualitySetting<T>() : T`  

```csharp
public T GetQualitySetting<T>();
```

- `public GetQualitySetting(System.Type type) : Game.Settings.QualitySetting`  

```csharp
public QualitySetting GetQualitySetting(Type type)
	{
		foreach (QualitySetting qualitySetting in m_QualitySettings)
		{
			if (qualitySetting.GetType() == type)
			{
				return qualitySetting;
			}
		}
		return null;
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
		foreach (QualitySetting item in EnumerateQualitySettings())
		{
			item.SetLevel(s_DefaultsMap[item.GetType()], apply: false);
		}
	}
```

- `public virtual SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply = True) : System.Void`  

```csharp
public override void SetLevel(Level quality, bool apply = true)
	{
		if (quality < Level.Custom)
		{
			for (int i = 0; i < m_QualitySettings.Count; i++)
			{
				m_QualitySettings[i].TransferValuesFrom(QualitySetting<GlobalQualitySettings>.s_SettingsMap[quality].m_QualitySettings[i]);
			}
			if (apply)
			{
				ApplyAndSave();
			}
		}
	}
```


## Nested types

- `Game.Settings.GlobalQualitySettings+<>c__DisplayClass3_0`  
- `Game.Settings.GlobalQualitySettings+<EnumerateQualitySettings>d__11`  

