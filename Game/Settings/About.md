# Game.Settings.About

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public class About : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    public static const System.String kName;
    private static const System.String kGameGroup;
    private static const System.String kContentGroup;

    public System.String gameVersion { get; }
    public System.String gameConfiguration { get; }
    public System.String coreVersion { get; }
    public System.String uiVersion { get; }
    public System.String unityVersion { get; }
    public System.String cohtmlVersion { get; }
    public System.String atlVersion { get; }

    public About();

    internal static System.String <GetPageData>g__GetOwnershipCheckString|18_0(Colossal.PSI.Common.IDlc id);
    internal static System.String <GetPageData>g__GetOwnershipString|18_1(Colossal.PSI.Common.IDlc id);
    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    public virtual System.Void SetDefaults();
}
```


## Fields

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `private static const System.String kGameGroup`  

```csharp
private static const System.String kGameGroup;
```

- `private static const System.String kContentGroup`  

```csharp
private static const System.String kContentGroup;
```


## Properties

- `public System.String gameVersion { get }`  

```csharp
public System.String gameVersion { get; }
```

- `public System.String gameConfiguration { get }`  

```csharp
public System.String gameConfiguration { get; }
```

- `public System.String coreVersion { get }`  

```csharp
public System.String coreVersion { get; }
```

- `public System.String uiVersion { get }`  

```csharp
public System.String uiVersion { get; }
```

- `public System.String unityVersion { get }`  

```csharp
public System.String unityVersion { get; }
```

- `public System.String cohtmlVersion { get }`  

```csharp
public System.String cohtmlVersion { get; }
```

- `public System.String atlVersion { get }`  

```csharp
public System.String atlVersion { get; }
```


## Constructors

- `public About()`  

```csharp
public About();
```


## Methods

- `internal static <GetPageData>g__GetOwnershipCheckString|18_0(Colossal.PSI.Common.IDlc id) : System.String`  

```csharp
internal static System.String <GetPageData>g__GetOwnershipCheckString|18_0(Colossal.PSI.Common.IDlc id);
```

- `internal static <GetPageData>g__GetOwnershipString|18_1(Colossal.PSI.Common.IDlc id) : System.String`  

```csharp
internal static System.String <GetPageData>g__GetOwnershipString|18_1(Colossal.PSI.Common.IDlc id);
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public override AutomaticSettings.SettingPageData GetPageData(string id, bool addPrefix)
	{
		AutomaticSettings.SettingPageData pageData = base.GetPageData(id, addPrefix);
		foreach (IPlatformServiceIntegration platformServiceIntegration in PlatformManager.instance.platformServiceIntegrations)
		{
			StringBuilder stringBuilder = new StringBuilder();
			platformServiceIntegration.LogVersion(stringBuilder);
			string[] array = stringBuilder.ToString().Split(Environment.NewLine);
			int num = 0;
			string[] array2 = array;
			foreach (string line in array2)
			{
				int sep = line.IndexOf(":", StringComparison.Ordinal);
				if (sep != -1)
				{
					AutomaticSettings.ManualProperty property = new AutomaticSettings.ManualProperty(typeof(About), typeof(string), platformServiceIntegration.name)
					{
						canRead = true,
						canWrite = false,
						attributes = 
						{
							(Attribute)new SettingsUIPathAttribute($"{platformServiceIntegration.GetType().Name}{num++}.{platformServiceIntegration.name}"),
							(Attribute)new SettingsUIDisplayNameAttribute((string)null, line.Substring(0, sep))
						},
						getter = (object obj) => line.Substring(sep + 1)
					};
					AutomaticSettings.SettingItemData item = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.StringField, this, property, pageData.prefix);
					pageData["General"].AddItem(item);
				}
			}
		}
		pageData.AddGroup("Content");
		foreach (IDlc dlc in PlatformManager.instance.EnumerateLocalDLCs())
		{
			AutomaticSettings.ManualProperty property2 = new AutomaticSettings.ManualProperty(typeof(About), typeof(string), dlc.internalName)
			{
				canRead = true,
				canWrite = false,
				attributes = 
				{
					(Attribute)new SettingsUIPathAttribute(dlc.internalName),
					(Attribute)new SettingsUIDisplayNameAttribute((string)null, dlc.internalName + GetOwnershipCheckString(dlc)),
					(Attribute)new SettingsUIDescriptionAttribute((string)null, dlc.version.fullVersion + GetOwnershipString(dlc))
				},
				getter = (object obj) => dlc.version.fullVersion
			};
			AutomaticSettings.SettingItemData item2 = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.StringField, this, property2, pageData.prefix)
			{
				simpleGroup = "Content"
			};
			pageData["General"].AddItem(item2);
		}
		return pageData;
		static string GetOwnershipCheckString(IDlc dlc2)
		{
			if (!PlatformManager.instance.IsDlcOwned(dlc2))
			{
				return "*";
			}
			return string.Empty;
		}
		static string GetOwnershipString(IDlc dlc2)
		{
			if (!PlatformManager.instance.IsDlcOwned(dlc2))
			{
				return "\n*The Content is available on disk but not currently owned";
			}
			return string.Empty;
		}
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
	}
```


## Nested types

- `Game.Settings.About+<>c__DisplayClass18_0`  
- `Game.Settings.About+<>c__DisplayClass18_1`  

