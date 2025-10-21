# Game.UI.Editor.AssetImportPanel+PrefabFactory

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.AssetPipeline.IPrefabFactory`  

## Code

```csharp
public class PrefabFactory : Game.AssetPipeline.IPrefabFactory
{
    private readonly System.Collections.Generic.List<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> m_RootPrefabs;
    private readonly System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_CreatedPrefabs;

    public System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> rootPrefabs { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabs { get; }

    public PrefabFactory();

    public T CreatePrefab<T>(System.String sourcePath, System.String rootMeshName, System.Int32 lodLevel);
    private T LoadOrCreateAsset<T>(System.String sourcePath, System.String rootMeshName);
    private static System.Boolean PathCompare(System.String subPath1, System.String subPath2);
}
```


## Fields

- `private readonly System.Collections.Generic.List<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> m_RootPrefabs`  

```csharp
private readonly System.Collections.Generic.List<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> m_RootPrefabs;
```

- `private readonly System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_CreatedPrefabs`  

```csharp
private readonly System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_CreatedPrefabs;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> rootPrefabs { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> rootPrefabs { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabs { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabs { get; }
```


## Constructors

- `public PrefabFactory()`  

```csharp
public PrefabFactory();
```


## Methods

- `public CreatePrefab<T>(System.String sourcePath, System.String rootMeshName, System.Int32 lodLevel) : T`  

```csharp
public T CreatePrefab<T>(System.String sourcePath, System.String rootMeshName, System.Int32 lodLevel);
```

- `private LoadOrCreateAsset<T>(System.String sourcePath, System.String rootMeshName) : T`  

```csharp
private T LoadOrCreateAsset<T>(System.String sourcePath, System.String rootMeshName);
```

- `private static PathCompare(System.String subPath1, System.String subPath2) : System.Boolean`  

```csharp
private static System.Boolean PathCompare(System.String subPath1, System.String subPath2);
```


## Nested types

- `Game.UI.Editor.AssetImportPanel+PrefabFactory+<>c__DisplayClass8_0<T>`  

