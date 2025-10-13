# Game.Prefabs.NetCompositionHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NetCompositionHelpers
{
    public static System.Void AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    public static System.Void CalculateCompositionData(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    private static System.Void CalculateCompositionPieceOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData);
    public static System.Void CalculateMinLod(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> meshDatas);
    public static System.Void CalculatePlaceableData(Game.Prefabs.PlaceableNetComposition& placeableData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetPieceData> placeableNetPieceData);
    public static System.Void CalculateRoundaboutSize(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    private static System.Void CalculateSyncVertexOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData);
    private static System.Int32 FindClosestLane(Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> lanes, System.Int32 startIndex, Unity.Mathematics.float3 position, Game.Prefabs.LaneFlags flags);
    public static System.Void GetCompositionPieces(Unity.Collections.NativeList<Game.Prefabs.NetCompositionPiece> resultBuffer, Unity.Collections.NativeArray<Game.Prefabs.NetGeometrySection> geometrySections, Game.Prefabs.CompositionFlags flags, Unity.Entities.BufferLookup<Game.Prefabs.NetSubSection> subSectionData, Unity.Entities.BufferLookup<Game.Prefabs.NetSectionPiece> sectionPieceData);
    public static Game.Prefabs.CompositionFlags GetElevationFlags(Game.Net.Elevation startElevation, Game.Net.Elevation middleElevation, Game.Net.Elevation endElevation, Game.Prefabs.NetGeometryData prefabGeometryData);
    public static System.Void GetRequirementFlags(Game.Prefabs.NetPieceRequirements[] requirements, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags);
    public static System.Void GetRequirementFlags(Game.Prefabs.NetPieceRequirements requirement, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags);
    private static System.Boolean HasRoad(Unity.Entities.Entity piece, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
    public static Game.Prefabs.CompositionFlags InvertCompositionFlags(Game.Prefabs.CompositionFlags flags);
    public static Game.Prefabs.NetSectionFlags InvertSectionFlags(Game.Prefabs.NetSectionFlags flags);
    public static System.Boolean TestEdgeFlags(Game.Prefabs.NetGeometryEdgeState edgeState, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestEdgeFlags(Game.Prefabs.NetGeometryNodeState nodeState, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestEdgeFlags(Game.Prefabs.ElectricityConnectionData electricityConnectionData, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestEdgeMatch(Game.Prefabs.NetGeometryNodeState nodeState, Unity.Mathematics.bool2 match);
    public static System.Boolean TestLaneFlags(Game.Prefabs.AuxiliaryNetLane lane, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestObjectFlags(Game.Prefabs.NetPieceObject _object, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
    public static System.Boolean TestPieceFlags(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
    public static System.Boolean TestPieceFlags2(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
    public static System.Boolean TestSectionFlags(Game.Prefabs.NetGeometrySection section, Game.Prefabs.CompositionFlags compositionFlags);
    public static System.Boolean TestSubSectionFlags(Game.Prefabs.NetSubSection subSection, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags);
}
```


## Methods

- `public static AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  

```csharp
public static System.Void AddCompositionLanes<TNetCompositionPieceList>(Unity.Entities.Entity entity, Game.Prefabs.NetCompositionData& compositionData, TNetCompositionPieceList pieces, Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> netLanes, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionCarriageway> carriageways, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes);
```

- `public static CalculateCompositionData(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  

```csharp
public static void CalculateCompositionData(ref NetCompositionData compositionData, NativeArray<NetCompositionPiece> pieces, ComponentLookup<NetPieceData> netPieceData, ComponentLookup<NetLaneData> netLaneData, ComponentLookup<NetVertexMatchData> netVertexMatchData, BufferLookup<NetPieceLane> netPieceLanes)
	{
		CalculateCompositionPieceOffsets(ref compositionData, pieces, netPieceData);
		CalculateSyncVertexOffsets(ref compositionData, pieces, netVertexMatchData);
		CalculateRoundaboutSize(ref compositionData, pieces, netLaneData, netPieceLanes);
	}
```

- `private static CalculateCompositionPieceOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetPieceData> netPieceData) : System.Void`  

```csharp
private static void CalculateCompositionPieceOffsets(ref NetCompositionData compositionData, NativeArray<NetCompositionPiece> pieces, ComponentLookup<NetPieceData> netPieceData)
	{
		compositionData.m_Width = 0f;
		compositionData.m_MiddleOffset = 0f;
		compositionData.m_WidthOffset = 0f;
		compositionData.m_NodeOffset = 0f;
		compositionData.m_HeightRange = new Bounds1(float.MaxValue, float.MinValue);
		compositionData.m_SurfaceHeight = new Bounds1(float.MaxValue, float.MinValue);
		bool test = (compositionData.m_Flags.m_General & CompositionFlags.General.Invert) != 0;
		float num = 0f;
		float num2 = 0f;
		float num3 = 0f;
		float num4 = 0f;
		float num5 = 0f;
		float num6 = 0f;
		float num7 = 0f;
		bool flag = false;
		bool flag2 = false;
		bool flag3 = false;
		bool flag4 = false;
		int num8 = 0;
		while (num8 < pieces.Length)
		{
			NetCompositionPiece value = pieces[num8];
			bool flag5 = (value.m_SectionFlags & NetSectionFlags.Underground) != 0;
			bool flag6 = (value.m_SectionFlags & NetSectionFlags.Overhead) != 0;
			bool test2 = (value.m_SectionFlags & NetSectionFlags.Invert) != 0;
			bool test3 = (value.m_SectionFlags & NetSectionFlags.FlipMesh) != 0;
			bool2 test4 = new bool2((value.m_SectionFlags & NetSectionFlags.Left) != 0, (value.m_SectionFlags & NetSectionFlags.Right) != 0);
			NetPieceData netPieceData2 = netPieceData[value.m_Piece];
			float num9 = netPieceData2.m_Width;
			if (!flag5 || (compositionData.m_Flags.m_General & CompositionFlags.General.Elevated) == 0)
			{
				compositionData.m_HeightRange |= value.m_Offset.y + netPieceData2.m_HeightRange;
			}
			if (!flag5 && !flag6 && (value.m_PieceFlags & NetPieceFlags.PreserveShape) == 0)
			{
				if ((value.m_PieceFlags & NetPieceFlags.Side) != 0)
				{
					float4 falseValue = math.select(netPieceData2.m_SurfaceHeights, netPieceData2.m_SurfaceHeights.yxwz, test2);
					falseValue = math.select(falseValue, falseValue.zwxy, test3);
					compositionData.m_EdgeHeights = math.select(compositionData.m_EdgeHeights, falseValue, test4.xyxy);
					compositionData.m_SideConnectionOffset = math.select(compositionData.m_SideConnectionOffset, netPieceData2.m_SideConnectionOffset, test4);
				}
				if ((value.m_PieceFlags & NetPieceFlags.Surface) != 0)
				{
					compositionData.m_SurfaceHeight.min = math.min(compositionData.m_SurfaceHeight.min, value.m_Offset.y + math.cmin(netPieceData2.m_SurfaceHeights));
					compositionData.m_SurfaceHeight.max = math.max(compositionData.m_SurfaceHeight.max, value.m_Offset.y + math.cmax(netPieceData2.m_SurfaceHeights));
					flag = true;
				}
			}
			compositionData.m_WidthOffset = math.max(compositionData.m_WidthOffset, netPieceData2.m_WidthOffset);
			compositionData.m_NodeOffset = math.max(compositionData.m_NodeOffset, netPieceData2.m_NodeOffset);
			value.m_Size.x = netPieceData2.m_Width;
			value.m_Size.y = netPieceData2.m_HeightRange.max - netPieceData2.m_HeightRange.min;
			value.m_Size.z = netPieceData2.m_Length;
			int i;
			for (i = num8 + 1; i < pieces.Length; i++)
			{
				NetCompositionPiece value2 = pieces[i];
				if (value2.m_SectionIndex != value.m_SectionIndex)
				{
					break;
				}
				NetPieceData netPieceData3 = netPieceData[value2.m_Piece];
				num9 = math.max(num9, netPieceData3.m_Width);
				if (!flag5 || (compositionData.m_Flags.m_General & CompositionFlags.General.Elevated) == 0)
				{
					compositionData.m_HeightRange |= value2.m_Offset.y + netPieceData3.m_HeightRange;
				}
				if (!flag5 && !flag6 && (value2.m_PieceFlags & NetPieceFlags.PreserveShape) == 0)
				{
					if ((value2.m_PieceFlags & NetPieceFlags.Side) != 0)
					{
						float4 falseValue2 = math.select(netPieceData3.m_SurfaceHeights, netPieceData3.m_SurfaceHeights.yxwz, test2);
						falseValue2 = math.select(falseValue2, falseValue2.zwxy, test3);
						compositionData.m_EdgeHeights = math.select(compositionData.m_EdgeHeights, falseValue2, test4.xyxy);
					}
					if ((value2.m_PieceFlags & NetPieceFlags.Surface) != 0)
					{
						compositionData.m_SurfaceHeight.min = math.min(compositionData.m_SurfaceHeight.min, value2.m_Offset.y + math.cmin(netPieceData3.m_SurfaceHeights));
						compositionData.m_SurfaceHeight.max = math.max(compositionData.m_SurfaceHeight.max, value2.m_Offset.y + math.cmax(netPieceData3.m_SurfaceHeights));
						flag = true;
					}
				}
				compositionData.m_WidthOffset = math.max(compositionData.m_WidthOffset, netPieceData3.m_WidthOffset);
				compositionData.m_NodeOffset = math.max(compositionData.m_NodeOffset, netPieceData3.m_NodeOffset);
				value2.m_Size.x = netPieceData3.m_Width;
				value2.m_Size.y = netPieceData3.m_HeightRange.max - netPieceData3.m_HeightRange.min;
				value2.m_Size.z = netPieceData3.m_Length;
				pieces[i] = value2;
			}
			float x = value.m_Offset.x;
			if (flag5)
			{
				value.m_Offset.x += num + num9 * 0.5f;
				num += num9;
				if ((value.m_SectionFlags & (NetSectionFlags.Median | NetSectionFlags.AlignCenter)) == NetSectionFlags.Median)
				{
					num2 = value.m_Offset.x - math.select(x * 2f, 0f, test);
					num3 = x;
					flag3 = true;
				}
				else if ((value.m_SectionFlags & (NetSectionFlags.Right | NetSectionFlags.AlignCenter)) == NetSectionFlags.Right && !flag3)
				{
					num2 = value.m_Offset.x - value.m_Size.x * 0.5f - math.select(x * 2f, 0f, test);
					num3 = x;
					flag3 = true;
				}
			}
			else if (flag6)
			{
				value.m_Offset.x += num4 + num9 * 0.5f;
				num4 += num9;
				if ((value.m_SectionFlags & (NetSectionFlags.Median | NetSectionFlags.AlignCenter)) == NetSectionFlags.Median)
				{
					num5 = value.m_Offset.x - math.select(x * 2f, 0f, test);
					num6 = x;
					flag4 = true;
				}
				else if ((value.m_SectionFlags & (NetSectionFlags.Right | NetSectionFlags.AlignCenter)) == NetSectionFlags.Right && !flag4)
				{
					num5 = value.m_Offset.x - value.m_Size.x * 0.5f - math.select(x * 2f, 0f, test);
					num6 = x;
					flag4 = true;
				}
			}
			else
			{
				value.m_Offset.x += compositionData.m_Width + num9 * 0.5f;
				compositionData.m_Width += num9;
				if ((value.m_SectionFlags & (NetSectionFlags.Median | NetSectionFlags.AlignCenter)) == NetSectionFlags.Median)
				{
					compositionData.m_MiddleOffset = value.m_Offset.x - math.select(x * 2f, 0f, test);
					num7 = x;
					flag2 = true;
				}
				else if ((value.m_SectionFlags & (NetSectionFlags.Right | NetSectionFlags.AlignCenter)) == NetSectionFlags.Right && !flag2)
				{
					compositionData.m_MiddleOffset = value.m_Offset.x - value.m_Size.x * 0.5f - math.select(x * 2f, 0f, test);
					num7 = x;
					flag2 = true;
				}
			}
			pieces[num8] = value;
			for (int j = num8 + 1; j < i; j++)
			{
				NetCompositionPiece value3 = pieces[j];
				value3.m_Offset.x = value.m_Offset.x;
				pieces[j] = value3;
			}
			if ((value.m_PieceFlags & NetPieceFlags.Side) != 0 && i > num8 + 1 && (value.m_SectionFlags & (NetSectionFlags.Left | NetSectionFlags.Right)) != 0)
			{
				bool test5 = (value.m_SectionFlags & NetSectionFlags.Right) != 0;
				for (int k = num8; k < i; k++)
				{
					NetCompositionPiece value4 = pieces[k];
					float num10 = (netPieceData[value4.m_Piece].m_Width - num9) * 0.5f;
					value4.m_Offset.x += math.select(0f - num10, num10, test5);
					pieces[k] = value4;
				}
			}
			num8 = i;
		}
		if (flag3)
		{
			num2 -= num * 0.5f;
		}
		if (flag4)
		{
			num5 -= num4 * 0.5f;
		}
		if (flag2)
		{
			compositionData.m_MiddleOffset -= compositionData.m_Width * 0.5f;
		}
		if ((compositionData.m_Flags.m_General & (CompositionFlags.General.DeadEnd | CompositionFlags.General.LevelCrossing)) == CompositionFlags.General.LevelCrossing || (compositionData.m_Flags.m_General & (CompositionFlags.General.DeadEnd | CompositionFlags.General.Intersection | CompositionFlags.General.Crosswalk)) == CompositionFlags.General.Crosswalk || (compositionData.m_Flags.m_Right & CompositionFlags.Side.AbruptEnd) != 0)
		{
			compositionData.m_State |= CompositionState.BlockUTurn;
		}
		for (int l = 0; l < pieces.Length; l++)
		{
			NetCompositionPiece value5 = pieces[l];
			bool num11 = (value5.m_SectionFlags & NetSectionFlags.Underground) != 0;
			bool flag7 = (value5.m_SectionFlags & NetSectionFlags.Overhead) != 0;
			if ((value5.m_PieceFlags & (NetPieceFlags.PreserveShape | NetPieceFlags.BlockTraffic)) == NetPieceFlags.BlockTraffic)
			{
				compositionData.m_State |= CompositionState.BlockUTurn;
			}
			if ((value5.m_PieceFlags & NetPieceFlags.LowerBottomToTerrain) != 0)
			{
				compositionData.m_State |= CompositionState.LowerToTerrain;
			}
			if ((value5.m_PieceFlags & NetPieceFlags.RaiseTopToTerrain) != 0)
			{
				compositionData.m_State |= CompositionState.RaiseToTerrain;
			}
			if ((value5.m_SectionFlags & NetSectionFlags.HalfLength) != 0)
			{
				compositionData.m_State |= CompositionState.HalfLength;
			}
			if ((value5.m_SectionFlags & NetSectionFlags.Hidden) != 0)
			{
				compositionData.m_State |= CompositionState.Hidden;
			}
			if (num11)
			{
				value5.m_Offset.x -= num * 0.5f + num3;
				value5.m_Offset.x += compositionData.m_MiddleOffset - num2;
			}
			else if (flag7)
			{
				value5.m_Offset.x -= num4 * 0.5f + num6;
				value5.m_Offset.x += compositionData.m_MiddleOffset - num5;
			}
			else
			{
				value5.m_Offset.x -= compositionData.m_Width * 0.5f + num7;
			}
			pieces[l] = value5;
		}
		compositionData.m_Width = math.max(compositionData.m_Width, math.max(num, num4));
		if (compositionData.m_HeightRange.min > compositionData.m_HeightRange.max)
		{
			compositionData.m_HeightRange = default(Bounds1);
		}
		if (flag)
		{
			compositionData.m_State |= CompositionState.HasSurface;
			if ((compositionData.m_Flags.m_General & (CompositionFlags.General.Elevated | CompositionFlags.General.Tunnel)) == 0)
			{
				compositionData.m_State |= CompositionState.ExclusiveGround;
			}
		}
		else
		{
			float num12 = MathUtils.Center(compositionData.m_HeightRange);
			compositionData.m_SurfaceHeight = new Bounds1(num12, num12);
		}
	}
```

- `public static CalculateMinLod(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.MeshData> meshDatas) : System.Void`  

```csharp
public static void CalculateMinLod(ref NetCompositionData compositionData, NativeArray<NetCompositionPiece> pieces, ComponentLookup<MeshData> meshDatas)
	{
		float num = 0f;
		for (int i = 0; i < pieces.Length; i++)
		{
			num += meshDatas[pieces[i].m_Piece].m_LodBias;
		}
		if (pieces.Length != 0)
		{
			num /= (float)pieces.Length;
		}
		float2 size = new float2(compositionData.m_Width, MathUtils.Size(compositionData.m_HeightRange));
		compositionData.m_MinLod = RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(size), num);
	}
```

- `public static CalculatePlaceableData(Game.Prefabs.PlaceableNetComposition& placeableData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.PlaceableNetPieceData> placeableNetPieceData) : System.Void`  

```csharp
public static void CalculatePlaceableData(ref PlaceableNetComposition placeableData, NativeArray<NetCompositionPiece> pieces, ComponentLookup<PlaceableNetPieceData> placeableNetPieceData)
	{
		placeableData.m_ConstructionCost = 0u;
		placeableData.m_UpkeepCost = 0f;
		for (int i = 0; i < pieces.Length; i++)
		{
			NetCompositionPiece netCompositionPiece = pieces[i];
			if (placeableNetPieceData.HasComponent(netCompositionPiece.m_Piece))
			{
				PlaceableNetPieceData placeableNetPieceData2 = placeableNetPieceData[netCompositionPiece.m_Piece];
				placeableData.m_ConstructionCost += placeableNetPieceData2.m_ConstructionCost;
				placeableData.m_ElevationCost += placeableNetPieceData2.m_ElevationCost;
				placeableData.m_UpkeepCost += placeableNetPieceData2.m_UpkeepCost;
			}
		}
	}
```

- `public static CalculateRoundaboutSize(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Void`  

```csharp
public static void CalculateRoundaboutSize(ref NetCompositionData compositionData, NativeArray<NetCompositionPiece> pieces, ComponentLookup<NetLaneData> netLaneData, BufferLookup<NetPieceLane> netPieceLanes)
	{
		float2 @float = 0f;
		float2 float2 = float.MaxValue;
		float4 float3 = 0f;
		for (int i = 0; i < pieces.Length; i++)
		{
			NetCompositionPiece netCompositionPiece = pieces[i];
			if (HasRoad(netCompositionPiece.m_Piece, netLaneData, netPieceLanes))
			{
				float y = (((netCompositionPiece.m_SectionFlags & NetSectionFlags.Invert) == 0) ? ((compositionData.m_Width + netCompositionPiece.m_Size.x) * 0.5f - netCompositionPiece.m_Offset.x) : ((compositionData.m_Width + netCompositionPiece.m_Size.x) * 0.5f + netCompositionPiece.m_Offset.x));
				if ((netCompositionPiece.m_SectionFlags & NetSectionFlags.Invert) != 0 != ((netCompositionPiece.m_SectionFlags & NetSectionFlags.FlipLanes) != 0))
				{
					@float.x = math.max(@float.x, y);
					float2.y = math.min(float2.y, y);
					float3.x += netCompositionPiece.m_Size.x;
					float3.w = math.max(float3.w, netCompositionPiece.m_Size.x);
				}
				else
				{
					@float.y = math.max(@float.y, y);
					float2.x = math.min(float2.x, y);
					float3.y += netCompositionPiece.m_Size.x;
					float3.z = math.max(float3.z, netCompositionPiece.m_Size.x);
				}
			}
		}
		compositionData.m_RoundaboutSize = math.select(@float, math.max(float2, @float), float2 < float.MaxValue);
		compositionData.m_RoundaboutSize = math.select(compositionData.m_RoundaboutSize, compositionData.m_Width * 0.5f, compositionData.m_RoundaboutSize == 0f);
		compositionData.m_RoundaboutSize += math.max(float3.xy, float3.zw) / 3f;
	}
```

- `private static CalculateSyncVertexOffsets(Game.Prefabs.NetCompositionData& compositionData, Unity.Collections.NativeArray<Game.Prefabs.NetCompositionPiece> pieces, Unity.Entities.ComponentLookup<Game.Prefabs.NetVertexMatchData> netVertexMatchData) : System.Void`  

```csharp
private static void CalculateSyncVertexOffsets(ref NetCompositionData compositionData, NativeArray<NetCompositionPiece> pieces, ComponentLookup<NetVertexMatchData> netVertexMatchData)
	{
		float4 syncVertexOffsetsLeft = new float4(0f, 0f, 0f, 1f);
		float4 syncVertexOffsetsRight = new float4(0f, 1f, 1f, 1f);
		float middleOffset = compositionData.m_MiddleOffset;
		float num = compositionData.m_Width * 0.5f + middleOffset;
		float num2 = compositionData.m_Width * 0.5f - middleOffset;
		bool flag = false;
		float2 @float = default(float2);
		for (int i = 0; i < pieces.Length; i++)
		{
			NetCompositionPiece netCompositionPiece = pieces[i];
			if ((netCompositionPiece.m_SectionFlags & (NetSectionFlags.Underground | NetSectionFlags.Overhead)) != 0)
			{
				continue;
			}
			if ((netCompositionPiece.m_SectionFlags & NetSectionFlags.Median) != 0)
			{
				if (netVertexMatchData.HasComponent(netCompositionPiece.m_Piece))
				{
					NetVertexMatchData netVertexMatchData2 = netVertexMatchData[netCompositionPiece.m_Piece];
					if (!math.any(math.isnan(netVertexMatchData2.m_Offsets.xy)))
					{
						@float.x = netVertexMatchData2.m_Offsets.x;
						@float.y = math.select(netVertexMatchData2.m_Offsets.z, netVertexMatchData2.m_Offsets.y, math.isnan(netVertexMatchData2.m_Offsets.z));
						if ((netCompositionPiece.m_SectionFlags & NetSectionFlags.Invert) != 0)
						{
							@float = -@float.yx;
						}
						@float += netCompositionPiece.m_Offset.x;
						if (num > 0f)
						{
							syncVertexOffsetsLeft.w = (@float.x - middleOffset) / num + 1f;
						}
						if (num2 > 0f)
						{
							syncVertexOffsetsRight.x = (@float.y - middleOffset) / num2;
						}
						flag = true;
					}
				}
				if (!flag)
				{
					float2 float2 = netCompositionPiece.m_Offset.x;
					float2.x -= netCompositionPiece.m_Size.x * 0.5f;
					float2.y += netCompositionPiece.m_Size.x * 0.5f;
					if (num > 0f)
					{
						syncVertexOffsetsLeft.w = (float2.x - middleOffset) / num + 1f;
					}
					if (num2 > 0f)
					{
						syncVertexOffsetsRight.x = (float2.y - middleOffset) / num2;
					}
				}
			}
			else
			{
				if (!netVertexMatchData.HasComponent(netCompositionPiece.m_Piece))
				{
					continue;
				}
				NetVertexMatchData netVertexMatchData3 = netVertexMatchData[netCompositionPiece.m_Piece];
				if (math.isnan(netVertexMatchData3.m_Offsets.x))
				{
					continue;
				}
				float num3 = netVertexMatchData3.m_Offsets.x;
				for (int j = 0; j < 3; j++)
				{
					if ((netCompositionPiece.m_SectionFlags & NetSectionFlags.Invert) != 0)
					{
						num3 = 0f - num3;
					}
					num3 += netCompositionPiece.m_Offset.x;
					if ((netCompositionPiece.m_SectionFlags & NetSectionFlags.Right) != 0)
					{
						num3 = (num3 - middleOffset) / num2;
						if (syncVertexOffsetsRight.z != 1f)
						{
							syncVertexOffsetsRight.w = num3;
						}
						else if (syncVertexOffsetsRight.y != 1f)
						{
							syncVertexOffsetsRight.z = num3;
						}
						else
						{
							syncVertexOffsetsRight.y = num3;
						}
					}
					else
					{
						num3 = (num3 - middleOffset) / num + 1f;
						if (syncVertexOffsetsLeft.y != 0f)
						{
							syncVertexOffsetsLeft.x = num3;
						}
						else if (syncVertexOffsetsLeft.z != 0f)
						{
							syncVertexOffsetsLeft.y = num3;
						}
						else
						{
							syncVertexOffsetsLeft.z = num3;
						}
					}
					if (j == 0)
					{
						if (math.isnan(netVertexMatchData3.m_Offsets.y))
						{
							break;
						}
						num3 = netVertexMatchData3.m_Offsets.y;
					}
					else
					{
						if (math.isnan(netVertexMatchData3.m_Offsets.z))
						{
							break;
						}
						num3 = netVertexMatchData3.m_Offsets.z;
					}
				}
			}
		}
		if (syncVertexOffsetsLeft.x > syncVertexOffsetsLeft.y)
		{
			syncVertexOffsetsLeft.xy = syncVertexOffsetsLeft.yx;
		}
		if (syncVertexOffsetsRight.z > syncVertexOffsetsRight.w)
		{
			syncVertexOffsetsRight.zw = syncVertexOffsetsRight.wz;
		}
		if (syncVertexOffsetsLeft.y > syncVertexOffsetsLeft.z)
		{
			syncVertexOffsetsLeft.yz = syncVertexOffsetsLeft.zy;
		}
		if (syncVertexOffsetsRight.y > syncVertexOffsetsRight.z)
		{
			syncVertexOffsetsRight.yz = syncVertexOffsetsRight.zy;
		}
		if (syncVertexOffsetsLeft.x > syncVertexOffsetsLeft.y)
		{
			syncVertexOffsetsLeft.xy = syncVertexOffsetsLeft.yx;
		}
		if (syncVertexOffsetsRight.z > syncVertexOffsetsRight.w)
		{
			syncVertexOffsetsRight.zw = syncVertexOffsetsRight.wz;
		}
		if (syncVertexOffsetsLeft.z <= syncVertexOffsetsLeft.x)
		{
			syncVertexOffsetsLeft.z = math.lerp(syncVertexOffsetsLeft.x, syncVertexOffsetsLeft.w, 2f / 3f);
		}
		if (syncVertexOffsetsRight.y >= syncVertexOffsetsRight.w)
		{
			syncVertexOffsetsRight.y = math.lerp(syncVertexOffsetsRight.w, syncVertexOffsetsRight.x, 2f / 3f);
		}
		if (syncVertexOffsetsLeft.y <= syncVertexOffsetsLeft.x)
		{
			syncVertexOffsetsLeft.y = math.lerp(syncVertexOffsetsLeft.x, syncVertexOffsetsLeft.z, 0.5f);
		}
		if (syncVertexOffsetsRight.z >= syncVertexOffsetsRight.w)
		{
			syncVertexOffsetsRight.z = math.lerp(syncVertexOffsetsRight.w, syncVertexOffsetsRight.y, 0.5f);
		}
		if (syncVertexOffsetsLeft.y < syncVertexOffsetsLeft.x + 1E-05f)
		{
			syncVertexOffsetsLeft.y = syncVertexOffsetsLeft.x;
		}
		if (syncVertexOffsetsLeft.w < syncVertexOffsetsLeft.z + 1E-05f)
		{
			syncVertexOffsetsLeft.z = syncVertexOffsetsLeft.w;
		}
		if (syncVertexOffsetsRight.y < syncVertexOffsetsRight.x + 1E-05f)
		{
			syncVertexOffsetsRight.y = syncVertexOffsetsRight.x;
		}
		if (syncVertexOffsetsRight.w < syncVertexOffsetsRight.z + 1E-05f)
		{
			syncVertexOffsetsRight.z = syncVertexOffsetsRight.w;
		}
		compositionData.m_SyncVertexOffsetsLeft = syncVertexOffsetsLeft;
		compositionData.m_SyncVertexOffsetsRight = syncVertexOffsetsRight;
	}
```

- `private static FindClosestLane(Unity.Collections.NativeList<Game.Prefabs.NetCompositionLane> lanes, System.Int32 startIndex, Unity.Mathematics.float3 position, Game.Prefabs.LaneFlags flags) : System.Int32`  

```csharp
private static int FindClosestLane(NativeList<NetCompositionLane> lanes, int startIndex, float3 position, LaneFlags flags)
	{
		int num = startIndex - 1;
		int num2 = startIndex + 1;
		while (true)
		{
			if (num >= 0 && num2 < lanes.Length)
			{
				NetCompositionLane netCompositionLane = lanes[num];
				NetCompositionLane netCompositionLane2 = lanes[num2];
				if (math.lengthsq(netCompositionLane.m_Position - position) <= math.lengthsq(netCompositionLane2.m_Position - position))
				{
					if ((netCompositionLane.m_Flags & flags) != 0)
					{
						return num;
					}
					num--;
				}
				else
				{
					if ((netCompositionLane2.m_Flags & flags) != 0)
					{
						return num2;
					}
					num2++;
				}
			}
			else if (num >= 0)
			{
				if ((lanes[num].m_Flags & flags) != 0)
				{
					return num;
				}
				num--;
			}
			else
			{
				if (num2 >= lanes.Length)
				{
					break;
				}
				if ((lanes[num2].m_Flags & flags) != 0)
				{
					return num2;
				}
				num2++;
			}
		}
		return -1;
	}
```

- `public static GetCompositionPieces(Unity.Collections.NativeList<Game.Prefabs.NetCompositionPiece> resultBuffer, Unity.Collections.NativeArray<Game.Prefabs.NetGeometrySection> geometrySections, Game.Prefabs.CompositionFlags flags, Unity.Entities.BufferLookup<Game.Prefabs.NetSubSection> subSectionData, Unity.Entities.BufferLookup<Game.Prefabs.NetSectionPiece> sectionPieceData) : System.Void`  

```csharp
public static void GetCompositionPieces(NativeList<NetCompositionPiece> resultBuffer, NativeArray<NetGeometrySection> geometrySections, CompositionFlags flags, BufferLookup<NetSubSection> subSectionData, BufferLookup<NetSectionPiece> sectionPieceData)
	{
		int num = 0;
		int num2 = 0;
		CompositionFlags compositionFlags = InvertCompositionFlags(flags);
		compositionFlags.m_Left = (CompositionFlags.Side)(((uint)compositionFlags.m_Left & 0xFFFFBFFFu) | (uint)(flags.m_Left & CompositionFlags.Side.AbruptEnd));
		compositionFlags.m_Right = (CompositionFlags.Side)(((uint)compositionFlags.m_Right & 0xFFFFBFFFu) | (uint)(flags.m_Right & CompositionFlags.Side.AbruptEnd));
		for (int i = 0; i < geometrySections.Length; i++)
		{
			NetGeometrySection section;
			if ((flags.m_General & CompositionFlags.General.Invert) != 0)
			{
				section = geometrySections[geometrySections.Length - 1 - i];
				section.m_Flags ^= NetSectionFlags.Invert | NetSectionFlags.FlipLanes;
				if ((section.m_Flags & NetSectionFlags.Left) != 0)
				{
					section.m_Flags &= ~NetSectionFlags.Left;
					section.m_Flags |= NetSectionFlags.Right;
				}
				else if ((section.m_Flags & NetSectionFlags.Right) != 0)
				{
					section.m_Flags &= ~NetSectionFlags.Right;
					section.m_Flags |= NetSectionFlags.Left;
				}
			}
			else
			{
				section = geometrySections[i];
			}
			if ((flags.m_General & CompositionFlags.General.Flip) != 0)
			{
				section.m_Flags ^= NetSectionFlags.FlipLanes;
			}
			CompositionFlags compositionFlags2 = (((section.m_Flags & NetSectionFlags.Invert) != 0) ? compositionFlags : flags);
			NetPieceFlags netPieceFlags = (NetPieceFlags)0;
			if ((section.m_Flags & NetSectionFlags.HiddenSurface) != 0)
			{
				netPieceFlags |= NetPieceFlags.Surface;
			}
			if ((section.m_Flags & NetSectionFlags.HiddenBottom) != 0)
			{
				netPieceFlags |= NetPieceFlags.Bottom;
			}
			if ((section.m_Flags & NetSectionFlags.HiddenTop) != 0)
			{
				netPieceFlags |= NetPieceFlags.Top;
			}
			if ((section.m_Flags & NetSectionFlags.HiddenSide) != 0)
			{
				netPieceFlags |= NetPieceFlags.Side;
			}
			if (!TestSectionFlags(section, compositionFlags2))
			{
				continue;
			}
			NetSectionFlags sectionFlags = (((section.m_Flags & NetSectionFlags.Invert) != 0) ? InvertSectionFlags(section.m_Flags) : section.m_Flags);
			while (true)
			{
				DynamicBuffer<NetSubSection> dynamicBuffer = subSectionData[section.m_Section];
				NetSubSection subSection;
				for (int j = 0; j < dynamicBuffer.Length; j++)
				{
					subSection = dynamicBuffer[j];
					if (TestSubSectionFlags(subSection, compositionFlags2, sectionFlags))
					{
						goto IL_01bb;
					}
				}
				break;
				IL_01bb:
				section.m_Section = subSection.m_SubSection;
			}
			DynamicBuffer<NetSectionPiece> dynamicBuffer2 = sectionPieceData[section.m_Section];
			for (int k = 0; k < dynamicBuffer2.Length; k++)
			{
				NetSectionPiece piece = dynamicBuffer2[k];
				NetPieceFlags netPieceFlags2 = piece.m_Flags;
				if (!TestPieceFlags(piece, compositionFlags2, sectionFlags))
				{
					if (!TestPieceFlags2(piece, compositionFlags2, sectionFlags))
					{
						continue;
					}
					netPieceFlags2 |= NetPieceFlags.SkipBottomHalf;
				}
				NetCompositionPiece value = new NetCompositionPiece
				{
					m_Piece = piece.m_Piece,
					m_SectionFlags = section.m_Flags,
					m_PieceFlags = netPieceFlags2,
					m_SectionIndex = num,
					m_Offset = section.m_Offset + piece.m_Offset
				};
				if ((netPieceFlags & netPieceFlags2) != 0)
				{
					value.m_SectionFlags |= NetSectionFlags.Hidden;
				}
				resultBuffer.Add(in value);
				num2++;
			}
			if (num2 != 0)
			{
				num++;
				num2 = 0;
			}
		}
	}
```

- `public static GetElevationFlags(Game.Net.Elevation startElevation, Game.Net.Elevation middleElevation, Game.Net.Elevation endElevation, Game.Prefabs.NetGeometryData prefabGeometryData) : Game.Prefabs.CompositionFlags`  

```csharp
public static CompositionFlags GetElevationFlags(Elevation startElevation, Elevation middleElevation, Elevation endElevation, NetGeometryData prefabGeometryData)
	{
		CompositionFlags result = default(CompositionFlags);
		float2 @float = math.max(math.max(math.cmin(startElevation.m_Elevation), math.cmin(endElevation.m_Elevation)), middleElevation.m_Elevation);
		float3 x = new float3(math.cmin(startElevation.m_Elevation), math.cmin(endElevation.m_Elevation), math.cmin(middleElevation.m_Elevation));
		float3 x2 = new float3(math.cmax(startElevation.m_Elevation), math.cmax(endElevation.m_Elevation), math.cmax(middleElevation.m_Elevation));
		float2 float2 = math.min(math.min(math.cmax(startElevation.m_Elevation), math.cmax(endElevation.m_Elevation)), middleElevation.m_Elevation);
		if (math.all(@float >= prefabGeometryData.m_ElevationLimit * 2f) || (prefabGeometryData.m_Flags & GeometryFlags.RequireElevated) != 0)
		{
			if ((prefabGeometryData.m_Flags & GeometryFlags.ElevatedIsRaised) != 0)
			{
				result.m_Left |= CompositionFlags.Side.Raised;
				result.m_Right |= CompositionFlags.Side.Raised;
			}
			else
			{
				result.m_General |= CompositionFlags.General.Elevated;
			}
		}
		else if (math.cmax(x) <= prefabGeometryData.m_ElevationLimit * -2f && math.cmin(x2) <= prefabGeometryData.m_ElevationLimit * -3f)
		{
			result.m_General |= CompositionFlags.General.Tunnel;
		}
		else
		{
			if (@float.x >= prefabGeometryData.m_ElevationLimit)
			{
				if ((prefabGeometryData.m_Flags & GeometryFlags.RaisedIsElevated) != 0)
				{
					result.m_General |= CompositionFlags.General.Elevated;
				}
				else
				{
					result.m_Left |= CompositionFlags.Side.Raised;
				}
			}
			else if (float2.x <= 0f - prefabGeometryData.m_ElevationLimit)
			{
				if ((prefabGeometryData.m_Flags & GeometryFlags.LoweredIsTunnel) != 0)
				{
					result.m_General |= CompositionFlags.General.Tunnel;
				}
				else
				{
					result.m_Left |= CompositionFlags.Side.Lowered;
				}
			}
			if (@float.y >= prefabGeometryData.m_ElevationLimit)
			{
				if ((prefabGeometryData.m_Flags & GeometryFlags.RaisedIsElevated) != 0)
				{
					result.m_General |= CompositionFlags.General.Elevated;
				}
				else
				{
					result.m_Right |= CompositionFlags.Side.Raised;
				}
			}
			else if (float2.y <= 0f - prefabGeometryData.m_ElevationLimit)
			{
				if ((prefabGeometryData.m_Flags & GeometryFlags.LoweredIsTunnel) != 0)
				{
					result.m_General |= CompositionFlags.General.Tunnel;
				}
				else
				{
					result.m_Right |= CompositionFlags.Side.Lowered;
				}
			}
		}
		return result;
	}
```

- `public static GetRequirementFlags(Game.Prefabs.NetPieceRequirements[] requirements, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags) : System.Void`  

```csharp
public static void GetRequirementFlags(NetPieceRequirements requirement, ref CompositionFlags compositionFlags, ref NetSectionFlags sectionFlags)
	{
		switch (requirement)
		{
		case NetPieceRequirements.Node:
			compositionFlags.m_General |= CompositionFlags.General.Node;
			break;
		case NetPieceRequirements.Intersection:
			compositionFlags.m_General |= CompositionFlags.General.Intersection;
			break;
		case NetPieceRequirements.DeadEnd:
			compositionFlags.m_General |= CompositionFlags.General.DeadEnd;
			break;
		case NetPieceRequirements.Crosswalk:
			compositionFlags.m_General |= CompositionFlags.General.Crosswalk;
			break;
		case NetPieceRequirements.BusStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.Median:
			sectionFlags |= NetSectionFlags.Median;
			break;
		case NetPieceRequirements.TrainStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeTrainStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.Inverted:
			sectionFlags |= NetSectionFlags.Invert;
			break;
		case NetPieceRequirements.TaxiStand:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.LevelCrossing:
			compositionFlags.m_General |= CompositionFlags.General.LevelCrossing;
			break;
		case NetPieceRequirements.Elevated:
			compositionFlags.m_General |= CompositionFlags.General.Elevated;
			break;
		case NetPieceRequirements.Tunnel:
			compositionFlags.m_General |= CompositionFlags.General.Tunnel;
			break;
		case NetPieceRequirements.Raised:
			compositionFlags.m_Right |= CompositionFlags.Side.Raised;
			break;
		case NetPieceRequirements.Lowered:
			compositionFlags.m_Right |= CompositionFlags.Side.Lowered;
			break;
		case NetPieceRequirements.LowTransition:
			compositionFlags.m_Right |= CompositionFlags.Side.LowTransition;
			break;
		case NetPieceRequirements.HighTransition:
			compositionFlags.m_Right |= CompositionFlags.Side.HighTransition;
			break;
		case NetPieceRequirements.WideMedian:
			compositionFlags.m_General |= CompositionFlags.General.WideMedian;
			break;
		case NetPieceRequirements.TramTrack:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryTrack;
			break;
		case NetPieceRequirements.TramStop:
			compositionFlags.m_Right |= CompositionFlags.Side.SecondaryStop;
			break;
		case NetPieceRequirements.OppositeTramTrack:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryTrack;
			break;
		case NetPieceRequirements.OppositeTramStop:
			compositionFlags.m_Left |= CompositionFlags.Side.SecondaryStop;
			break;
		case NetPieceRequirements.MedianBreak:
			compositionFlags.m_General |= CompositionFlags.General.MedianBreak;
			break;
		case NetPieceRequirements.ShipStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.Sidewalk:
			compositionFlags.m_Right |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.Edge:
			compositionFlags.m_General |= CompositionFlags.General.Edge;
			break;
		case NetPieceRequirements.SubwayStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeSubwayStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.MiddlePlatform:
			compositionFlags.m_General |= CompositionFlags.General.MiddlePlatform;
			break;
		case NetPieceRequirements.Underground:
			sectionFlags |= NetSectionFlags.Underground;
			break;
		case NetPieceRequirements.Roundabout:
			compositionFlags.m_General |= CompositionFlags.General.Roundabout;
			break;
		case NetPieceRequirements.OppositeSidewalk:
			compositionFlags.m_Left |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.SoundBarrier:
			compositionFlags.m_Right |= CompositionFlags.Side.SoundBarrier;
			break;
		case NetPieceRequirements.Overhead:
			sectionFlags |= NetSectionFlags.Overhead;
			break;
		case NetPieceRequirements.TrafficLights:
			compositionFlags.m_General |= CompositionFlags.General.TrafficLights;
			break;
		case NetPieceRequirements.PublicTransportLane:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryLane;
			break;
		case NetPieceRequirements.OppositePublicTransportLane:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryLane;
			break;
		case NetPieceRequirements.Spillway:
			compositionFlags.m_General |= CompositionFlags.General.Spillway;
			break;
		case NetPieceRequirements.MiddleGrass:
			compositionFlags.m_General |= CompositionFlags.General.PrimaryMiddleBeautification;
			break;
		case NetPieceRequirements.MiddleTrees:
			compositionFlags.m_General |= CompositionFlags.General.SecondaryMiddleBeautification;
			break;
		case NetPieceRequirements.WideSidewalk:
			compositionFlags.m_Right |= CompositionFlags.Side.WideSidewalk;
			break;
		case NetPieceRequirements.SideGrass:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryBeautification;
			break;
		case NetPieceRequirements.SideTrees:
			compositionFlags.m_Right |= CompositionFlags.Side.SecondaryBeautification;
			break;
		case NetPieceRequirements.OppositeGrass:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryBeautification;
			break;
		case NetPieceRequirements.OppositeTrees:
			compositionFlags.m_Left |= CompositionFlags.Side.SecondaryBeautification;
			break;
		case NetPieceRequirements.Opening:
			compositionFlags.m_General |= CompositionFlags.General.Opening;
			break;
		case NetPieceRequirements.Front:
			compositionFlags.m_General |= CompositionFlags.General.Front;
			break;
		case NetPieceRequirements.Back:
			compositionFlags.m_General |= CompositionFlags.General.Back;
			break;
		case NetPieceRequirements.Flipped:
			sectionFlags |= NetSectionFlags.FlipMesh;
			break;
		case NetPieceRequirements.RemoveTrafficLights:
			compositionFlags.m_General |= CompositionFlags.General.RemoveTrafficLights;
			break;
		case NetPieceRequirements.AllWayStop:
			compositionFlags.m_General |= CompositionFlags.General.AllWayStop;
			break;
		case NetPieceRequirements.Pavement:
			compositionFlags.m_General |= CompositionFlags.General.Pavement;
			break;
		case NetPieceRequirements.Gravel:
			compositionFlags.m_General |= CompositionFlags.General.Gravel;
			break;
		case NetPieceRequirements.Tiles:
			compositionFlags.m_General |= CompositionFlags.General.Tiles;
			break;
		case NetPieceRequirements.ForbidLeftTurn:
			compositionFlags.m_Right |= CompositionFlags.Side.ForbidLeftTurn;
			break;
		case NetPieceRequirements.ForbidRightTurn:
			compositionFlags.m_Right |= CompositionFlags.Side.ForbidRightTurn;
			break;
		case NetPieceRequirements.OppositeWideSidewalk:
			compositionFlags.m_Left |= CompositionFlags.Side.WideSidewalk;
			break;
		case NetPieceRequirements.OppositeForbidLeftTurn:
			compositionFlags.m_Left |= CompositionFlags.Side.ForbidLeftTurn;
			break;
		case NetPieceRequirements.OppositeForbidRightTurn:
			compositionFlags.m_Left |= CompositionFlags.Side.ForbidRightTurn;
			break;
		case NetPieceRequirements.OppositeSoundBarrier:
			compositionFlags.m_Left |= CompositionFlags.Side.SoundBarrier;
			break;
		case NetPieceRequirements.SidePlatform:
			compositionFlags.m_Right |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.AddCrosswalk:
			compositionFlags.m_Right |= CompositionFlags.Side.AddCrosswalk;
			break;
		case NetPieceRequirements.RemoveCrosswalk:
			compositionFlags.m_Right |= CompositionFlags.Side.RemoveCrosswalk;
			break;
		case NetPieceRequirements.Lighting:
			compositionFlags.m_General |= CompositionFlags.General.Lighting;
			break;
		case NetPieceRequirements.OppositeBusStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeTaxiStand:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeRaised:
			compositionFlags.m_Left |= CompositionFlags.Side.Raised;
			break;
		case NetPieceRequirements.OppositeLowered:
			compositionFlags.m_Left |= CompositionFlags.Side.Lowered;
			break;
		case NetPieceRequirements.OppositeLowTransition:
			compositionFlags.m_Left |= CompositionFlags.Side.LowTransition;
			break;
		case NetPieceRequirements.OppositeHighTransition:
			compositionFlags.m_Left |= CompositionFlags.Side.HighTransition;
			break;
		case NetPieceRequirements.OppositeShipStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositePlatform:
			compositionFlags.m_Left |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.OppositeAddCrosswalk:
			compositionFlags.m_Left |= CompositionFlags.Side.AddCrosswalk;
			break;
		case NetPieceRequirements.OppositeRemoveCrosswalk:
			compositionFlags.m_Left |= CompositionFlags.Side.RemoveCrosswalk;
			break;
		case NetPieceRequirements.Inside:
			compositionFlags.m_General |= CompositionFlags.General.Inside;
			break;
		case NetPieceRequirements.ForbidStraight:
			compositionFlags.m_Right |= CompositionFlags.Side.ForbidStraight;
			break;
		case NetPieceRequirements.OppositeForbidStraight:
			compositionFlags.m_Left |= CompositionFlags.Side.ForbidStraight;
			break;
		case NetPieceRequirements.Hidden:
			sectionFlags |= NetSectionFlags.Hidden;
			break;
		case NetPieceRequirements.ParkingSpaces:
			compositionFlags.m_Right |= CompositionFlags.Side.ParkingSpaces;
			break;
		case NetPieceRequirements.OppositeParkingSpaces:
			compositionFlags.m_Left |= CompositionFlags.Side.ParkingSpaces;
			break;
		case NetPieceRequirements.FixedNodeSize:
			compositionFlags.m_General |= CompositionFlags.General.FixedNodeSize;
			break;
		case NetPieceRequirements.HalfLength:
			sectionFlags |= NetSectionFlags.HalfLength;
			break;
		case NetPieceRequirements.AbruptEnd:
			compositionFlags.m_Right |= CompositionFlags.Side.AbruptEnd;
			break;
		case NetPieceRequirements.OppositeAbruptEnd:
			compositionFlags.m_Left |= CompositionFlags.Side.AbruptEnd;
			break;
		case NetPieceRequirements.AttachmentTrack:
			compositionFlags.m_Right |= CompositionFlags.Side.SecondaryTrack;
			break;
		case NetPieceRequirements.EnterGate:
			compositionFlags.m_Right |= CompositionFlags.Side.Gate;
			break;
		case NetPieceRequirements.ExitGate:
			compositionFlags.m_Left |= CompositionFlags.Side.Gate;
			break;
		case NetPieceRequirements.StyleBreak:
			compositionFlags.m_General |= CompositionFlags.General.StyleBreak;
			break;
		}
	}
```

- `public static GetRequirementFlags(Game.Prefabs.NetPieceRequirements requirement, Game.Prefabs.CompositionFlags& compositionFlags, Game.Prefabs.NetSectionFlags& sectionFlags) : System.Void`  

```csharp
public static void GetRequirementFlags(NetPieceRequirements requirement, ref CompositionFlags compositionFlags, ref NetSectionFlags sectionFlags)
	{
		switch (requirement)
		{
		case NetPieceRequirements.Node:
			compositionFlags.m_General |= CompositionFlags.General.Node;
			break;
		case NetPieceRequirements.Intersection:
			compositionFlags.m_General |= CompositionFlags.General.Intersection;
			break;
		case NetPieceRequirements.DeadEnd:
			compositionFlags.m_General |= CompositionFlags.General.DeadEnd;
			break;
		case NetPieceRequirements.Crosswalk:
			compositionFlags.m_General |= CompositionFlags.General.Crosswalk;
			break;
		case NetPieceRequirements.BusStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.Median:
			sectionFlags |= NetSectionFlags.Median;
			break;
		case NetPieceRequirements.TrainStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeTrainStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.Inverted:
			sectionFlags |= NetSectionFlags.Invert;
			break;
		case NetPieceRequirements.TaxiStand:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.LevelCrossing:
			compositionFlags.m_General |= CompositionFlags.General.LevelCrossing;
			break;
		case NetPieceRequirements.Elevated:
			compositionFlags.m_General |= CompositionFlags.General.Elevated;
			break;
		case NetPieceRequirements.Tunnel:
			compositionFlags.m_General |= CompositionFlags.General.Tunnel;
			break;
		case NetPieceRequirements.Raised:
			compositionFlags.m_Right |= CompositionFlags.Side.Raised;
			break;
		case NetPieceRequirements.Lowered:
			compositionFlags.m_Right |= CompositionFlags.Side.Lowered;
			break;
		case NetPieceRequirements.LowTransition:
			compositionFlags.m_Right |= CompositionFlags.Side.LowTransition;
			break;
		case NetPieceRequirements.HighTransition:
			compositionFlags.m_Right |= CompositionFlags.Side.HighTransition;
			break;
		case NetPieceRequirements.WideMedian:
			compositionFlags.m_General |= CompositionFlags.General.WideMedian;
			break;
		case NetPieceRequirements.TramTrack:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryTrack;
			break;
		case NetPieceRequirements.TramStop:
			compositionFlags.m_Right |= CompositionFlags.Side.SecondaryStop;
			break;
		case NetPieceRequirements.OppositeTramTrack:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryTrack;
			break;
		case NetPieceRequirements.OppositeTramStop:
			compositionFlags.m_Left |= CompositionFlags.Side.SecondaryStop;
			break;
		case NetPieceRequirements.MedianBreak:
			compositionFlags.m_General |= CompositionFlags.General.MedianBreak;
			break;
		case NetPieceRequirements.ShipStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.Sidewalk:
			compositionFlags.m_Right |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.Edge:
			compositionFlags.m_General |= CompositionFlags.General.Edge;
			break;
		case NetPieceRequirements.SubwayStop:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeSubwayStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.MiddlePlatform:
			compositionFlags.m_General |= CompositionFlags.General.MiddlePlatform;
			break;
		case NetPieceRequirements.Underground:
			sectionFlags |= NetSectionFlags.Underground;
			break;
		case NetPieceRequirements.Roundabout:
			compositionFlags.m_General |= CompositionFlags.General.Roundabout;
			break;
		case NetPieceRequirements.OppositeSidewalk:
			compositionFlags.m_Left |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.SoundBarrier:
			compositionFlags.m_Right |= CompositionFlags.Side.SoundBarrier;
			break;
		case NetPieceRequirements.Overhead:
			sectionFlags |= NetSectionFlags.Overhead;
			break;
		case NetPieceRequirements.TrafficLights:
			compositionFlags.m_General |= CompositionFlags.General.TrafficLights;
			break;
		case NetPieceRequirements.PublicTransportLane:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryLane;
			break;
		case NetPieceRequirements.OppositePublicTransportLane:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryLane;
			break;
		case NetPieceRequirements.Spillway:
			compositionFlags.m_General |= CompositionFlags.General.Spillway;
			break;
		case NetPieceRequirements.MiddleGrass:
			compositionFlags.m_General |= CompositionFlags.General.PrimaryMiddleBeautification;
			break;
		case NetPieceRequirements.MiddleTrees:
			compositionFlags.m_General |= CompositionFlags.General.SecondaryMiddleBeautification;
			break;
		case NetPieceRequirements.WideSidewalk:
			compositionFlags.m_Right |= CompositionFlags.Side.WideSidewalk;
			break;
		case NetPieceRequirements.SideGrass:
			compositionFlags.m_Right |= CompositionFlags.Side.PrimaryBeautification;
			break;
		case NetPieceRequirements.SideTrees:
			compositionFlags.m_Right |= CompositionFlags.Side.SecondaryBeautification;
			break;
		case NetPieceRequirements.OppositeGrass:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryBeautification;
			break;
		case NetPieceRequirements.OppositeTrees:
			compositionFlags.m_Left |= CompositionFlags.Side.SecondaryBeautification;
			break;
		case NetPieceRequirements.Opening:
			compositionFlags.m_General |= CompositionFlags.General.Opening;
			break;
		case NetPieceRequirements.Front:
			compositionFlags.m_General |= CompositionFlags.General.Front;
			break;
		case NetPieceRequirements.Back:
			compositionFlags.m_General |= CompositionFlags.General.Back;
			break;
		case NetPieceRequirements.Flipped:
			sectionFlags |= NetSectionFlags.FlipMesh;
			break;
		case NetPieceRequirements.RemoveTrafficLights:
			compositionFlags.m_General |= CompositionFlags.General.RemoveTrafficLights;
			break;
		case NetPieceRequirements.AllWayStop:
			compositionFlags.m_General |= CompositionFlags.General.AllWayStop;
			break;
		case NetPieceRequirements.Pavement:
			compositionFlags.m_General |= CompositionFlags.General.Pavement;
			break;
		case NetPieceRequirements.Gravel:
			compositionFlags.m_General |= CompositionFlags.General.Gravel;
			break;
		case NetPieceRequirements.Tiles:
			compositionFlags.m_General |= CompositionFlags.General.Tiles;
			break;
		case NetPieceRequirements.ForbidLeftTurn:
			compositionFlags.m_Right |= CompositionFlags.Side.ForbidLeftTurn;
			break;
		case NetPieceRequirements.ForbidRightTurn:
			compositionFlags.m_Right |= CompositionFlags.Side.ForbidRightTurn;
			break;
		case NetPieceRequirements.OppositeWideSidewalk:
			compositionFlags.m_Left |= CompositionFlags.Side.WideSidewalk;
			break;
		case NetPieceRequirements.OppositeForbidLeftTurn:
			compositionFlags.m_Left |= CompositionFlags.Side.ForbidLeftTurn;
			break;
		case NetPieceRequirements.OppositeForbidRightTurn:
			compositionFlags.m_Left |= CompositionFlags.Side.ForbidRightTurn;
			break;
		case NetPieceRequirements.OppositeSoundBarrier:
			compositionFlags.m_Left |= CompositionFlags.Side.SoundBarrier;
			break;
		case NetPieceRequirements.SidePlatform:
			compositionFlags.m_Right |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.AddCrosswalk:
			compositionFlags.m_Right |= CompositionFlags.Side.AddCrosswalk;
			break;
		case NetPieceRequirements.RemoveCrosswalk:
			compositionFlags.m_Right |= CompositionFlags.Side.RemoveCrosswalk;
			break;
		case NetPieceRequirements.Lighting:
			compositionFlags.m_General |= CompositionFlags.General.Lighting;
			break;
		case NetPieceRequirements.OppositeBusStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeTaxiStand:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositeRaised:
			compositionFlags.m_Left |= CompositionFlags.Side.Raised;
			break;
		case NetPieceRequirements.OppositeLowered:
			compositionFlags.m_Left |= CompositionFlags.Side.Lowered;
			break;
		case NetPieceRequirements.OppositeLowTransition:
			compositionFlags.m_Left |= CompositionFlags.Side.LowTransition;
			break;
		case NetPieceRequirements.OppositeHighTransition:
			compositionFlags.m_Left |= CompositionFlags.Side.HighTransition;
			break;
		case NetPieceRequirements.OppositeShipStop:
			compositionFlags.m_Left |= CompositionFlags.Side.PrimaryStop;
			break;
		case NetPieceRequirements.OppositePlatform:
			compositionFlags.m_Left |= CompositionFlags.Side.Sidewalk;
			break;
		case NetPieceRequirements.OppositeAddCrosswalk:
			compositionFlags.m_Left |= CompositionFlags.Side.AddCrosswalk;
			break;
		case NetPieceRequirements.OppositeRemoveCrosswalk:
			compositionFlags.m_Left |= CompositionFlags.Side.RemoveCrosswalk;
			break;
		case NetPieceRequirements.Inside:
			compositionFlags.m_General |= CompositionFlags.General.Inside;
			break;
		case NetPieceRequirements.ForbidStraight:
			compositionFlags.m_Right |= CompositionFlags.Side.ForbidStraight;
			break;
		case NetPieceRequirements.OppositeForbidStraight:
			compositionFlags.m_Left |= CompositionFlags.Side.ForbidStraight;
			break;
		case NetPieceRequirements.Hidden:
			sectionFlags |= NetSectionFlags.Hidden;
			break;
		case NetPieceRequirements.ParkingSpaces:
			compositionFlags.m_Right |= CompositionFlags.Side.ParkingSpaces;
			break;
		case NetPieceRequirements.OppositeParkingSpaces:
			compositionFlags.m_Left |= CompositionFlags.Side.ParkingSpaces;
			break;
		case NetPieceRequirements.FixedNodeSize:
			compositionFlags.m_General |= CompositionFlags.General.FixedNodeSize;
			break;
		case NetPieceRequirements.HalfLength:
			sectionFlags |= NetSectionFlags.HalfLength;
			break;
		case NetPieceRequirements.AbruptEnd:
			compositionFlags.m_Right |= CompositionFlags.Side.AbruptEnd;
			break;
		case NetPieceRequirements.OppositeAbruptEnd:
			compositionFlags.m_Left |= CompositionFlags.Side.AbruptEnd;
			break;
		case NetPieceRequirements.AttachmentTrack:
			compositionFlags.m_Right |= CompositionFlags.Side.SecondaryTrack;
			break;
		case NetPieceRequirements.EnterGate:
			compositionFlags.m_Right |= CompositionFlags.Side.Gate;
			break;
		case NetPieceRequirements.ExitGate:
			compositionFlags.m_Left |= CompositionFlags.Side.Gate;
			break;
		case NetPieceRequirements.StyleBreak:
			compositionFlags.m_General |= CompositionFlags.General.StyleBreak;
			break;
		}
	}
```

- `private static HasRoad(Unity.Entities.Entity piece, Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> netLaneData, Unity.Entities.BufferLookup<Game.Prefabs.NetPieceLane> netPieceLanes) : System.Boolean`  

```csharp
private static bool HasRoad(Entity piece, ComponentLookup<NetLaneData> netLaneData, BufferLookup<NetPieceLane> netPieceLanes)
	{
		if (!netPieceLanes.HasBuffer(piece))
		{
			return false;
		}
		DynamicBuffer<NetPieceLane> dynamicBuffer = netPieceLanes[piece];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			if ((netLaneData[dynamicBuffer[i].m_Lane].m_Flags & LaneFlags.Road) != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `public static InvertCompositionFlags(Game.Prefabs.CompositionFlags flags) : Game.Prefabs.CompositionFlags`  

```csharp
public static CompositionFlags InvertCompositionFlags(CompositionFlags flags)
	{
		return new CompositionFlags(flags.m_General, flags.m_Right, flags.m_Left);
	}
```

- `public static InvertSectionFlags(Game.Prefabs.NetSectionFlags flags) : Game.Prefabs.NetSectionFlags`  

```csharp
public static NetSectionFlags InvertSectionFlags(NetSectionFlags flags)
	{
		return flags;
	}
```

- `public static TestEdgeFlags(Game.Prefabs.NetGeometryEdgeState edgeState, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static bool TestEdgeFlags(ElectricityConnectionData electricityConnectionData, CompositionFlags compositionFlags)
	{
		if (((electricityConnectionData.m_CompositionAll | electricityConnectionData.m_CompositionNone) & compositionFlags) != electricityConnectionData.m_CompositionAll)
		{
			return false;
		}
		if (electricityConnectionData.m_CompositionAny == default(CompositionFlags))
		{
			return true;
		}
		return (electricityConnectionData.m_CompositionAny & compositionFlags) != default(CompositionFlags);
	}
```

- `public static TestEdgeFlags(Game.Prefabs.NetGeometryNodeState nodeState, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static bool TestEdgeFlags(ElectricityConnectionData electricityConnectionData, CompositionFlags compositionFlags)
	{
		if (((electricityConnectionData.m_CompositionAll | electricityConnectionData.m_CompositionNone) & compositionFlags) != electricityConnectionData.m_CompositionAll)
		{
			return false;
		}
		if (electricityConnectionData.m_CompositionAny == default(CompositionFlags))
		{
			return true;
		}
		return (electricityConnectionData.m_CompositionAny & compositionFlags) != default(CompositionFlags);
	}
```

- `public static TestEdgeFlags(Game.Prefabs.ElectricityConnectionData electricityConnectionData, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static bool TestEdgeFlags(ElectricityConnectionData electricityConnectionData, CompositionFlags compositionFlags)
	{
		if (((electricityConnectionData.m_CompositionAll | electricityConnectionData.m_CompositionNone) & compositionFlags) != electricityConnectionData.m_CompositionAll)
		{
			return false;
		}
		if (electricityConnectionData.m_CompositionAny == default(CompositionFlags))
		{
			return true;
		}
		return (electricityConnectionData.m_CompositionAny & compositionFlags) != default(CompositionFlags);
	}
```

- `public static TestEdgeMatch(Game.Prefabs.NetGeometryNodeState nodeState, Unity.Mathematics.bool2 match) : System.Boolean`  

```csharp
public static bool TestEdgeMatch(NetGeometryNodeState nodeState, bool2 match)
	{
		return nodeState.m_MatchType switch
		{
			NetEdgeMatchType.Both => math.all(match), 
			NetEdgeMatchType.Any => math.any(match), 
			NetEdgeMatchType.Exclusive => match.x != match.y, 
			_ => false, 
		};
	}
```

- `public static TestLaneFlags(Game.Prefabs.AuxiliaryNetLane lane, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static bool TestLaneFlags(AuxiliaryNetLane lane, CompositionFlags compositionFlags)
	{
		if (((lane.m_CompositionAll | lane.m_CompositionNone) & compositionFlags) != lane.m_CompositionAll)
		{
			return false;
		}
		if (lane.m_CompositionAny == default(CompositionFlags))
		{
			return true;
		}
		return (lane.m_CompositionAny & compositionFlags) != default(CompositionFlags);
	}
```

- `public static TestObjectFlags(Game.Prefabs.NetPieceObject _object, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static bool TestObjectFlags(NetPieceObject _object, CompositionFlags compositionFlags, NetSectionFlags sectionFlags)
	{
		if ((sectionFlags & NetSectionFlags.Median) == 0)
		{
			compositionFlags.m_General &= ~CompositionFlags.General.MedianBreak;
		}
		if (((_object.m_CompositionAll | _object.m_CompositionNone) & compositionFlags) != _object.m_CompositionAll)
		{
			return false;
		}
		if (((_object.m_SectionAll | _object.m_SectionNone) & sectionFlags) != _object.m_SectionAll)
		{
			return false;
		}
		if (_object.m_CompositionAny == default(CompositionFlags) && _object.m_SectionAny == (NetSectionFlags)0)
		{
			return true;
		}
		if (!((_object.m_CompositionAny & compositionFlags) != default(CompositionFlags)))
		{
			return (_object.m_SectionAny & sectionFlags) != 0;
		}
		return true;
	}
```

- `public static TestPieceFlags(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static bool TestPieceFlags(NetSectionPiece piece, CompositionFlags compositionFlags, NetSectionFlags sectionFlags)
	{
		if ((sectionFlags & NetSectionFlags.Median) == 0)
		{
			compositionFlags.m_General &= ~CompositionFlags.General.MedianBreak;
		}
		if (((piece.m_CompositionAll | piece.m_CompositionNone) & compositionFlags) != piece.m_CompositionAll)
		{
			return false;
		}
		if (((piece.m_SectionAll | piece.m_SectionNone) & sectionFlags) != piece.m_SectionAll)
		{
			return false;
		}
		if (piece.m_CompositionAny == default(CompositionFlags) && piece.m_SectionAny == (NetSectionFlags)0)
		{
			return true;
		}
		if (!((piece.m_CompositionAny & compositionFlags) != default(CompositionFlags)))
		{
			return (piece.m_SectionAny & sectionFlags) != 0;
		}
		return true;
	}
```

- `public static TestPieceFlags2(Game.Prefabs.NetSectionPiece piece, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static bool TestPieceFlags2(NetSectionPiece piece, CompositionFlags compositionFlags, NetSectionFlags sectionFlags)
	{
		if ((compositionFlags.m_General & CompositionFlags.General.Roundabout) != 0 && (piece.m_Flags & NetPieceFlags.Side) != 0)
		{
			CompositionFlags compositionFlags2 = compositionFlags;
			if ((compositionFlags2.m_General & CompositionFlags.General.Elevated) != 0)
			{
				if ((compositionFlags2.m_Left & CompositionFlags.Side.HighTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Elevated;
					compositionFlags2.m_Left &= ~CompositionFlags.Side.HighTransition;
				}
				else if ((compositionFlags2.m_Left & CompositionFlags.Side.LowTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Elevated;
					compositionFlags2.m_Left &= ~CompositionFlags.Side.LowTransition;
					compositionFlags2.m_Left |= CompositionFlags.Side.Raised;
				}
				if ((compositionFlags2.m_Right & CompositionFlags.Side.HighTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Elevated;
					compositionFlags2.m_Right &= ~CompositionFlags.Side.HighTransition;
				}
				else if ((compositionFlags2.m_Right & CompositionFlags.Side.LowTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Elevated;
					compositionFlags2.m_Right &= ~CompositionFlags.Side.LowTransition;
					compositionFlags2.m_Right |= CompositionFlags.Side.Raised;
				}
			}
			else if ((compositionFlags2.m_General & CompositionFlags.General.Tunnel) != 0)
			{
				if ((compositionFlags2.m_Left & CompositionFlags.Side.HighTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Tunnel;
					compositionFlags2.m_Left &= ~CompositionFlags.Side.HighTransition;
				}
				else if ((compositionFlags2.m_Left & CompositionFlags.Side.LowTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Tunnel;
					compositionFlags2.m_Left &= ~CompositionFlags.Side.LowTransition;
					compositionFlags2.m_Left |= CompositionFlags.Side.Lowered;
				}
				if ((compositionFlags2.m_Right & CompositionFlags.Side.HighTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Tunnel;
					compositionFlags2.m_Right &= ~CompositionFlags.Side.HighTransition;
				}
				else if ((compositionFlags2.m_Right & CompositionFlags.Side.LowTransition) != 0)
				{
					compositionFlags2.m_General &= ~CompositionFlags.General.Tunnel;
					compositionFlags2.m_Right &= ~CompositionFlags.Side.LowTransition;
					compositionFlags2.m_Right |= CompositionFlags.Side.Lowered;
				}
			}
			else
			{
				if ((compositionFlags2.m_Left & CompositionFlags.Side.LowTransition) != 0)
				{
					if ((compositionFlags2.m_Left & CompositionFlags.Side.Raised) != 0)
					{
						compositionFlags2.m_Left &= ~(CompositionFlags.Side.Raised | CompositionFlags.Side.LowTransition);
					}
					else if ((compositionFlags2.m_Left & CompositionFlags.Side.Lowered) != 0)
					{
						compositionFlags2.m_Left &= ~(CompositionFlags.Side.Lowered | CompositionFlags.Side.LowTransition);
					}
					else if ((compositionFlags2.m_Left & CompositionFlags.Side.SoundBarrier) != 0)
					{
						compositionFlags2.m_Left &= ~(CompositionFlags.Side.LowTransition | CompositionFlags.Side.SoundBarrier);
					}
				}
				if ((compositionFlags2.m_Right & CompositionFlags.Side.LowTransition) != 0)
				{
					if ((compositionFlags2.m_Right & CompositionFlags.Side.Raised) != 0)
					{
						compositionFlags2.m_Right &= ~(CompositionFlags.Side.Raised | CompositionFlags.Side.LowTransition);
					}
					else if ((compositionFlags2.m_Right & CompositionFlags.Side.Lowered) != 0)
					{
						compositionFlags2.m_Right &= ~(CompositionFlags.Side.Lowered | CompositionFlags.Side.LowTransition);
					}
					else if ((compositionFlags2.m_Right & CompositionFlags.Side.SoundBarrier) != 0)
					{
						compositionFlags2.m_Right &= ~(CompositionFlags.Side.LowTransition | CompositionFlags.Side.SoundBarrier);
					}
				}
			}
			if (compositionFlags != compositionFlags2)
			{
				return TestPieceFlags(piece, compositionFlags2, sectionFlags);
			}
		}
		return false;
	}
```

- `public static TestSectionFlags(Game.Prefabs.NetGeometrySection section, Game.Prefabs.CompositionFlags compositionFlags) : System.Boolean`  

```csharp
public static bool TestSectionFlags(NetGeometrySection section, CompositionFlags compositionFlags)
	{
		if (((section.m_CompositionAll | section.m_CompositionNone) & compositionFlags) != section.m_CompositionAll)
		{
			return false;
		}
		if (section.m_CompositionAny == default(CompositionFlags))
		{
			return true;
		}
		return (section.m_CompositionAny & compositionFlags) != default(CompositionFlags);
	}
```

- `public static TestSubSectionFlags(Game.Prefabs.NetSubSection subSection, Game.Prefabs.CompositionFlags compositionFlags, Game.Prefabs.NetSectionFlags sectionFlags) : System.Boolean`  

```csharp
public static bool TestSubSectionFlags(NetSubSection subSection, CompositionFlags compositionFlags, NetSectionFlags sectionFlags)
	{
		if ((sectionFlags & NetSectionFlags.Median) == 0)
		{
			compositionFlags.m_General &= ~CompositionFlags.General.MedianBreak;
		}
		if (((subSection.m_CompositionAll | subSection.m_CompositionNone) & compositionFlags) != subSection.m_CompositionAll)
		{
			return false;
		}
		if (((subSection.m_SectionAll | subSection.m_SectionNone) & sectionFlags) != subSection.m_SectionAll)
		{
			return false;
		}
		if (subSection.m_CompositionAny == default(CompositionFlags) && subSection.m_SectionAny == (NetSectionFlags)0)
		{
			return true;
		}
		if (!((subSection.m_CompositionAny & compositionFlags) != default(CompositionFlags)))
		{
			return (subSection.m_SectionAny & sectionFlags) != 0;
		}
		return true;
	}
```


## Nested types

- `Game.Prefabs.NetCompositionHelpers+TempLaneData`  
- `Game.Prefabs.NetCompositionHelpers+TempLaneGroup`  

