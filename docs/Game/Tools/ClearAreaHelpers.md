# Game.Tools.ClearAreaHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ClearAreaHelpers
{
    public static System.Void FillClearAreas(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.Entity ignoreUpgradeOrArea, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData, Unity.Entities.ComponentLookup<Game.Areas.Clear> clearAreaData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.BufferLookup<Game.Areas.SubArea> subAreaBuffers, Unity.Entities.BufferLookup<Game.Areas.Node> nodeBuffers, Unity.Entities.BufferLookup<Game.Areas.Triangle> triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void FillClearAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData objectGeometryData, Unity.Entities.Entity ignoreArea, Unity.Entities.ComponentLookup`1[[Game.Areas.Clear, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreaData, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeBuffers, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> prefabAreaGeometryData, Unity.Entities.BufferLookup<Game.Prefabs.SubArea> prefabSubAreas, Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> prefabSubAreaNodes, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Boolean isComplete, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
    public static System.Void InitClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform topLevelTransform);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Mathematics.float3 position, System.Boolean onGround);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Bezier4x3 curve, System.Boolean onGround);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Game.Objects.Transform ownerTransform);
    public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Unity.Mathematics.int2 nodeRange, Game.Objects.Transform ownerTransform);
    private static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Triangle3 triangle, Game.Objects.Transform ownerTransform);
    public static System.Void TransformClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform oldTransform, Game.Objects.Transform newTransform);
}
```


## Methods

- `public static FillClearAreas(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.Entity ignoreUpgradeOrArea, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData, Unity.Entities.ComponentLookup<Game.Areas.Clear> clearAreaData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.BufferLookup<Game.Areas.SubArea> subAreaBuffers, Unity.Entities.BufferLookup<Game.Areas.Node> nodeBuffers, Unity.Entities.BufferLookup<Game.Areas.Triangle> triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static System.Void FillClearAreas(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Unity.Entities.Entity ignoreUpgradeOrArea, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData, Unity.Entities.ComponentLookup<Game.Areas.Clear> clearAreaData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.BufferLookup<Game.Areas.SubArea> subAreaBuffers, Unity.Entities.BufferLookup<Game.Areas.Node> nodeBuffers, Unity.Entities.BufferLookup<Game.Areas.Triangle> triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
```

- `public static FillClearAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData objectGeometryData, Unity.Entities.Entity ignoreArea, Unity.Entities.ComponentLookup`1[[Game.Areas.Clear, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreaData, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeBuffers, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static System.Void FillClearAreas(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData objectGeometryData, Unity.Entities.Entity ignoreArea, Unity.Entities.ComponentLookup`1[[Game.Areas.Clear, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreaData, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& nodeBuffers, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangleBuffers, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
```

- `public static FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> prefabAreaGeometryData, Unity.Entities.BufferLookup<Game.Prefabs.SubArea> prefabSubAreas, Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> prefabSubAreaNodes, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static System.Void FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Entities.ComponentLookup<Game.Prefabs.AreaGeometryData> prefabAreaGeometryData, Unity.Entities.BufferLookup<Game.Prefabs.SubArea> prefabSubAreas, Unity.Entities.BufferLookup<Game.Prefabs.SubAreaNode> prefabSubAreaNodes, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
```

- `public static FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Boolean isComplete, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas) : System.Void`  

```csharp
public static System.Void FillClearAreas(Unity.Entities.Entity ownerPrefab, Game.Objects.Transform ownerTransform, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Boolean isComplete, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> prefabObjectGeometryData, Unity.Collections.NativeList`1[[Game.Tools.ClearAreaData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& clearAreas);
```

- `public static InitClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform topLevelTransform) : System.Void`  

```csharp
public static System.Void InitClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform topLevelTransform);
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Mathematics.float3 position, System.Boolean onGround) : System.Boolean`  

```csharp
public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Mathematics.float3 position, System.Boolean onGround);
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Bezier4x3 curve, System.Boolean onGround) : System.Boolean`  

```csharp
public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Bezier4x3 curve, System.Boolean onGround);
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Game.Objects.Transform ownerTransform) : System.Boolean`  

```csharp
public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Game.Objects.Transform ownerTransform);
```

- `public static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Unity.Mathematics.int2 nodeRange, Game.Objects.Transform ownerTransform) : System.Boolean`  

```csharp
public static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> subAreaNodes, Unity.Mathematics.int2 nodeRange, Game.Objects.Transform ownerTransform);
```

- `private static ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Triangle3 triangle, Game.Objects.Transform ownerTransform) : System.Boolean`  

```csharp
private static System.Boolean ShouldClear(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Colossal.Mathematics.Triangle3 triangle, Game.Objects.Transform ownerTransform);
```

- `public static TransformClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform oldTransform, Game.Objects.Transform newTransform) : System.Void`  

```csharp
public static System.Void TransformClearAreas(Unity.Collections.NativeList<Game.Tools.ClearAreaData> clearAreas, Game.Objects.Transform oldTransform, Game.Objects.Transform newTransform);
```


