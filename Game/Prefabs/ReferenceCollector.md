# Game.Prefabs.ReferenceCollector

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ReferenceCollector
{
    private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects;
    private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields;

    public ReferenceCollector();

    public Game.Prefabs.ReferenceCollector+CollectedReferences CollectDependencies(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> objs, System.Boolean addRoot);
    public Game.Prefabs.ReferenceCollector+CollectedReferences CollectDependencies(Colossal.IO.AssetDatabase.IAssetData obj);
    private System.Void TraverseObject(System.Object obj, Game.Prefabs.ReferenceCollector+CollectedReferences references);
    private System.Void TraverseSurfaceAsset(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Game.Prefabs.ReferenceCollector+CollectedReferences references);
    private System.Boolean TryAddVisited(System.Object obj);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects;
```

- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields;
```


## Constructors

- `public ReferenceCollector()`  

```csharp
public ReferenceCollector();
```


## Methods

- `public CollectDependencies(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> objs, System.Boolean addRoot) : Game.Prefabs.ReferenceCollector+CollectedReferences`  

```csharp
public Game.Prefabs.ReferenceCollector+CollectedReferences CollectDependencies(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> objs, System.Boolean addRoot);
```

- `public CollectDependencies(Colossal.IO.AssetDatabase.IAssetData obj) : Game.Prefabs.ReferenceCollector+CollectedReferences`  

```csharp
public Game.Prefabs.ReferenceCollector+CollectedReferences CollectDependencies(Colossal.IO.AssetDatabase.IAssetData obj);
```

- `private TraverseObject(System.Object obj, Game.Prefabs.ReferenceCollector+CollectedReferences references) : System.Void`  

```csharp
private System.Void TraverseObject(System.Object obj, Game.Prefabs.ReferenceCollector+CollectedReferences references);
```

- `private TraverseSurfaceAsset(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Game.Prefabs.ReferenceCollector+CollectedReferences references) : System.Void`  

```csharp
private System.Void TraverseSurfaceAsset(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Game.Prefabs.ReferenceCollector+CollectedReferences references);
```

- `private TryAddVisited(System.Object obj) : System.Boolean`  

```csharp
private System.Boolean TryAddVisited(System.Object obj);
```


## Nested types

- `Game.Prefabs.ReferenceCollector+CollectedReferences`  
- `Game.Prefabs.ReferenceCollector+<>c`  

