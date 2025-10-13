# Game.PSI.ModTags

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ModTags
{
    private static Colossal.Logging.ILog sLog;
    public static readonly System.Int32 kMaxTags;
    private static readonly System.Type[] sExcludePropTypes;

    private static System.Void GetAssetTypeTags(Colossal.IO.AssetDatabase.AssetData assetData, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
    private static System.Collections.Generic.IEnumerable<System.String> GetComponentTags(Game.Prefabs.ComponentBase component, System.Collections.Generic.HashSet<System.String> validTags, System.Type terminateAtType);
    public static System.Collections.Generic.IEnumerable<System.String> GetEnumFlagTags<T>(T value, T defaultValue);
    private static System.Void GetMapTags(Game.Assets.MapMetadata map, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
    private static System.Void GetPrefabTags(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
    private static System.Void GetSaveTags(Game.Assets.SaveGameMetadata save, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
    public static System.Void GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
    public static System.Boolean IsProp(Game.Prefabs.PrefabBase prefab);
}
```


## Fields

- `private static Colossal.Logging.ILog sLog`  

```csharp
private static Colossal.Logging.ILog sLog;
```

- `public static readonly System.Int32 kMaxTags`  

```csharp
public static readonly System.Int32 kMaxTags;
```

- `private static readonly System.Type[] sExcludePropTypes`  

```csharp
private static readonly System.Type[] sExcludePropTypes;
```


## Methods

- `private static GetAssetTypeTags(Colossal.IO.AssetDatabase.AssetData assetData, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static void GetAssetTypeTags(AssetData assetData, HashSet<string> tags, HashSet<string> typeTags, HashSet<string> validTags)
	{
		Type type = assetData.GetType();
		while (type != typeof(AssetData))
		{
			if (!type.IsDefined(typeof(ExcludeGeneratedModTagAttribute), inherit: false))
			{
				string item = type.Name.Replace("Metadata", "").Replace("Asset", "");
				if (validTags.Contains(item))
				{
					typeTags.Add(item);
				}
			}
			type = type.BaseType;
		}
		foreach (string modTag in assetData.modTags)
		{
			if (validTags.Contains(modTag))
			{
				typeTags.Add(modTag);
			}
		}
	}
```

- `private static GetComponentTags(Game.Prefabs.ComponentBase component, System.Collections.Generic.HashSet<System.String> validTags, System.Type terminateAtType) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private static IEnumerable<string> GetComponentTags(ComponentBase component, HashSet<string> validTags, Type terminateAtType)
	{
		Type type = component.GetType();
		while (type != terminateAtType && type != null)
		{
			if (!type.IsDefined(typeof(ExcludeGeneratedModTagAttribute), inherit: false))
			{
				string text = type.Name.Replace("Prefab", string.Empty).Replace("Object", string.Empty);
				if (validTags.Contains(text))
				{
					yield return text;
				}
			}
			type = type.BaseType;
		}
		foreach (string modTag in component.modTags)
		{
			if (validTags.Contains(modTag))
			{
				yield return modTag;
			}
		}
	}
```

- `public static GetEnumFlagTags<T>(T value, T defaultValue) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.String> GetEnumFlagTags<T>(T value, T defaultValue);
```

- `private static GetMapTags(Game.Assets.MapMetadata map, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static void GetMapTags(MapMetadata map, HashSet<string> tags, HashSet<string> typeTags, HashSet<string> validTags)
	{
		if (validTags.Contains(map.target.theme))
		{
			tags.Add(map.target.theme);
		}
	}
```

- `private static GetPrefabTags(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static void GetPrefabTags(PrefabBase prefab, HashSet<string> tags, HashSet<string> typeTags, HashSet<string> validTags)
	{
		foreach (string componentTag in GetComponentTags(prefab, validTags, typeof(PrefabBase)))
		{
			typeTags.Add(componentTag);
		}
		foreach (ComponentBase component in prefab.components)
		{
			foreach (string componentTag2 in GetComponentTags(component, validTags, typeof(ComponentBase)))
			{
				tags.Add(componentTag2);
			}
		}
	}
```

- `private static GetSaveTags(Game.Assets.SaveGameMetadata save, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static void GetSaveTags(SaveGameMetadata save, HashSet<string> tags, HashSet<string> typeTags, HashSet<string> validTags)
	{
		if (validTags.Contains(save.target.theme))
		{
			tags.Add(save.target.theme);
		}
	}
```

- `public static GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
public static void GetTags(AssetData asset, HashSet<string> tags, HashSet<string> typeTags, HashSet<string> validTags)
	{
		GetAssetTypeTags(asset, tags, typeTags, validTags);
		if (asset is MapMetadata map)
		{
			GetMapTags(map, tags, typeTags, validTags);
		}
		else if (asset is SaveGameMetadata save)
		{
			GetSaveTags(save, tags, typeTags, validTags);
		}
		else if (asset is PrefabAsset prefabAsset && prefabAsset.Load() is PrefabBase prefab)
		{
			GetPrefabTags(prefab, tags, typeTags, validTags);
		}
		tags.UnionWith(typeTags);
		while (tags.Count > kMaxTags)
		{
			string text = tags.FirstOrDefault((string tag) => !typeTags.Contains(tag));
			if (text != null)
			{
				tags.Remove(text);
			}
			else
			{
				text = tags.FirstOrDefault();
				if (text == null)
				{
					break;
				}
				tags.Remove(text);
				typeTags.Remove(text);
			}
			sLog.WarnFormat("Generated mod tags for {0} exceed max count, removing {1}", asset.name, text);
		}
	}
```

- `public static IsProp(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public static bool IsProp(PrefabBase prefab)
	{
		if (prefab.GetType() == typeof(StaticObjectPrefab))
		{
			Type[] array = sExcludePropTypes;
			foreach (Type type in array)
			{
				if (prefab.TryGet(type, out var _))
				{
					return false;
				}
			}
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.PSI.ModTags+<>c__DisplayClass2_0`  
- `Game.PSI.ModTags+<GetComponentTags>d__6`  
- `Game.PSI.ModTags+<GetEnumFlagTags>d__8<T>`  

