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
public static void AlignStack(ref Stack stack, StackData stackData, bool start, bool end)
	{
		float num = MathUtils.Size(stack.m_Range);
		float num2 = MathUtils.Size(stackData.m_FirstBounds);
		float num3 = MathUtils.Size(stackData.m_MiddleBounds);
		float num4 = MathUtils.Size(stackData.m_LastBounds);
		num2 = math.select(num2 * 0.5f, num2, stackData.m_DontScale.x);
		num4 = math.select(num4 * 0.5f, num4, stackData.m_DontScale.z);
		float num5 = math.max(num, num2 + num4);
		if (math.all(stackData.m_DontScale.xz))
		{
			int num6 = (int)((num5 - num2 - num4) / num3 + math.select(0.5f, 0.001f, stackData.m_DontScale.y));
			num5 = math.select(num5, num2 + num4 + (float)num6 * num3, num6 == 0 || stackData.m_DontScale.y);
		}
		float falseValue = (num5 - num) * math.select(1f, 0.5f, start == end);
		stack.m_Range.min -= math.select(falseValue, 0f, start && !end);
		stack.m_Range.max += math.select(falseValue, 0f, end && !start);
	}
```

- `private static BuildCurve(Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 direction, System.Single length) : Colossal.Mathematics.Bezier4x3`  

```csharp
private static Bezier4x3 BuildCurve(float3 startPos, float3 direction, float length)
	{
		direction = MathUtils.Normalize(direction, direction.xz);
		direction.y = math.clamp(direction.y, -1f, 1f);
		Bezier4x3 result = default(Bezier4x3);
		result.a = startPos;
		result.b = startPos + direction * (length * (1f / 3f));
		result.c = startPos + direction * (length * (2f / 3f));
		result.d = startPos + direction * length;
		return result;
	}
```

- `public static BuildCurveMatrix(Game.Net.Curve curve, Unity.Mathematics.float3x4 transformMatrix, Unity.Mathematics.float4 size, System.Int32 tilingCount) : Unity.Mathematics.float4x4`  

```csharp
public static float4x4 BuildCurveMatrix(Curve curve, float3x4 transformMatrix, float4 size, int tilingCount)
	{
		float2 @float = default(float2);
		@float.x = math.distance(curve.m_Bezier.a, curve.m_Bezier.b);
		@float.y = math.distance(curve.m_Bezier.c, curve.m_Bezier.d);
		@float /= curve.m_Length;
		float4 float2 = new float4(0f, @float.x, 1f - @float.y, 1f);
		float3 c = transformMatrix.c3;
		float num = curve.m_Length / math.max(1f, size.z);
		num = math.select(num, math.round(num * (float)tilingCount) / (float)tilingCount, tilingCount != 0);
		float2 *= num;
		float4x4 result = default(float4x4);
		result.c0 = new float4(curve.m_Bezier.a - c, float2.x);
		result.c1 = new float4(curve.m_Bezier.b - c, float2.y);
		result.c2 = new float4(curve.m_Bezier.c - c, float2.z);
		result.c3 = new float4(curve.m_Bezier.d - c, float2.w);
		return result;
	}
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.NodeLane nodeLane) : Unity.Mathematics.float4`  

```csharp
public static float4 BuildCurveParams(float4 size)
	{
		return new float4(size.z, 1f, 1f, 1f);
	}
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.EdgeLane edgeLane) : Unity.Mathematics.float4`  

```csharp
public static float4 BuildCurveParams(float4 size)
	{
		return new float4(size.z, 1f, 1f, 1f);
	}
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size, Game.Net.Elevation elevation) : Unity.Mathematics.float4`  

```csharp
public static float4 BuildCurveParams(float4 size)
	{
		return new float4(size.z, 1f, 1f, 1f);
	}
```

- `public static BuildCurveParams(Unity.Mathematics.float4 size) : Unity.Mathematics.float4`  

```csharp
public static float4 BuildCurveParams(float4 size)
	{
		return new float4(size.z, 1f, 1f, 1f);
	}
```

- `public static BuildCurveScale(Game.Net.NodeLane nodeLane, Game.Prefabs.NetLaneData netLaneData) : Unity.Mathematics.float4`  

```csharp
public static float4 BuildCurveScale()
	{
		return 1f;
	}
```

- `public static BuildCurveScale() : Unity.Mathematics.float4`  

```csharp
public static float4 BuildCurveScale()
	{
		return 1f;
	}
```

- `private static BuildEdgeMatrix(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 offset, Unity.Mathematics.float4 mappingOffsets) : Unity.Mathematics.float4x4`  

```csharp
private static float4x4 BuildEdgeMatrix(Bezier4x3 curve, float3 offset, float4 mappingOffsets)
	{
		return new float4x4
		{
			c0 = new float4(curve.a - offset, mappingOffsets.x),
			c1 = new float4(curve.b - offset, mappingOffsets.y),
			c2 = new float4(curve.c - offset, mappingOffsets.z),
			c3 = new float4(curve.d - offset, mappingOffsets.w)
		};
	}
```

- `public static BuildTransformMatrix(Game.Net.Curve curve, Unity.Mathematics.float4 size, Unity.Mathematics.float4 curveScale, System.Single smoothingDistance, System.Boolean isDecal, System.Boolean isLoaded) : Unity.Mathematics.float4x4`  

```csharp
public static float4x4 BuildTransformMatrix(Curve curve, float4 size, float4 curveScale, float smoothingDistance, bool isDecal, bool isLoaded)
	{
		if (isDecal)
		{
			float3 value = curve.m_Bezier.d - curve.m_Bezier.a;
			float3 @float = math.select(new float3(2.5f, 2.5f, 2f), size.xyz, isLoaded);
			size.xy *= math.max(curveScale.xy, curveScale.zw);
			if (MathUtils.TryNormalize(ref value))
			{
				float3 float2 = math.normalizesafe(MathUtils.StartTangent(curve.m_Bezier));
				float3 float3 = math.normalizesafe(MathUtils.EndTangent(curve.m_Bezier));
				curve.m_Bezier.a -= float2 * smoothingDistance;
				curve.m_Bezier.d += float3 * smoothingDistance;
				float3 float4 = new float3
				{
					xz = math.normalizesafe(MathUtils.Right(value.xz), new float2(1f, 0f))
				};
				float3 float5 = math.cross(value, float4);
				float3 x = curve.m_Bezier.b - curve.m_Bezier.a;
				float3 x2 = curve.m_Bezier.c - curve.m_Bezier.a;
				float3 x3 = curve.m_Bezier.d - curve.m_Bezier.a;
				float3 y = new float3(math.dot(x, float4), math.dot(x, float5), math.dot(x, value));
				float3 x4 = new float3(math.dot(x2, float4), math.dot(x2, float5), math.dot(x2, value));
				float3 y2 = new float3(math.dot(x3, float4), math.dot(x3, float5), math.dot(x3, value));
				float3 float6 = math.min(math.min(0f, y), math.min(x4, y2));
				float3 float7 = math.max(math.max(0f, y), math.max(x4, y2));
				float2 x5 = new float2(math.dot(float4, float2), math.dot(float4, float3));
				float2 x6 = new float2(float2.y, float3.y);
				float3 float8 = new float3(size.xy, size.x * math.cmax(math.abs(x5)) + size.y * math.cmax(math.abs(x6))) * 0.5f;
				float6 -= float8;
				float7 += float8;
				float3 v = math.lerp(float6, float7, 0.5f);
				quaternion quaternion = quaternion.LookRotation(value, float5);
				float3 translation = curve.m_Bezier.a + math.rotate(quaternion, v);
				float3 scale = (float7 - float6) / @float;
				translation.y += size.w;
				translation -= float5 * (size.w * scale.y);
				return float4x4.TRS(translation, quaternion, scale);
			}
			float3 translation2 = math.lerp(curve.m_Bezier.a, curve.m_Bezier.d, 0.5f);
			quaternion identity = quaternion.identity;
			size.z += smoothingDistance;
			float3 scale2 = size.xyx / @float;
			return float4x4.TRS(translation2, identity, scale2);
		}
		if (isLoaded)
		{
			return float4x4.Translate(math.lerp(curve.m_Bezier.a, curve.m_Bezier.d, 0.5f));
		}
		float3 translation3 = math.lerp(curve.m_Bezier.a, curve.m_Bezier.d, 0.5f);
		quaternion identity2 = quaternion.identity;
		float3 scale3 = new float3(math.max(size.xy, 0.02f) * 0.4f, 1f);
		return float4x4.TRS(translation3, identity2, scale3);
	}
```

- `public static CalculateEdgeParameters(Game.Net.EdgeGeometry edgeGeometry, System.Boolean isRotated, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters) : System.Void`  

```csharp
public static void CalculateEdgeParameters(EdgeGeometry edgeGeometry, bool isRotated, out CompositionParameters compositionParameters)
	{
		float3 @float = MathUtils.Center(edgeGeometry.m_Bounds);
		float2 float2 = edgeGeometry.m_Start.m_Length + edgeGeometry.m_End.m_Length;
		CalculateMappingOffsets(edgeGeometry.m_Start, out var leftOffsets, out var rightOffsets, new float2(0f, edgeGeometry.m_Start.m_Length.x), new float2(0f, edgeGeometry.m_Start.m_Length.y));
		CalculateMappingOffsets(edgeGeometry.m_End, out var leftOffsets2, out var rightOffsets2, new float2(edgeGeometry.m_Start.m_Length.x, float2.x), new float2(edgeGeometry.m_Start.m_Length.y, float2.y));
		compositionParameters.m_TransformMatrix = TransformHelper.Translate(@float);
		if (isRotated)
		{
			compositionParameters.m_CompositionMatrix0 = BuildEdgeMatrix(MathUtils.Invert(edgeGeometry.m_End.m_Right), @float, rightOffsets2.wzyx);
			compositionParameters.m_CompositionMatrix1 = BuildEdgeMatrix(MathUtils.Invert(edgeGeometry.m_Start.m_Right), @float, rightOffsets.wzyx);
			compositionParameters.m_CompositionMatrix2 = BuildEdgeMatrix(MathUtils.Invert(edgeGeometry.m_End.m_Left), @float, leftOffsets2.wzyx);
			compositionParameters.m_CompositionMatrix3 = BuildEdgeMatrix(MathUtils.Invert(edgeGeometry.m_Start.m_Left), @float, leftOffsets.wzyx);
		}
		else
		{
			compositionParameters.m_CompositionMatrix0 = BuildEdgeMatrix(edgeGeometry.m_Start.m_Left, @float, leftOffsets);
			compositionParameters.m_CompositionMatrix1 = BuildEdgeMatrix(edgeGeometry.m_End.m_Left, @float, leftOffsets2);
			compositionParameters.m_CompositionMatrix2 = BuildEdgeMatrix(edgeGeometry.m_Start.m_Right, @float, rightOffsets);
			compositionParameters.m_CompositionMatrix3 = BuildEdgeMatrix(edgeGeometry.m_End.m_Right, @float, rightOffsets2);
		}
		compositionParameters.m_CompositionMatrix4 = float4x4.identity;
		compositionParameters.m_CompositionMatrix5 = float4x4.identity;
		compositionParameters.m_CompositionMatrix6 = float4x4.identity;
		compositionParameters.m_CompositionMatrix7 = float4x4.identity;
		compositionParameters.m_CompositionSync0 = new float4(0.2f, 0.4f, 0.6f, 0.8f);
		compositionParameters.m_CompositionSync1 = new float4(0.2f, 0.4f, 0.6f, 0.8f);
		compositionParameters.m_CompositionSync2 = new float4(0.2f, 0.4f, 0.6f, 0.8f);
		compositionParameters.m_CompositionSync3 = new float4(0.2f, 0.4f, 0.6f, 0.8f);
	}
```

- `private static CalculateMappingOffsets(Game.Net.Segment segment, Unity.Mathematics.float4& leftOffsets, Unity.Mathematics.float4& rightOffsets, Unity.Mathematics.float2 leftMappingOffset, Unity.Mathematics.float2 rightMappingOffset) : System.Void`  

```csharp
private static void CalculateMappingOffsets(Segment segment, out float4 leftOffsets, out float4 rightOffsets, float2 leftMappingOffset, float2 rightMappingOffset)
	{
		float2 @float = default(float2);
		@float.x = Vector3.Distance(segment.m_Left.a, segment.m_Left.b);
		@float.y = Vector3.Distance(segment.m_Left.c, segment.m_Left.d);
		float2 float2 = default(float2);
		float2.x = Vector3.Distance(segment.m_Right.a, segment.m_Right.b);
		float2.y = Vector3.Distance(segment.m_Right.c, segment.m_Right.d);
		@float *= (leftMappingOffset.y - leftMappingOffset.x) / math.max(1f, segment.m_Length.x);
		float2 *= (rightMappingOffset.y - rightMappingOffset.x) / math.max(1f, segment.m_Length.y);
		leftOffsets = new float4(leftMappingOffset.x, leftMappingOffset.x + @float.x, leftMappingOffset.y - @float.y, leftMappingOffset.y);
		rightOffsets = new float4(rightMappingOffset.x, rightMappingOffset.x + float2.x, rightMappingOffset.y - float2.y, rightMappingOffset.y);
	}
```

- `public static CalculateNetObjectSubMeshData(Game.Objects.NetObject netObject) : Game.Prefabs.SubMeshFlags`  

```csharp
public static SubMeshFlags CalculateNetObjectSubMeshData(Game.Objects.NetObject netObject)
	{
		return (SubMeshFlags)((((netObject.m_Flags & NetObjectFlags.TrackPassThrough) != 0) ? 4096 : 2048) | (((netObject.m_Flags & NetObjectFlags.Backward) != 0) ? 8388608 : 4194304));
	}
```

- `public static CalculateNodeParameters(Game.Net.EdgeNodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters) : System.Void`  

```csharp
public static void CalculateNodeParameters(EdgeNodeGeometry nodeGeometry, NetCompositionData prefabCompositionData, out CompositionParameters compositionParameters)
	{
		float3 @float = MathUtils.Center(nodeGeometry.m_Bounds);
		float4 mappingOffsets = new float4(0f, 1f / 3f, 2f / 3f, 1f) * prefabCompositionData.m_Width;
		compositionParameters.m_TransformMatrix = TransformHelper.Translate(@float);
		compositionParameters.m_CompositionSync0 = prefabCompositionData.m_SyncVertexOffsetsLeft;
		compositionParameters.m_CompositionSync1 = nodeGeometry.m_SyncVertexTargetsLeft;
		compositionParameters.m_CompositionSync2 = prefabCompositionData.m_SyncVertexOffsetsRight;
		compositionParameters.m_CompositionSync3 = nodeGeometry.m_SyncVertexTargetsRight;
		if (nodeGeometry.m_MiddleRadius > 0f)
		{
			float2 float2 = nodeGeometry.m_Left.m_Length + nodeGeometry.m_Right.m_Length;
			CalculateMappingOffsets(nodeGeometry.m_Left, out var leftOffsets, out var rightOffsets, new float2(0f, nodeGeometry.m_Left.m_Length.x), new float2(0f, nodeGeometry.m_Left.m_Length.y));
			CalculateMappingOffsets(nodeGeometry.m_Right, out var leftOffsets2, out var rightOffsets2, new float2(nodeGeometry.m_Left.m_Length.x, float2.x), new float2(nodeGeometry.m_Left.m_Length.y, float2.y));
			float3 direction = MathUtils.StartTangent(nodeGeometry.m_Left.m_Left);
			float3 direction2 = MathUtils.StartTangent(nodeGeometry.m_Left.m_Right);
			MathUtils.Divide(nodeGeometry.m_Middle, out var output, out var output2, 0.99f);
			float4 mappingOffsets2 = math.lerp(leftOffsets, rightOffsets, 0.5f);
			float4 mappingOffsets3 = math.lerp(leftOffsets2, rightOffsets2, 0.5f);
			compositionParameters.m_CompositionMatrix0 = BuildEdgeMatrix(nodeGeometry.m_Left.m_Left, @float, leftOffsets);
			compositionParameters.m_CompositionMatrix1 = BuildEdgeMatrix(nodeGeometry.m_Right.m_Left, @float, leftOffsets2);
			compositionParameters.m_CompositionMatrix2 = BuildEdgeMatrix(nodeGeometry.m_Left.m_Right, @float, rightOffsets);
			compositionParameters.m_CompositionMatrix3 = BuildEdgeMatrix(nodeGeometry.m_Right.m_Right, @float, rightOffsets2);
			compositionParameters.m_CompositionMatrix4 = BuildEdgeMatrix(output, @float, mappingOffsets2);
			compositionParameters.m_CompositionMatrix5 = BuildEdgeMatrix(output2, @float, mappingOffsets3);
			compositionParameters.m_CompositionMatrix6 = BuildEdgeMatrix(BuildCurve(nodeGeometry.m_Left.m_Left.a, direction, prefabCompositionData.m_Width), @float, mappingOffsets);
			compositionParameters.m_CompositionMatrix7 = BuildEdgeMatrix(BuildCurve(nodeGeometry.m_Left.m_Right.a, direction2, prefabCompositionData.m_Width), @float, mappingOffsets);
		}
		else
		{
			CalculateMappingOffsets(nodeGeometry.m_Left, out var leftOffsets3, out var rightOffsets3, new float2(0f, nodeGeometry.m_Left.m_Length.x), new float2(0f, nodeGeometry.m_Left.m_Length.y));
			CalculateMappingOffsets(nodeGeometry.m_Right, out var leftOffsets4, out var rightOffsets4, new float2(0f, nodeGeometry.m_Right.m_Length.x), new float2(0f, nodeGeometry.m_Right.m_Length.y));
			float3 direction3 = MathUtils.StartTangent(nodeGeometry.m_Left.m_Left);
			float3 direction4 = MathUtils.StartTangent(nodeGeometry.m_Right.m_Right);
			compositionParameters.m_CompositionMatrix0 = BuildEdgeMatrix(nodeGeometry.m_Left.m_Left, @float, leftOffsets3);
			compositionParameters.m_CompositionMatrix1 = BuildEdgeMatrix(nodeGeometry.m_Right.m_Left, @float, leftOffsets4);
			compositionParameters.m_CompositionMatrix2 = BuildEdgeMatrix(nodeGeometry.m_Left.m_Right, @float, rightOffsets3);
			compositionParameters.m_CompositionMatrix3 = BuildEdgeMatrix(nodeGeometry.m_Right.m_Right, @float, rightOffsets4);
			compositionParameters.m_CompositionMatrix4 = BuildEdgeMatrix(nodeGeometry.m_Middle, @float, math.lerp(leftOffsets4, rightOffsets3, 0.5f));
			compositionParameters.m_CompositionMatrix5 = float4x4.identity;
			compositionParameters.m_CompositionMatrix6 = BuildEdgeMatrix(BuildCurve(nodeGeometry.m_Left.m_Left.a, direction3, prefabCompositionData.m_Width), @float, mappingOffsets);
			compositionParameters.m_CompositionMatrix7 = BuildEdgeMatrix(BuildCurve(nodeGeometry.m_Right.m_Right.a, direction4, prefabCompositionData.m_Width), @float, mappingOffsets);
		}
	}
```

- `public static CalculateOrphanParameters(Game.Net.Node node, Game.Net.NodeGeometry nodeGeometry, Game.Prefabs.NetCompositionData prefabCompositionData, System.Boolean isPrimary, Game.Rendering.BatchDataHelpers+CompositionParameters& compositionParameters) : System.Void`  

```csharp
public static void CalculateOrphanParameters(Node node, NodeGeometry nodeGeometry, NetCompositionData prefabCompositionData, bool isPrimary, out CompositionParameters compositionParameters)
	{
		float3 @float = MathUtils.Center(nodeGeometry.m_Bounds);
		Segment segment = default(Segment);
		Bezier4x3 left;
		float3 direction;
		if (isPrimary)
		{
			segment.m_Left.a = new float3(node.m_Position.x - prefabCompositionData.m_Width * 0.5f, node.m_Position.y, node.m_Position.z);
			segment.m_Left.b = new float3(node.m_Position.x - prefabCompositionData.m_Width * 0.5f, node.m_Position.y, node.m_Position.z + prefabCompositionData.m_Width * 0.2761424f);
			segment.m_Left.c = new float3(node.m_Position.x - prefabCompositionData.m_Width * 0.2761424f, node.m_Position.y, node.m_Position.z + prefabCompositionData.m_Width * 0.5f);
			segment.m_Left.d = new float3(node.m_Position.x, node.m_Position.y, node.m_Position.z + prefabCompositionData.m_Width * 0.5f);
			segment.m_Right = new Bezier4x3(node.m_Position, node.m_Position, node.m_Position, node.m_Position);
			segment.m_Length = new float2(prefabCompositionData.m_Width * (MathF.PI / 2f), 0f);
			left = segment.m_Left;
			left.a.x += prefabCompositionData.m_Width;
			left.b.x += prefabCompositionData.m_Width;
			left.c.x = node.m_Position.x * 2f - left.c.x;
			direction = new float3(0f, 0f, 1f);
		}
		else
		{
			segment.m_Left.a = new float3(node.m_Position.x + prefabCompositionData.m_Width * 0.5f, node.m_Position.y, node.m_Position.z);
			segment.m_Left.b = new float3(node.m_Position.x + prefabCompositionData.m_Width * 0.5f, node.m_Position.y, node.m_Position.z - prefabCompositionData.m_Width * 0.2761424f);
			segment.m_Left.c = new float3(node.m_Position.x + prefabCompositionData.m_Width * 0.2761424f, node.m_Position.y, node.m_Position.z - prefabCompositionData.m_Width * 0.5f);
			segment.m_Left.d = new float3(node.m_Position.x, node.m_Position.y, node.m_Position.z - prefabCompositionData.m_Width * 0.5f);
			segment.m_Right = new Bezier4x3(node.m_Position, node.m_Position, node.m_Position, node.m_Position);
			segment.m_Length = new float2(prefabCompositionData.m_Width * (MathF.PI / 2f), 0f);
			left = segment.m_Left;
			left.a.x -= prefabCompositionData.m_Width;
			left.b.x -= prefabCompositionData.m_Width;
			left.c.x = node.m_Position.x * 2f - left.c.x;
			direction = new float3(0f, 0f, -1f);
		}
		CalculateMappingOffsets(segment, out var leftOffsets, out var rightOffsets, new float2(0f, segment.m_Length.x), new float2(0f, 0f));
		float4 mappingOffsets = new float4(0f, 1f / 3f, 2f / 3f, 1f) * prefabCompositionData.m_Width;
		compositionParameters.m_TransformMatrix = TransformHelper.Translate(@float);
		compositionParameters.m_CompositionSync0 = prefabCompositionData.m_SyncVertexOffsetsLeft;
		compositionParameters.m_CompositionSync1 = prefabCompositionData.m_SyncVertexOffsetsLeft;
		compositionParameters.m_CompositionSync2 = prefabCompositionData.m_SyncVertexOffsetsRight;
		compositionParameters.m_CompositionSync3 = prefabCompositionData.m_SyncVertexOffsetsRight;
		compositionParameters.m_CompositionMatrix0 = BuildEdgeMatrix(segment.m_Left, @float, leftOffsets);
		compositionParameters.m_CompositionMatrix1 = BuildEdgeMatrix(segment.m_Right, @float, rightOffsets);
		compositionParameters.m_CompositionMatrix2 = compositionParameters.m_CompositionMatrix1;
		compositionParameters.m_CompositionMatrix3 = BuildEdgeMatrix(left, @float, leftOffsets);
		compositionParameters.m_CompositionMatrix4 = compositionParameters.m_CompositionMatrix1;
		compositionParameters.m_CompositionMatrix5 = float4x4.identity;
		compositionParameters.m_CompositionMatrix6 = BuildEdgeMatrix(BuildCurve(segment.m_Left.a, direction, prefabCompositionData.m_Width), @float, mappingOffsets);
		compositionParameters.m_CompositionMatrix7 = BuildEdgeMatrix(BuildCurve(left.a, direction, prefabCompositionData.m_Width), @float, mappingOffsets);
	}
```

- `public static CalculateQuantitySubMeshData(Game.Objects.Quantity quantity, Game.Prefabs.QuantityObjectData quantityObjectData, System.Boolean editorMode) : Game.Prefabs.SubMeshFlags`  

```csharp
public static SubMeshFlags CalculateQuantitySubMeshData(Quantity quantity, QuantityObjectData quantityObjectData, bool editorMode)
	{
		if (editorMode)
		{
			if ((quantityObjectData.m_StepMask & 1) == 0)
			{
				return SubMeshFlags.RequireFull;
			}
			return SubMeshFlags.RequireEmpty;
		}
		switch (quantityObjectData.m_StepMask & 6)
		{
		case 6u:
			if (quantity.m_Fullness > 66)
			{
				return SubMeshFlags.RequireFull;
			}
			if (quantity.m_Fullness > 33)
			{
				return SubMeshFlags.RequirePartial2;
			}
			if (quantity.m_Fullness > 0)
			{
				return SubMeshFlags.RequirePartial1;
			}
			return SubMeshFlags.RequireEmpty;
		case 4u:
			if (quantity.m_Fullness > 50)
			{
				return SubMeshFlags.RequireFull;
			}
			if (quantity.m_Fullness > 0)
			{
				return SubMeshFlags.RequirePartial2;
			}
			return SubMeshFlags.RequireEmpty;
		case 2u:
			if (quantity.m_Fullness > 50)
			{
				return SubMeshFlags.RequireFull;
			}
			if (quantity.m_Fullness > 0)
			{
				return SubMeshFlags.RequirePartial1;
			}
			return SubMeshFlags.RequireEmpty;
		default:
			if (quantity.m_Fullness == 0)
			{
				return SubMeshFlags.RequireEmpty;
			}
			return SubMeshFlags.RequireFull;
		}
	}
```

- `public static CalculateStackSubMeshData(Game.Objects.Stack stack, Game.Prefabs.StackData stackData, Unity.Mathematics.int3& tileCounts, Unity.Mathematics.float3& offsets, Unity.Mathematics.float3& scale) : Game.Prefabs.SubMeshFlags`  

```csharp
public static void CalculateStackSubMeshData(StackData stackData, float3 offsets, float3 scales, int tileIndex, SubMeshFlags subMeshFlags, ref float3 subMeshPosition, ref float3 subMeshScale)
	{
		float num;
		float num2;
		if ((subMeshFlags & SubMeshFlags.IsStackStart) != 0)
		{
			num = offsets.x + scales.x * MathUtils.Size(stackData.m_FirstBounds) * (float)tileIndex;
			num2 = scales.x;
		}
		else if ((subMeshFlags & SubMeshFlags.IsStackMiddle) != 0)
		{
			num = offsets.y + scales.y * MathUtils.Size(stackData.m_MiddleBounds) * (float)tileIndex;
			num2 = scales.y;
		}
		else
		{
			num = offsets.z + scales.z * MathUtils.Size(stackData.m_LastBounds) * (float)tileIndex;
			num2 = scales.z;
		}
		switch (stackData.m_Direction)
		{
		case StackDirection.Right:
			subMeshPosition.x += num;
			subMeshScale.x = num2;
			break;
		case StackDirection.Up:
			subMeshPosition.y += num;
			subMeshScale.y = num2;
			break;
		case StackDirection.Forward:
			subMeshPosition.z += num;
			subMeshScale.z = num2;
			break;
		}
	}
```

- `public static CalculateStackSubMeshData(Game.Prefabs.StackData stackData, Unity.Mathematics.float3 offsets, Unity.Mathematics.float3 scales, System.Int32 tileIndex, Game.Prefabs.SubMeshFlags subMeshFlags, Unity.Mathematics.float3& subMeshPosition, Unity.Mathematics.float3& subMeshScale) : System.Void`  

```csharp
public static void CalculateStackSubMeshData(StackData stackData, float3 offsets, float3 scales, int tileIndex, SubMeshFlags subMeshFlags, ref float3 subMeshPosition, ref float3 subMeshScale)
	{
		float num;
		float num2;
		if ((subMeshFlags & SubMeshFlags.IsStackStart) != 0)
		{
			num = offsets.x + scales.x * MathUtils.Size(stackData.m_FirstBounds) * (float)tileIndex;
			num2 = scales.x;
		}
		else if ((subMeshFlags & SubMeshFlags.IsStackMiddle) != 0)
		{
			num = offsets.y + scales.y * MathUtils.Size(stackData.m_MiddleBounds) * (float)tileIndex;
			num2 = scales.y;
		}
		else
		{
			num = offsets.z + scales.z * MathUtils.Size(stackData.m_LastBounds) * (float)tileIndex;
			num2 = scales.z;
		}
		switch (stackData.m_Direction)
		{
		case StackDirection.Right:
			subMeshPosition.x += num;
			subMeshScale.x = num2;
			break;
		case StackDirection.Up:
			subMeshPosition.y += num;
			subMeshScale.y = num2;
			break;
		case StackDirection.Forward:
			subMeshPosition.z += num;
			subMeshScale.z = num2;
			break;
		}
	}
```

- `public static CalculateTreeSubMeshData(Game.Objects.Tree tree, Game.Prefabs.GrowthScaleData growthScaleData, Unity.Mathematics.float3& scale) : Game.Prefabs.SubMeshFlags`  

```csharp
public static SubMeshFlags CalculateTreeSubMeshData(Tree tree, GrowthScaleData growthScaleData, out float3 scale)
	{
		switch (tree.m_State & (TreeState.Teen | TreeState.Adult | TreeState.Elderly | TreeState.Dead | TreeState.Stump))
		{
		case TreeState.Teen:
			if (tree.m_Growth < 128)
			{
				scale = math.lerp(math.sqrt(growthScaleData.m_ChildSize / growthScaleData.m_TeenSize), 1f, (float)(int)tree.m_Growth * (1f / 128f));
			}
			else
			{
				scale = math.lerp(1f, math.sqrt(growthScaleData.m_AdultSize / growthScaleData.m_TeenSize), (float)(tree.m_Growth - 128) * (1f / 128f));
			}
			return SubMeshFlags.RequireTeen;
		case TreeState.Adult:
			if (tree.m_Growth < 128)
			{
				scale = math.lerp(math.sqrt(growthScaleData.m_TeenSize / growthScaleData.m_AdultSize), 1f, (float)(int)tree.m_Growth * (1f / 128f));
			}
			else
			{
				scale = math.lerp(1f, math.sqrt(growthScaleData.m_ElderlySize / growthScaleData.m_AdultSize), (float)(tree.m_Growth - 128) * (1f / 128f));
			}
			return SubMeshFlags.RequireAdult;
		case TreeState.Elderly:
			if (tree.m_Growth < 128)
			{
				scale = math.lerp(math.sqrt(growthScaleData.m_AdultSize / growthScaleData.m_ElderlySize), 1f, (float)(int)tree.m_Growth * (1f / 128f));
			}
			else
			{
				scale = math.lerp(1f, math.sqrt(growthScaleData.m_DeadSize / growthScaleData.m_ElderlySize), (float)(tree.m_Growth - 128) * (1f / 128f));
			}
			return SubMeshFlags.RequireElderly;
		case TreeState.Dead:
			if (tree.m_Growth < 128)
			{
				scale = math.lerp(math.sqrt(growthScaleData.m_ElderlySize / growthScaleData.m_DeadSize), 1f, (float)(int)tree.m_Growth * (1f / 128f));
			}
			else
			{
				scale = 1f;
			}
			return SubMeshFlags.RequireDead;
		case TreeState.Stump:
			scale = 1f;
			return SubMeshFlags.RequireStump;
		default:
			if (tree.m_Growth < 128)
			{
				scale = math.lerp(math.sqrt(growthScaleData.m_ChildSize / growthScaleData.m_TeenSize), 1f, (float)(int)tree.m_Growth * (1f / 128f));
			}
			else
			{
				scale = math.lerp(1f, math.sqrt(growthScaleData.m_TeenSize / growthScaleData.m_ChildSize), (float)(tree.m_Growth - 128) * (1f / 128f));
			}
			return SubMeshFlags.RequireChild;
		}
	}
```

- `public static GetAnimationCoordinate(Game.Prefabs.AnimationClip clip, System.Single time, System.Single previousTime) : Unity.Mathematics.float3`  

```csharp
public static float3 GetAnimationCoordinate(Game.Prefabs.AnimationClip clip, float time, float previousTime)
	{
		float2 x = new float2(time, previousTime);
		x /= clip.m_AnimationLength;
		return new float3((math.select(math.saturate(x), math.frac(x), clip.m_Playback != AnimationPlayback.Once) * clip.m_TextureRange + clip.m_TextureOffset) * clip.m_TextureWidth + 0.5f, clip.m_OneOverTextureWidth);
	}
```

- `public static GetBoneParameters(Game.Rendering.Skeleton skeleton) : Unity.Mathematics.float2`  

```csharp
public static float2 GetBoneParameters(Animated animated)
	{
		uint x = math.select(animated.m_BoneAllocation.End - 1, 0u, animated.m_BoneAllocation.End == 0);
		return new float2(math.asfloat(animated.m_BoneAllocation.Begin), math.asfloat(x));
	}
```

- `public static GetBoneParameters(Game.Rendering.Animated animated) : Unity.Mathematics.float2`  

```csharp
public static float2 GetBoneParameters(Animated animated)
	{
		uint x = math.select(animated.m_BoneAllocation.End - 1, 0u, animated.m_BoneAllocation.End == 0);
		return new float2(math.asfloat(animated.m_BoneAllocation.Begin), math.asfloat(x));
	}
```

- `public static GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, Game.Buildings.CitizenPresence citizenPresence, System.Single lightFactor, System.Boolean abandoned, System.Boolean electricity) : Unity.Mathematics.float4`  

```csharp
public static float4 GetBuildingState(PseudoRandomSeed pseudoRandomSeed, int passengersCount, int passengerCapacity, float lightFactor, bool destroyed)
	{
		Unity.Mathematics.Random random = pseudoRandomSeed.GetRandom(PseudoRandomSeed.kBuildingState);
		float num = (float)passengersCount / (float)math.max(1, passengerCapacity);
		float y = math.select(0.2f + num * 0.0031372549f, 0f, destroyed) * lightFactor;
		float z = math.select(0.09f, 0f, destroyed);
		return new float4(random.NextFloat(1f), y, z, 0f);
	}
```

- `public static GetBuildingState(Game.Common.PseudoRandomSeed pseudoRandomSeed, System.Int32 passengersCount, System.Int32 passengerCapacity, System.Single lightFactor, System.Boolean destroyed) : Unity.Mathematics.float4`  

```csharp
public static float4 GetBuildingState(PseudoRandomSeed pseudoRandomSeed, int passengersCount, int passengerCapacity, float lightFactor, bool destroyed)
	{
		Unity.Mathematics.Random random = pseudoRandomSeed.GetRandom(PseudoRandomSeed.kBuildingState);
		float num = (float)passengersCount / (float)math.max(1, passengerCapacity);
		float y = math.select(0.2f + num * 0.0031372549f, 0f, destroyed) * lightFactor;
		float z = math.select(0.09f, 0f, destroyed);
		return new float4(random.NextFloat(1f), y, z, 0f);
	}
```

- `public static GetDamage(Game.Objects.Surface surface, Game.Objects.Damaged damaged, Game.Events.OnFire onFire) : Unity.Mathematics.float4`  

```csharp
public static float4 GetDamage(Surface surface, Damaged damaged, OnFire onFire)
	{
		float2 @float = 1f - new float2((float)(int)surface.m_Dirtyness * 0.003921569f, damaged.m_Damage.x);
		float4 result = default(float4);
		result.x = 1f - @float.x * @float.y;
		result.y = damaged.m_Damage.y;
		result.z = damaged.m_Damage.z;
		result.w = onFire.m_Intensity * 0.01f;
		return result;
	}
```

- `public static GetLightParameters(Game.Rendering.Emissive emissive) : Unity.Mathematics.float2`  

```csharp
public static float2 GetLightParameters(Emissive emissive)
	{
		uint x = math.select(emissive.m_BufferAllocation.End - 1, 0u, emissive.m_BufferAllocation.End == 0);
		return new float2(math.asfloat(emissive.m_BufferAllocation.Begin), math.asfloat(x));
	}
```

- `public static GetTileCount(Game.Net.Curve curve, System.Single length, System.Int32 tilingCount, System.Boolean geometryTiling, System.Int32& clipCount) : System.Int32`  

```csharp
public static int GetTileCount(Curve curve, float length, int tilingCount, bool geometryTiling, out int clipCount)
	{
		if (tilingCount != 0)
		{
			float num = curve.m_Length / math.max(1f, length);
			clipCount = Mathf.RoundToInt(num * (float)tilingCount);
			int y = (clipCount + tilingCount - 1) / tilingCount;
			return math.select(math.min(1, y), math.min(256, y), geometryTiling);
		}
		if (geometryTiling)
		{
			float num2 = curve.m_Length / math.max(1f, length);
			clipCount = 0;
			return math.clamp(Mathf.CeilToInt(num2 - 0.0001f), 1, 256);
		}
		clipCount = 0;
		return 1;
	}
```

- `public static GetWetness(Game.Objects.Surface surface) : Unity.Mathematics.float4`  

```csharp
public static float4 GetWetness(Surface surface)
	{
		return new float4((int)surface.m_Wetness, (int)surface.m_SnowAmount, (int)surface.m_AccumulatedWetness, (int)surface.m_AccumulatedSnow) * 0.003921569f;
	}
```


## Nested types

- `Game.Rendering.BatchDataHelpers+CompositionParameters`  

