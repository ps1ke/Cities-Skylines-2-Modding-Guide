# Game.PSI.PdxSdk.Launcher

**Assembly:** `Game`  
**Namespace:** `Game.PSI.PdxSdk`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Launcher
{
    private static readonly System.String kLastSaveInfoPath;
    private static const System.String kLastSaveInfoFileName;

    public static System.Void DeleteLastSaveMetadata();
    private static System.String FormatMoney(System.Int32 money, System.Boolean unlimitedMoney);
    private static System.String LocalizedString(System.String id, System.String def);
    public static System.Void SaveLastSaveMetadata(Game.Assets.SaveInfo saveInfo);
}
```


## Fields

- `private static readonly System.String kLastSaveInfoPath`  

```csharp
private static readonly System.String kLastSaveInfoPath;
```

- `private static const System.String kLastSaveInfoFileName`  

```csharp
private static const System.String kLastSaveInfoFileName;
```


## Methods

- `public static DeleteLastSaveMetadata() : System.Void`  

```csharp
public static void DeleteLastSaveMetadata()
	{
		if (File.Exists(kLastSaveInfoPath))
		{
			File.Delete(kLastSaveInfoPath);
		}
	}
```

- `private static FormatMoney(System.Int32 money, System.Boolean unlimitedMoney) : System.String`  

```csharp
private static string FormatMoney(int money, bool unlimitedMoney)
	{
		if (unlimitedMoney)
		{
			return LocalizedString("Menu.UNLIMITED_MONEY_LABEL", "Unlimited");
		}
		return string.Format(LocalizedString("Common.VALUE_MONEY", "{0}¢{1}").Replace("SIGN", "0").Replace("VALUE", "1"), ((float)math.sign(money) < 0f) ? "-" : "", money);
	}
```

- `private static LocalizedString(System.String id, System.String def) : System.String`  

```csharp
private static string LocalizedString(string id, string def)
	{
		if (GameManager.instance.localizationManager.activeDictionary.TryGetValue(id, out var value))
		{
			return value;
		}
		return def;
	}
```

- `public static SaveLastSaveMetadata(Game.Assets.SaveInfo saveInfo) : System.Void`  

```csharp
public static void SaveLastSaveMetadata(SaveInfo saveInfo)
	{
		try
		{
			SaveInfoData saveInfoData = new SaveInfoData();
			saveInfoData.title = saveInfo.cityName;
			saveInfoData.desc = string.Format("{0}: {1} {2}: {3}", LocalizedString("GameListScreen.POPULATION_LABEL", "Population"), saveInfo.population, LocalizedString("GameListScreen.MONEY_LABEL", "Money"), FormatMoney(saveInfo.money, saveInfo.options != null && saveInfo.options["unlimitedMoney"]));
			saveInfoData.date = saveInfo.lastModified.ToString("s");
			saveInfoData.rawGameVersion = Version.current.shortVersion;
			SaveInfoData data = saveInfoData;
			File.WriteAllText(kLastSaveInfoPath, JSON.Dump(data));
		}
		catch (Exception exception)
		{
			UnityEngine.Debug.LogException(exception);
		}
	}
```


## Nested types

- `Game.PSI.PdxSdk.Launcher+LocaleID`  
- `Game.PSI.PdxSdk.Launcher+SaveInfoData`  

