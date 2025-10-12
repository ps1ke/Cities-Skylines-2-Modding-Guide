# Game.UI.Editor.AssetImportPanel+PrefabFactory

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.AssetPipeline.IPrefabFactory`  

## Fields

- `private readonly System.Collections.Generic.List<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> m_RootPrefabs`  
- `private readonly System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_CreatedPrefabs`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<System.ValueTuple<Game.Prefabs.PrefabBase, System.String>> rootPrefabs { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Prefabs.PrefabBase> prefabs { get }`  

## Constructors

- `public PrefabFactory()`  

## Methods

- `public CreatePrefab<T>(System.String sourcePath, System.String rootMeshName, System.Int32 lodLevel) : T`  
- `private LoadOrCreateAsset<T>(System.String sourcePath, System.String rootMeshName) : T`  
- `private static PathCompare(System.String subPath1, System.String subPath2) : System.Boolean`  

## Nested types

- `Game.UI.Editor.AssetImportPanel+PrefabFactory+<>c__DisplayClass8_0<T>`  

