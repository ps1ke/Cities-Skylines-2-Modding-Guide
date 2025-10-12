# Game.PSI.ModTags

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static Colossal.Logging.ILog sLog`  
- `public static readonly System.Int32 kMaxTags`  
- `private static readonly System.Type[] sExcludePropTypes`  

## Methods

- `private static GetAssetTypeTags(Colossal.IO.AssetDatabase.AssetData assetData, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  
- `private static GetComponentTags(Game.Prefabs.ComponentBase component, System.Collections.Generic.HashSet<System.String> validTags, System.Type terminateAtType) : System.Collections.Generic.IEnumerable<System.String>`  
- `public static GetEnumFlagTags<T>(T value, T defaultValue) : System.Collections.Generic.IEnumerable<System.String>`  
- `private static GetMapTags(Game.Assets.MapMetadata map, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  
- `private static GetPrefabTags(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  
- `private static GetSaveTags(Game.Assets.SaveGameMetadata save, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  
- `public static GetTags(Colossal.IO.AssetDatabase.AssetData asset, System.Collections.Generic.HashSet<System.String> tags, System.Collections.Generic.HashSet<System.String> typeTags, System.Collections.Generic.HashSet<System.String> validTags) : System.Void`  
- `public static IsProp(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

## Nested types

- `Game.PSI.ModTags+<>c__DisplayClass2_0`  
- `Game.PSI.ModTags+<GetComponentTags>d__6`  
- `Game.PSI.ModTags+<GetEnumFlagTags>d__8<T>`  

