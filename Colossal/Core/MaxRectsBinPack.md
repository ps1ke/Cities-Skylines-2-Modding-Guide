# Colossal.Core.MaxRectsBinPack

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Core`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class MaxRectsBinPack
{
    private System.Int32 <binWidth>k__BackingField;
    private System.Int32 <binHeight>k__BackingField;
    private System.Boolean <allowRotations>k__BackingField;
    private System.Collections.Generic.List<UnityEngine.Rect> m_UsedRectangles;
    private System.Collections.Generic.List<UnityEngine.Rect> m_FreeRectangles;

    public System.Int32 binWidth { get; private set; }
    public System.Int32 binHeight { get; private set; }
    public System.Boolean allowRotations { get; private set; }
    public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get; }
    public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get; }

    public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations);
    public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles);

    private System.Int32 CommonIntervalLength(System.Int32 i1start, System.Int32 i1end, System.Int32 i2start, System.Int32 i2end);
    private System.Int32 ContactPointScoreNode(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
    private UnityEngine.Rect FindPositionForNewNodeBestAreaFit(System.Int32 width, System.Int32 height, System.Int32& bestAreaFit, System.Int32& bestShortSideFit);
    private UnityEngine.Rect FindPositionForNewNodeBestLongSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit);
    private UnityEngine.Rect FindPositionForNewNodeBestShortSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit);
    private UnityEngine.Rect FindPositionForNewNodeBottomLeft(System.Int32 width, System.Int32 height, System.Int32& bestY, System.Int32& bestX);
    private UnityEngine.Rect FindPositionForNewNodeContactPoint(System.Int32 width, System.Int32 height, System.Int32& bestContactScore);
    public System.Void Init(System.Int32 width, System.Int32 height, System.Boolean rotations);
    public UnityEngine.Rect Insert(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method);
    public System.Void Insert(System.Collections.Generic.List<UnityEngine.Rect> rects, System.Collections.Generic.List<UnityEngine.Rect> dst, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method);
    private System.Boolean IsContainedIn(UnityEngine.Rect a, UnityEngine.Rect b);
    public System.Single Occupancy();
    private System.Void PlaceRect(UnityEngine.Rect node);
    private System.Void PruneFreeList();
    public System.Void Resize(System.Int32 width, System.Int32 height);
    private UnityEngine.Rect ScoreRect(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method, System.Int32& score1, System.Int32& score2);
    private System.Boolean SplitFreeNode(UnityEngine.Rect freeNode, UnityEngine.Rect& usedNode);
}
```


## Fields

- `private System.Int32 <binWidth>k__BackingField`  

```csharp
private System.Int32 <binWidth>k__BackingField;
```

- `private System.Int32 <binHeight>k__BackingField`  

```csharp
private System.Int32 <binHeight>k__BackingField;
```

- `private System.Boolean <allowRotations>k__BackingField`  

```csharp
private System.Boolean <allowRotations>k__BackingField;
```

- `private System.Collections.Generic.List<UnityEngine.Rect> m_UsedRectangles`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rect> m_UsedRectangles;
```

- `private System.Collections.Generic.List<UnityEngine.Rect> m_FreeRectangles`  

```csharp
private System.Collections.Generic.List<UnityEngine.Rect> m_FreeRectangles;
```


## Properties

- `public System.Int32 binWidth { get; private set }`  

```csharp
public System.Int32 binWidth { get; private set; }
```

- `public System.Int32 binHeight { get; private set }`  

```csharp
public System.Int32 binHeight { get; private set; }
```

- `public System.Boolean allowRotations { get; private set }`  

```csharp
public System.Boolean allowRotations { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get; }
```

- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get; }
```


## Constructors

- `public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations)`  

```csharp
public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations);
```

- `public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles)`  

```csharp
public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles);
```


## Methods

- `private CommonIntervalLength(System.Int32 i1start, System.Int32 i1end, System.Int32 i2start, System.Int32 i2end) : System.Int32`  

```csharp
private System.Int32 CommonIntervalLength(System.Int32 i1start, System.Int32 i1end, System.Int32 i2start, System.Int32 i2end);
```

- `private ContactPointScoreNode(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Int32`  

```csharp
private System.Int32 ContactPointScoreNode(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
```

- `private FindPositionForNewNodeBestAreaFit(System.Int32 width, System.Int32 height, System.Int32& bestAreaFit, System.Int32& bestShortSideFit) : UnityEngine.Rect`  

```csharp
private UnityEngine.Rect FindPositionForNewNodeBestAreaFit(System.Int32 width, System.Int32 height, System.Int32& bestAreaFit, System.Int32& bestShortSideFit);
```

- `private FindPositionForNewNodeBestLongSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit) : UnityEngine.Rect`  

```csharp
private UnityEngine.Rect FindPositionForNewNodeBestLongSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit);
```

- `private FindPositionForNewNodeBestShortSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit) : UnityEngine.Rect`  

```csharp
private UnityEngine.Rect FindPositionForNewNodeBestShortSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit);
```

- `private FindPositionForNewNodeBottomLeft(System.Int32 width, System.Int32 height, System.Int32& bestY, System.Int32& bestX) : UnityEngine.Rect`  

```csharp
private UnityEngine.Rect FindPositionForNewNodeBottomLeft(System.Int32 width, System.Int32 height, System.Int32& bestY, System.Int32& bestX);
```

- `private FindPositionForNewNodeContactPoint(System.Int32 width, System.Int32 height, System.Int32& bestContactScore) : UnityEngine.Rect`  

```csharp
private UnityEngine.Rect FindPositionForNewNodeContactPoint(System.Int32 width, System.Int32 height, System.Int32& bestContactScore);
```

- `public Init(System.Int32 width, System.Int32 height, System.Boolean rotations) : System.Void`  

```csharp
public System.Void Init(System.Int32 width, System.Int32 height, System.Boolean rotations);
```

- `public Insert(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method) : UnityEngine.Rect`  

```csharp
public UnityEngine.Rect Insert(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method);
```

- `public Insert(System.Collections.Generic.List<UnityEngine.Rect> rects, System.Collections.Generic.List<UnityEngine.Rect> dst, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method) : System.Void`  

```csharp
public System.Void Insert(System.Collections.Generic.List<UnityEngine.Rect> rects, System.Collections.Generic.List<UnityEngine.Rect> dst, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method);
```

- `private IsContainedIn(UnityEngine.Rect a, UnityEngine.Rect b) : System.Boolean`  

```csharp
private System.Boolean IsContainedIn(UnityEngine.Rect a, UnityEngine.Rect b);
```

- `public Occupancy() : System.Single`  

```csharp
public System.Single Occupancy();
```

- `private PlaceRect(UnityEngine.Rect node) : System.Void`  

```csharp
private System.Void PlaceRect(UnityEngine.Rect node);
```

- `private PruneFreeList() : System.Void`  

```csharp
private System.Void PruneFreeList();
```

- `public Resize(System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public System.Void Resize(System.Int32 width, System.Int32 height);
```

- `private ScoreRect(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method, System.Int32& score1, System.Int32& score2) : UnityEngine.Rect`  

```csharp
private UnityEngine.Rect ScoreRect(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method, System.Int32& score1, System.Int32& score2);
```

- `private SplitFreeNode(UnityEngine.Rect freeNode, UnityEngine.Rect& usedNode) : System.Boolean`  

```csharp
private System.Boolean SplitFreeNode(UnityEngine.Rect freeNode, UnityEngine.Rect& usedNode);
```


## Nested types

- `Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic`  

