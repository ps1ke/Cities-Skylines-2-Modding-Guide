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
public static System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorPrefabUtils+IconInfo> GetIcons(Game.Prefabs.PrefabBase prefab);
```

- `public static GetLocaleAssets(Game.Prefabs.PrefabBase prefab) : System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset>`  

```csharp
public static System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> GetLocaleAssets(Game.Prefabs.PrefabBase prefab);
```

- `public static GetPrefabByID(System.String prefabID) : Game.Prefabs.PrefabBase`  

```csharp
public static Game.Prefabs.PrefabBase GetPrefabByID(System.String prefabID);
```

- `public static GetPrefabByID<T>(System.String prefabID) : T`  

```csharp
public static T GetPrefabByID<T>(System.String prefabID);
```

- `public static GetPrefabID(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
public static System.String GetPrefabID(Game.Prefabs.PrefabBase prefab);
```

- `public static GetPrefabLabel(Game.Prefabs.PrefabBase prefab) : Game.UI.Localization.LocalizedString`  

```csharp
public static Game.UI.Localization.LocalizedString GetPrefabLabel(Game.Prefabs.PrefabBase prefab);
```

- `public static GetPrefabTags(System.Type type) : System.String[]`  

```csharp
public static System.String[] GetPrefabTags(System.Type type);
```

- `public static GetPrefabTypeName(System.Type type) : System.String`  

```csharp
public static System.String GetPrefabTypeName(System.Type type);
```

- `public static GetPrefabTypes(System.Type type) : System.String[]`  

```csharp
public static System.String[] GetPrefabTypes(System.Type type);
```

- `public static GetUserImages() : System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem>`  

```csharp
public static System.Collections.Generic.IEnumerable<Game.UI.Editor.AssetItem> GetUserImages();
```

- `public static SavePrefab(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
public static System.Void SavePrefab(Game.Prefabs.PrefabBase prefab);
```


## Nested types

- `Game.UI.Editor.EditorPrefabUtils+IconInfo`  
- `Game.UI.Editor.EditorPrefabUtils+<>c`  
- `Game.UI.Editor.EditorPrefabUtils+<>c__DisplayClass11_0`  
- `Game.UI.Editor.EditorPrefabUtils+<GetIcons>d__12`  
- `Game.UI.Editor.EditorPrefabUtils+<GetLocaleAssets>d__11`  
- `Game.UI.Editor.EditorPrefabUtils+<GetUserImages>d__14`  

