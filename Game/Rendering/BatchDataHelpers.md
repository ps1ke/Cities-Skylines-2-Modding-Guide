# Game.Rendering.BatchDataHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BatchDataHelpers
{
    public static System.Void AlignStack(Game.Objects.Stack& stack, Game.Prefabs.StackData stackData, System.Boolean start, System.Boolean end);
    private static Colossal.Mathematics.Bezier4x3 BuildCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 direction, System.Single length);
    public static Unity.Mathematics.float4x4 BuildCurveMatrix(Game.Net.Curve curve, Unity.Mathematics.float3x4 transformMatrix, Unity.Mathematics.float4 size, System.Int32 tilingCount);
    public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.NodeLane nodeLane);
    public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.EdgeLane edgeLane);
    public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.Elevation elevation);
    public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size);
    public static Unity.Mathematics.float4 BuildCurveScale(Game.Net.NodeLane nodeLane, Game.Prefabs.NetLaneData netLaneData);
    public static Unity.Mathematics.float4 BuildCurveScale();
    private static Unity.Mathematics.float4x4 BuildEdgeMatrix(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 offset, Unity.Mathematics.float4 mappingOffsets);
    public static Unity.Mathematics.float4x4 BuildTransformMatrix(Game.Net.Curve curve, Unity.Mathematics.float4 size, Unity.Mathematics.float4 curveScale, System.Single smoothingDistance, System.Boolean isDecal, System.Boolean isLoaded);
    public static System.Void CalculateEdgeParameters(Game.Net.EdgeGeometry edgeGeometry, System.Boolean isRotated, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters);
    private static System.Void CalculateMappingOffsets(Game.Net.Segment segment, Unity.Mathematics.float4& leftOffsets, Unity.Mathematics.float4& rightOffsets, Unity.Mathematics.float2 leftMappingOffset, Unity.Mathematics.float2 rightMappingOffset);
    public static Game.Prefabs.SubMeshFlags CalculateNetObjectSubMeshData(Game.Objects.NetObject netObject);
    public static System.Void CalculateNodeParameters(Game.Net.EdgeNodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters);
    public static System.Void CalculateOrphanParameters(Game.Net.Node node, Game.Net.NodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, System.Boolean isPrimary, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters);
    public static Game.Prefabs.SubMeshFlags CalculateQuantitySubMeshData(Game.Objects.Quantity quantity, Game.Prefabs.QuantityObjectData quantityObjectData, System.Boolean editorMode);
    public static Game.Prefabs.SubMeshFlags CalculateStackSubMeshData(Game.Objects.Stack stack, Game.Prefabs.StackData stackData, Unity.Mathematics.int3& tileCounts, Unity.Mathematics.float3& offsets, Unity.Mathematics.float3& scale);
    public static System.Void CalculateStackSubMeshData(Game.Prefabs.StackData stackData, Unity.Mathematics.float3 offsets, Unity.Mathematics.float3 scales, System.Int32 tileIndex, Game.Prefabs.SubMeshFlags subMeshFlags, Unity.Mathematics.float3& subMeshPosition, Unity.Mathematics.float3& subMeshScale);
    public static Game.Prefabs.SubMeshFlags CalculateTreeSubMeshData(Game.Objects.Tree tree, Game.Prefabs.GrowthScaleData growthScaleData, Unity.Mathematics.float3& scale);
    public static Unity.Mathematics.float3 GetAnimationCoordinate(Game.Prefabs.AnimationClip clip, System.Single time, System.Single previousTime);
    public static Unity.Mathematics.float2 GetBoneParameters(Game.Rendering.Skeleton skeleton);
    public static Unity.Mathematics.float2 GetBoneParameters(Game.Rendering.Animated animated);
    public static Unity.Mathematics.float4 GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, Game.Buildings.CitizenPresence citizenPresence, System.Single lightFactor, System.Boolean abandoned, System.Boolean electricity);
    public static Unity.Mathematics.float4 GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, System.Int32 passengersCount, System.Int32 passengerCapacity, System.Single lightFactor, System.Boolean destroyed);
    public static Unity.Mathematics.float4 GetDamage(Game.Objects.Surface surface, Game.Objects.Damaged damaged, Game.Events.OnFire onFire);
    public static Unity.Mathematics.float2 GetLightParameters(Game.Rendering.Emissive emissive);
    public static System.Int32 GetTileCount(Game.Net.Curve curve, System.Single length, System.Int32 tilingCount, System.Boolean geometryTiling, System.Int32& clipCount);
    public static Unity.Mathematics.float4 GetWetness(Game.Objects.Surface surface);
}
```


## Methods

- `public static AlignStack(Game.Objects.Stack& stack, Game.Prefabs.StackData stackData, System.Boolean start, System.Boolean end) : System.Void`  

```csharp
public static System.Void AlignStack(Game.Objects.Stack& stack, Game.Prefabs.StackData stackData, System.Boolean start, System.Boolean end);
```

- `private static BuildCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 direction, System.Single length) : Colossal.Mathematics.Bezier4x3`  

```csharp
private static Colossal.Mathematics.Bezier4x3 BuildCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 direction, System.Single length);
```

- `public static BuildCurveMatrix(Game.Net.Curve curve, Unity.Mathematics.float3x4 transformMatrix, Unity.Mathematics.float4 size, System.Int32 tilingCount) : Unity.Mathematics.float4x4`  

```csharp
public static Unity.Mathematics.float4x4 BuildCurveMatrix(Game.Net.Curve curve, Unity.Mathematics.float3x4 transformMatrix, Unity.Mathematics.float4 size, System.Int32 tilingCount);
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.NodeLane nodeLane) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.NodeLane nodeLane);
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.EdgeLane edgeLane) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.EdgeLane edgeLane);
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.Elevation elevation) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.Elevation elevation);
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 BuildCurveParams(Unity.Mathematics.float4 size);
```

- `public static BuildCurveScale(Game.Net.NodeLane nodeLane, Game.Prefabs.NetLaneData netLaneData) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 BuildCurveScale(Game.Net.NodeLane nodeLane, Game.Prefabs.NetLaneData netLaneData);
```

- `public static BuildCurveScale() : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 BuildCurveScale();
```

- `private static BuildEdgeMatrix(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 offset, Unity.Mathematics.float4 mappingOffsets) : Unity.Mathematics.float4x4`  

```csharp
private static Unity.Mathematics.float4x4 BuildEdgeMatrix(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 offset, Unity.Mathematics.float4 mappingOffsets);
```

- `public static BuildTransformMatrix(Game.Net.Curve curve, Unity.Mathematics.float4 size, Unity.Mathematics.float4 curveScale, System.Single smoothingDistance, System.Boolean isDecal, System.Boolean isLoaded) : Unity.Mathematics.float4x4`  

```csharp
public static Unity.Mathematics.float4x4 BuildTransformMatrix(Game.Net.Curve curve, Unity.Mathematics.float4 size, Unity.Mathematics.float4 curveScale, System.Single smoothingDistance, System.Boolean isDecal, System.Boolean isLoaded);
```

- `public static CalculateEdgeParameters(Game.Net.EdgeGeometry edgeGeometry, System.Boolean isRotated, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters) : System.Void`  

```csharp
public static System.Void CalculateEdgeParameters(Game.Net.EdgeGeometry edgeGeometry, System.Boolean isRotated, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters);
```

- `private static CalculateMappingOffsets(Game.Net.Segment segment, Unity.Mathematics.float4& leftOffsets, Unity.Mathematics.float4& rightOffsets, Unity.Mathematics.float2 leftMappingOffset, Unity.Mathematics.float2 rightMappingOffset) : System.Void`  

```csharp
private static System.Void CalculateMappingOffsets(Game.Net.Segment segment, Unity.Mathematics.float4& leftOffsets, Unity.Mathematics.float4& rightOffsets, Unity.Mathematics.float2 leftMappingOffset, Unity.Mathematics.float2 rightMappingOffset);
```

- `public static CalculateNetObjectSubMeshData(Game.Objects.NetObject netObject) : Game.Prefabs.SubMeshFlags`  

```csharp
public static Game.Prefabs.SubMeshFlags CalculateNetObjectSubMeshData(Game.Objects.NetObject netObject);
```

- `public static CalculateNodeParameters(Game.Net.EdgeNodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters) : System.Void`  

```csharp
public static System.Void CalculateNodeParameters(Game.Net.EdgeNodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters);
```

- `public static CalculateOrphanParameters(Game.Net.Node node, Game.Net.NodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, System.Boolean isPrimary, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters) : System.Void`  

```csharp
public static System.Void CalculateOrphanParameters(Game.Net.Node node, Game.Net.NodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, System.Boolean isPrimary, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters);
```

- `public static CalculateQuantitySubMeshData(Game.Objects.Quantity quantity, Game.Prefabs.QuantityObjectData quantityObjectData, System.Boolean editorMode) : Game.Prefabs.SubMeshFlags`  

```csharp
public static Game.Prefabs.SubMeshFlags CalculateQuantitySubMeshData(Game.Objects.Quantity quantity, Game.Prefabs.QuantityObjectData quantityObjectData, System.Boolean editorMode);
```

- `public static CalculateStackSubMeshData(Game.Objects.Stack stack, Game.Prefabs.StackData stackData, Unity.Mathematics.int3& tileCounts, Unity.Mathematics.float3& offsets, Unity.Mathematics.float3& scale) : Game.Prefabs.SubMeshFlags`  

```csharp
public static Game.Prefabs.SubMeshFlags CalculateStackSubMeshData(Game.Objects.Stack stack, Game.Prefabs.StackData stackData, Unity.Mathematics.int3& tileCounts, Unity.Mathematics.float3& offsets, Unity.Mathematics.float3& scale);
```

- `public static CalculateStackSubMeshData(Game.Prefabs.StackData stackData, Unity.Mathematics.float3 offsets, Unity.Mathematics.float3 scales, System.Int32 tileIndex, Game.Prefabs.SubMeshFlags subMeshFlags, Unity.Mathematics.float3& subMeshPosition, Unity.Mathematics.float3& subMeshScale) : System.Void`  

```csharp
public static System.Void CalculateStackSubMeshData(Game.Prefabs.StackData stackData, Unity.Mathematics.float3 offsets, Unity.Mathematics.float3 scales, System.Int32 tileIndex, Game.Prefabs.SubMeshFlags subMeshFlags, Unity.Mathematics.float3& subMeshPosition, Unity.Mathematics.float3& subMeshScale);
```

- `public static CalculateTreeSubMeshData(Game.Objects.Tree tree, Game.Prefabs.GrowthScaleData growthScaleData, Unity.Mathematics.float3& scale) : Game.Prefabs.SubMeshFlags`  

```csharp
public static Game.Prefabs.SubMeshFlags CalculateTreeSubMeshData(Game.Objects.Tree tree, Game.Prefabs.GrowthScaleData growthScaleData, Unity.Mathematics.float3& scale);
```

- `public static GetAnimationCoordinate(Game.Prefabs.AnimationClip clip, System.Single time, System.Single previousTime) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetAnimationCoordinate(Game.Prefabs.AnimationClip clip, System.Single time, System.Single previousTime);
```

- `public static GetBoneParameters(Game.Rendering.Skeleton skeleton) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetBoneParameters(Game.Rendering.Skeleton skeleton);
```

- `public static GetBoneParameters(Game.Rendering.Animated animated) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetBoneParameters(Game.Rendering.Animated animated);
```

- `public static GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, Game.Buildings.CitizenPresence citizenPresence, System.Single lightFactor, System.Boolean abandoned, System.Boolean electricity) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, Game.Buildings.CitizenPresence citizenPresence, System.Single lightFactor, System.Boolean abandoned, System.Boolean electricity);
```

- `public static GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, System.Int32 passengersCount, System.Int32 passengerCapacity, System.Single lightFactor, System.Boolean destroyed) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, System.Int32 passengersCount, System.Int32 passengerCapacity, System.Single lightFactor, System.Boolean destroyed);
```

- `public static GetDamage(Game.Objects.Surface surface, Game.Objects.Damaged damaged, Game.Events.OnFire onFire) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 GetDamage(Game.Objects.Surface surface, Game.Objects.Damaged damaged, Game.Events.OnFire onFire);
```

- `public static GetLightParameters(Game.Rendering.Emissive emissive) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetLightParameters(Game.Rendering.Emissive emissive);
```

- `public static GetTileCount(Game.Net.Curve curve, System.Single length, System.Int32 tilingCount, System.Boolean geometryTiling, System.Int32& clipCount) : System.Int32`  

```csharp
public static System.Int32 GetTileCount(Game.Net.Curve curve, System.Single length, System.Int32 tilingCount, System.Boolean geometryTiling, System.Int32& clipCount);
```

- `public static GetWetness(Game.Objects.Surface surface) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 GetWetness(Game.Objects.Surface surface);
```


## Nested types

- `Game.Rendering.BatchDataHelpers+CompositionParameters`  

