# Game.UI.Localization.UILocalizationManager

**Assembly:** `Game`  
**Namespace:** `Game.UI.Localization`  

**Type:** class public  

**Base:** `cohtml.Net.ILocalizationManager`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UILocalizationManager : cohtml.Net.ILocalizationManager, System.IDisposable
{
    private readonly Colossal.Localization.LocalizationManager m_LocalizationManager;

    public UILocalizationManager(Colossal.Localization.LocalizationManager localizationManager);
    private UILocalizationManager();

    public virtual System.Void Translate(System.String key, cohtml.Net.ILocalizationManager+TranslationData data);
}
```


## Fields

- `private readonly Colossal.Localization.LocalizationManager m_LocalizationManager`  

```csharp
private readonly Colossal.Localization.LocalizationManager m_LocalizationManager;
```


## Constructors

- `public UILocalizationManager(Colossal.Localization.LocalizationManager localizationManager)`  

```csharp
private UILocalizationManager()
	{
	}
```

- `private UILocalizationManager()`  

```csharp
private UILocalizationManager()
	{
	}
```


## Methods

- `public virtual Translate(System.String key, cohtml.Net.ILocalizationManager+TranslationData data) : System.Void`  

```csharp
public override void Translate(string key, TranslationData data)
	{
		if (m_LocalizationManager != null && m_LocalizationManager.activeDictionary.TryGetValue(key, out var value))
		{
			data.Set(value);
		}
		else
		{
			data.Set(key);
		}
	}
```


