# Colossal.Core.MaxRectsBinPack

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Core`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Fields

- `private System.Int32 <binWidth>k__BackingField`  
- `private System.Int32 <binHeight>k__BackingField`  
- `private System.Boolean <allowRotations>k__BackingField`  
- `private System.Collections.Generic.List<UnityEngine.Rect> m_UsedRectangles`  
- `private System.Collections.Generic.List<UnityEngine.Rect> m_FreeRectangles`  

## Properties

- `public System.Int32 binWidth { get; private set }`  
- `public System.Int32 binHeight { get; private set }`  
- `public System.Boolean allowRotations { get; private set }`  
- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get }`  
- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get }`  

## Constructors

- `public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations)`  
- `public MaxRectsBinPack(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles)`  

## Methods

- `private CommonIntervalLength(System.Int32 i1start, System.Int32 i1end, System.Int32 i2start, System.Int32 i2end) : System.Int32`  
- `private ContactPointScoreNode(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Int32`  
- `private FindPositionForNewNodeBestAreaFit(System.Int32 width, System.Int32 height, System.Int32& bestAreaFit, System.Int32& bestShortSideFit) : UnityEngine.Rect`  
- `private FindPositionForNewNodeBestLongSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit) : UnityEngine.Rect`  
- `private FindPositionForNewNodeBestShortSideFit(System.Int32 width, System.Int32 height, System.Int32& bestShortSideFit, System.Int32& bestLongSideFit) : UnityEngine.Rect`  
- `private FindPositionForNewNodeBottomLeft(System.Int32 width, System.Int32 height, System.Int32& bestY, System.Int32& bestX) : UnityEngine.Rect`  
- `private FindPositionForNewNodeContactPoint(System.Int32 width, System.Int32 height, System.Int32& bestContactScore) : UnityEngine.Rect`  
- `public Init(System.Int32 width, System.Int32 height, System.Boolean rotations) : System.Void`  
- `public Insert(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method) : UnityEngine.Rect`  
- `public Insert(System.Collections.Generic.List<UnityEngine.Rect> rects, System.Collections.Generic.List<UnityEngine.Rect> dst, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method) : System.Void`  
- `private IsContainedIn(UnityEngine.Rect a, UnityEngine.Rect b) : System.Boolean`  
- `public Occupancy() : System.Single`  
- `private PlaceRect(UnityEngine.Rect node) : System.Void`  
- `private PruneFreeList() : System.Void`  
- `public Resize(System.Int32 width, System.Int32 height) : System.Void`  
- `private ScoreRect(System.Int32 width, System.Int32 height, Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic method, System.Int32& score1, System.Int32& score2) : UnityEngine.Rect`  
- `private SplitFreeNode(UnityEngine.Rect freeNode, UnityEngine.Rect& usedNode) : System.Boolean`  

## Nested types

- `Colossal.Core.MaxRectsBinPack+FreeRectChoiceHeuristic`  

