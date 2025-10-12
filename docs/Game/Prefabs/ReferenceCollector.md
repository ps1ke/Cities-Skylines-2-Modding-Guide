# Game.Prefabs.ReferenceCollector

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects`  
- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields`  

## Constructors

- `public ReferenceCollector()`  

## Methods

- `public CollectDependencies(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> objs, System.Boolean addRoot) : Game.Prefabs.ReferenceCollector+CollectedReferences`  
- `public CollectDependencies(Colossal.IO.AssetDatabase.IAssetData obj) : Game.Prefabs.ReferenceCollector+CollectedReferences`  
- `private TraverseObject(System.Object obj, Game.Prefabs.ReferenceCollector+CollectedReferences references) : System.Void`  
- `private TraverseSurfaceAsset(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Game.Prefabs.ReferenceCollector+CollectedReferences references) : System.Void`  
- `private TryAddVisited(System.Object obj) : System.Boolean`  

## Nested types

- `Game.Prefabs.ReferenceCollector+CollectedReferences`  
- `Game.Prefabs.ReferenceCollector+<>c`  

