# Game.UI.Editor.LocalizationField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class LocalizationField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization;
    private Game.UI.Localization.LocalizedString <placeholder>k__BackingField;

    public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get; }
    public Game.UI.Localization.LocalizedString placeholder { get; set; }

    public LocalizationField(Game.UI.Localization.LocalizedString placeholder);

    public System.Void Add(Colossal.IO.AssetDatabase.LocaleAsset asset, System.String localeFormat);
    public System.Void Add(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry);
    public System.Void AddLanguage();
    public System.Void BuildLocaleData(System.String format, System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.LocaleData> localeDatas, System.String fallback);
    public System.Void Clear();
    public System.Void Initialize();
    public System.Void Initialize(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> assets, System.String localeFormat);
    public System.Void Initialize(System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> entries);
    private System.Void InitializeMandatory();
    public static System.Boolean IsMandatory(System.String localeId);
    public System.Boolean IsValid();
    private System.Boolean IsValid(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry);
    public System.Void RemoveLanguage(System.Int32 index);
    public System.Void SetEntry(System.Int32 index, System.String localeId, System.String text);
    private System.Boolean TryGetUnusedLanguage(System.String& localeID);
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> ValidEntries();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization;
```

- `private Game.UI.Localization.LocalizedString <placeholder>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <placeholder>k__BackingField;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get; }
```

- `public Game.UI.Localization.LocalizedString placeholder { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString placeholder { get; set; }
```


## Constructors

- `public LocalizationField(Game.UI.Localization.LocalizedString placeholder)`  

```csharp
public LocalizationField(LocalizedString placeholder)
	{
		this.placeholder = placeholder;
		Initialize();
	}
```


## Methods

- `public Add(Colossal.IO.AssetDatabase.LocaleAsset asset, System.String localeFormat) : System.Void`  

```csharp
public void Add(LocalizationFieldEntry entry)
	{
		int num = m_Localization.FindIndex((LocalizationFieldEntry loc) => loc.localeId == entry.localeId);
		if (num < 0)
		{
			m_Localization.Add(entry);
		}
		else
		{
			m_Localization[num] = entry;
		}
	}
```

- `public Add(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry) : System.Void`  

```csharp
public void Add(LocalizationFieldEntry entry)
	{
		int num = m_Localization.FindIndex((LocalizationFieldEntry loc) => loc.localeId == entry.localeId);
		if (num < 0)
		{
			m_Localization.Add(entry);
		}
		else
		{
			m_Localization[num] = entry;
		}
	}
```

- `public AddLanguage() : System.Void`  

```csharp
public void AddLanguage()
	{
		if (TryGetUnusedLanguage(out var localeID))
		{
			m_Localization.Add(new LocalizationFieldEntry
			{
				localeId = localeID,
				text = string.Empty
			});
		}
		SetPropertiesChanged();
	}
```

- `public BuildLocaleData(System.String format, System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.LocaleData> localeDatas, System.String fallback = null) : System.Void`  

```csharp
public void BuildLocaleData(string format, Dictionary<string, LocaleData> localeDatas, string fallback = null)
	{
		foreach (LocalizationFieldEntry item in m_Localization)
		{
			if (IsValid(item))
			{
				if (!localeDatas.ContainsKey(item.localeId))
				{
					localeDatas[item.localeId] = new LocaleData(item.localeId, new Dictionary<string, string>(), new Dictionary<string, int>());
				}
				localeDatas[item.localeId].entries[format] = item.text;
			}
		}
		if (fallback != null)
		{
			string fallbackLocaleId = GameManager.instance.localizationManager.fallbackLocaleId;
			if (!localeDatas.ContainsKey(fallbackLocaleId))
			{
				localeDatas[fallbackLocaleId] = new LocaleData(fallbackLocaleId, new Dictionary<string, string>(), new Dictionary<string, int>());
			}
			localeDatas[fallbackLocaleId].entries.TryAdd(format, fallback);
		}
	}
```

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		m_Localization.Clear();
	}
```

- `public Initialize() : System.Void`  

```csharp
public void Initialize(IEnumerable<LocalizationFieldEntry> entries)
	{
		Clear();
		InitializeMandatory();
		foreach (LocalizationFieldEntry entry in entries)
		{
			Add(entry);
		}
	}
```

- `public Initialize(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> assets, System.String localeFormat) : System.Void`  

```csharp
public void Initialize(IEnumerable<LocalizationFieldEntry> entries)
	{
		Clear();
		InitializeMandatory();
		foreach (LocalizationFieldEntry entry in entries)
		{
			Add(entry);
		}
	}
```

- `public Initialize(System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> entries) : System.Void`  

```csharp
public void Initialize(IEnumerable<LocalizationFieldEntry> entries)
	{
		Clear();
		InitializeMandatory();
		foreach (LocalizationFieldEntry entry in entries)
		{
			Add(entry);
		}
	}
```

- `private InitializeMandatory() : System.Void`  

```csharp
private void InitializeMandatory()
	{
		if (!string.IsNullOrEmpty(GameManager.instance.localizationManager.fallbackLocaleId))
		{
			int num = m_Localization.FindIndex((LocalizationFieldEntry l) => IsMandatory(l.localeId));
			if (num < 0)
			{
				m_Localization.Add(new LocalizationFieldEntry
				{
					localeId = GameManager.instance.localizationManager.fallbackLocaleId,
					text = string.Empty
				});
			}
			else if (num > 0)
			{
				List<LocalizationFieldEntry> list = m_Localization;
				List<LocalizationFieldEntry> list2 = m_Localization;
				int index = num;
				LocalizationFieldEntry localizationFieldEntry = m_Localization[num];
				LocalizationFieldEntry localizationFieldEntry2 = m_Localization[0];
				LocalizationFieldEntry localizationFieldEntry3 = (list[0] = localizationFieldEntry);
				localizationFieldEntry3 = (list2[index] = localizationFieldEntry2);
			}
		}
	}
```

- `public static IsMandatory(System.String localeId) : System.Boolean`  

```csharp
public static bool IsMandatory(string localeId)
	{
		return localeId == GameManager.instance.localizationManager.fallbackLocaleId;
	}
```

- `public IsValid() : System.Boolean`  

```csharp
private bool IsValid(LocalizationFieldEntry entry)
	{
		return !string.IsNullOrWhiteSpace(entry.text);
	}
```

- `private IsValid(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry) : System.Boolean`  

```csharp
private bool IsValid(LocalizationFieldEntry entry)
	{
		return !string.IsNullOrWhiteSpace(entry.text);
	}
```

- `public RemoveLanguage(System.Int32 index) : System.Void`  

```csharp
public void RemoveLanguage(int index)
	{
		if (IsMandatory(m_Localization[index].localeId))
		{
			LocalizationFieldEntry value = m_Localization[index];
			value.text = string.Empty;
			m_Localization[index] = value;
		}
		else
		{
			m_Localization.RemoveAt(index);
		}
		SetPropertiesChanged();
	}
```

- `public SetEntry(System.Int32 index, System.String localeId, System.String text) : System.Void`  

```csharp
public void SetEntry(int index, string localeId, string text)
	{
		LocalizationFieldEntry value = m_Localization[index];
		value.localeId = localeId;
		value.text = text;
		m_Localization[index] = value;
		SetPropertiesChanged();
	}
```

- `private TryGetUnusedLanguage(System.String& localeID) : System.Boolean`  

```csharp
private bool TryGetUnusedLanguage(out string localeID)
	{
		if (m_Localization.FindIndex((LocalizationFieldEntry entry) => entry.localeId == GameManager.instance.localizationManager.activeLocaleId) < 0)
		{
			localeID = GameManager.instance.localizationManager.activeLocaleId;
			return true;
		}
		string[] supportedLocales = GameManager.instance.localizationManager.GetSupportedLocales();
		foreach (string locale in supportedLocales)
		{
			if (m_Localization.FindIndex((LocalizationFieldEntry entry) => entry.localeId == locale) < 0)
			{
				localeID = locale;
				return true;
			}
		}
		localeID = null;
		return false;
	}
```

- `public ValidEntries() : System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry>`  

```csharp
public IEnumerable<LocalizationFieldEntry> ValidEntries()
	{
		foreach (LocalizationFieldEntry item in m_Localization)
		{
			if (IsValid(item))
			{
				yield return item;
			}
		}
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("supportedLocales");
		writer.Write(GameManager.instance.localizationManager.GetSupportedLocales());
		writer.PropertyName("localization");
		writer.Write((IList<LocalizationFieldEntry>)m_Localization);
		writer.PropertyName("placeholder");
		writer.Write(placeholder);
		writer.PropertyName("mandatoryId");
		writer.Write(GameManager.instance.localizationManager.fallbackLocaleId);
	}
```


## Nested types

- `Game.UI.Editor.LocalizationField+LocalizationFieldEntry`  
- `Game.UI.Editor.LocalizationField+Bindings`  
- `Game.UI.Editor.LocalizationField+<>c`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass14_0`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass15_0`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass22_0`  
- `Game.UI.Editor.LocalizationField+<ValidEntries>d__20`  

