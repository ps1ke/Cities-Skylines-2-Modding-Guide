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
private static System.Void GetAssetTypeTags(Colossal.IO.AssetDatabase.AssetData assetData, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
```

- `private static GetComponentTags(Game.Prefabs.ComponentBase component, System.Collections.Generic.HashSet<System.String> validTags, System.Type terminateAtType) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private static System.Collections.Generic.IEnumerable<System.String> GetComponentTags(Game.Prefabs.ComponentBase component, System.Collections.Generic.HashSet<System.String> validTags, System.Type terminateAtType);
```

- `public static GetEnumFlagTags<T>(T value, T defaultValue) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
public static System.Collections.Generic.IEnumerable<System.String> GetEnumFlagTags<T>(T value, T defaultValue);
```

- `private static GetMapTags(Game.Assets.MapMetadata map, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static System.Void GetMapTags(Game.Assets.MapMetadata map, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
```

- `private static GetPrefabTags(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static System.Void GetPrefabTags(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
```

- `private static GetSaveTags(Game.Assets.SaveGameMetadata save, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
private static System.Void GetSaveTags(Game.Assets.SaveGameMetadata save, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
```

- `public static GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  

```csharp
public static System.Void GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags);
```

- `public static IsProp(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public static System.Boolean IsProp(Game.Prefabs.PrefabBase prefab);
```


## Nested types

- `Game.PSI.ModTags+<>c__DisplayClass2_0`  
- `Game.PSI.ModTags+<GetComponentTags>d__6`  
- `Game.PSI.ModTags+<GetEnumFlagTags>d__8<T>`  

