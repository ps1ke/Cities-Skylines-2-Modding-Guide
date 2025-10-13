# Game.UI.Editor.EditorPrefabUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class EditorPrefabUtils
{
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.String[]> s_PrefabTypes;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.String[]> s_PrefabTags;
    public static readonly Game.UI.Localization.LocalizedString kNone;

    public static System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorPrefabUtils+IconInfo> GetIcons(Game.Prefabs.PrefabBase prefab);
    public static System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> GetLocaleAssets(Game.Prefabs.PrefabBase prefab);
    public static Game.Prefabs.PrefabBase GetPrefabByID(System.String prefabID);
    public static T GetPrefabByID<T>(System.String prefabID);
    public static System.String GetPrefabID(Game.Prefabs.PrefabBase prefab);
    public static Game.UI.Localization.LocalizedString GetPrefabLabel(Game.Prefabs.PrefabBase prefab);
    public static System.String[] GetPrefabTags(System.Type type);
    public static System.String GetPrefabTypeName(System.Type type);
    public static System.String[] GetPrefabTypes(System.Type type);
    public static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetUserImages();
    public static System.Void SavePrefab(Game.Prefabs.PrefabBase prefab);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.String[]> s_PrefabTypes`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.String[]> s_PrefabTypes;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.String[]> s_PrefabTags`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.String[]> s_PrefabTags;
```

- `public static readonly Game.UI.Localization.LocalizedString kNone`  

```csharp
public static readonly Game.UI.Localization.LocalizedString kNone;
```


## Methods

- `public static GetIcons(Game.Prefabs.PrefabBase prefab) : System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorPrefabUtils+IconInfo>`  

```csharp
public static IEnumerable<IconInfo> GetIcons(PrefabBase prefab)
	{
		foreach (ComponentBase comp in prefab.components)
		{
			FieldInfo[] fields = comp.GetType().GetFields();
			foreach (FieldInfo fieldInfo in fields)
			{
				if (fieldInfo.FieldType != typeof(string))
				{
					continue;
				}
				CustomFieldAttribute customAttribute = fieldInfo.GetCustomAttribute<CustomFieldAttribute>();
				if (customAttribute != null && !(customAttribute.Factory != typeof(UIIconField)))
				{
					string text = (string)fieldInfo.GetValue(comp);
					if (UIExtensions.TryGetImageAsset(text, out var imageAsset))
					{
						yield return new IconInfo
						{
							m_Asset = imageAsset,
							m_URI = text,
							m_Field = fieldInfo,
							m_Component = comp
						};
					}
				}
			}
		}
	}
```

- `public static GetLocaleAssets(Game.Prefabs.PrefabBase prefab) : System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset>`  

```csharp
public static IEnumerable<LocaleAsset> GetLocaleAssets(PrefabBase prefab)
	{
		if (!(prefab.asset != null) || prefab.asset.database == AssetDatabase.game)
		{
			yield break;
		}
		foreach (LocaleAsset asset in AssetDatabase.global.GetAssets(SearchFilter<LocaleAsset>.ByCondition((LocaleAsset a) => a.subPath == prefab.asset.subPath)))
		{
			yield return asset;
		}
	}
```

- `public static GetPrefabByID(System.String prefabID) : Game.Prefabs.PrefabBase`  

```csharp
[CanBeNull]
	public static PrefabBase GetPrefabByID([CanBeNull] string prefabID)
	{
		return null;
	}
```

- `public static GetPrefabByID<T>(System.String prefabID) : T`  

```csharp
public static T GetPrefabByID<T>(System.String prefabID);
```

- `public static GetPrefabID(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
[CanBeNull]
	public static string GetPrefabID(PrefabBase prefab)
	{
		if (prefab != null && AssetDatabase.global.resources.prefabsMap.TryGetGuid(prefab, out var id))
		{
			return id;
		}
		return null;
	}
```

- `public static GetPrefabLabel(Game.Prefabs.PrefabBase prefab) : Game.UI.Localization.LocalizedString`  

```csharp
public static LocalizedString GetPrefabLabel(PrefabBase prefab)
	{
		if (prefab == null)
		{
			return kNone;
		}
		if (prefab.asset != null)
		{
			SourceMeta meta = prefab.asset.GetMeta();
			if (prefab.asset.database == AssetDatabase<ParadoxMods>.instance)
			{
				return LocalizedString.Value($"{prefab.name} - ({meta.platformID})");
			}
			if (prefab.asset.database == AssetDatabase.user)
			{
				string text = (meta.packaged ? meta.packageName : prefab.asset.name);
				return LocalizedString.Value(prefab.name + " - (" + text + ")");
			}
		}
		return LocalizedString.Value(prefab.name);
	}
```

- `public static GetPrefabTags(System.Type type) : System.String[]`  

```csharp
public static string[] GetPrefabTags(Type type)
	{
		if (s_PrefabTags.TryGetValue(type, out var value))
		{
			return value;
		}
		List<string> list = new List<string>();
		Type type2 = type;
		while (type2 != null && type2 != typeof(PrefabBase) && typeof(PrefabBase).IsAssignableFrom(type2))
		{
			string text = type2.Name;
			if (text.Length > 6 && text.EndsWith("Prefab"))
			{
				text = text.Substring(0, text.Length - 6);
			}
			list.Add(text.ToLowerInvariant());
			type2 = type2.BaseType;
		}
		return s_PrefabTags[type] = list.ToArray();
	}
```

- `public static GetPrefabTypeName(System.Type type) : System.String`  

```csharp
public static string GetPrefabTypeName(Type type)
	{
		return type.FullName;
	}
```

- `public static GetPrefabTypes(System.Type type) : System.String[]`  

```csharp
public static string[] GetPrefabTypes(Type type)
	{
		if (s_PrefabTypes.TryGetValue(type, out var value))
		{
			return value;
		}
		List<string> list = new List<string>();
		Type type2 = type;
		while (type2 != null && type2 != typeof(PrefabBase) && typeof(PrefabBase).IsAssignableFrom(type2))
		{
			list.Add(GetPrefabTypeName(type2));
			type2 = type2.BaseType;
		}
		return s_PrefabTypes[type] = list.ToArray();
	}
```

- `public static GetUserImages() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
public static IEnumerable<AssetItem> GetUserImages()
	{
		yield return new AssetItem
		{
			guid = default(Hash128),
			displayName = kNone
		};
		foreach (ImageAsset asset in AssetDatabase.global.GetAssets(SearchFilter<ImageAsset>.ByCondition((ImageAsset a) => a.GetMeta().subPath?.StartsWith(ScreenUtility.kScreenshotDirectory) ?? false)))
		{
			using (asset)
			{
				yield return new AssetItem
				{
					guid = asset.id,
					fileName = asset.name,
					displayName = asset.name,
					image = asset.ToUri()
				};
			}
		}
	}
```

- `public static SavePrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
public static void SavePrefab(PrefabBase prefab)
	{
		(prefab.asset ?? AssetDatabase.user.AddAsset(AssetDataPath.Create("StreamingData~/" + prefab.name, prefab.name ?? ""), prefab)).Save();
	}
```


## Nested types

- `Game.UI.Editor.EditorPrefabUtils+IconInfo`  
- `Game.UI.Editor.EditorPrefabUtils+<>c`  
- `Game.UI.Editor.EditorPrefabUtils+<>c__DisplayClass11_0`  
- `Game.UI.Editor.EditorPrefabUtils+<GetIcons>d__12`  
- `Game.UI.Editor.EditorPrefabUtils+<GetLocaleAssets>d__11`  
- `Game.UI.Editor.EditorPrefabUtils+<GetUserImages>d__14`  

