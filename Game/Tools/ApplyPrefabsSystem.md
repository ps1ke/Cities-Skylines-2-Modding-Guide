# Game.Tools.ApplyPrefabsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyPrefabsSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_SaveInstanceQuery;

    public ApplyPrefabsSystem();

    public static T AddComponent<T>(Game.Prefabs.PrefabBase asset);
    private static System.Void CheckCachedValue(Unity.Mathematics.float3& value, Unity.Mathematics.float3 cached);
    private static System.Void CheckCachedValue(Unity.Mathematics.quaternion& value, Unity.Mathematics.quaternion cached);
    private Game.Prefabs.NetPieceRequirements[] CreateRequirementArray(Game.Prefabs.NetPieceRequirements[] requirementMap, Game.Prefabs.CompositionFlags flags);
    private Game.Prefabs.NetPieceRequirements[] CreateRequirementMap();
    private System.Int32 GetNodeIndex(Unity.Entities.Entity node, System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> dictionary);
    private System.Int32 GetParentMesh(Unity.Entities.Entity node);
    private System.Boolean HasEdgeStartOrEnd(Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.Entity node, Unity.Entities.Entity instanceEntity);
    private System.Collections.Generic.List<Game.Prefabs.ObjectSubAreaInfo> ListObjectSubAreas(Unity.Entities.Entity instanceEntity, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void ListObjectSubNets(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubNetInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subNetList, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubLaneInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLaneList, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void ListObjectSubObjects(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubObjectInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subObjectList, System.Collections.Generic.List`1[[Game.Prefabs.EffectSource+EffectSettings, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subEffectList, System.Collections.Generic.List`1[[Game.Prefabs.ActivityLocation+LocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subActivityList, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public static System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase asset);
    public static System.Void RemoveComponent(Game.Prefabs.PrefabBase asset, System.Type componentType);
    private System.Void UpdateObjectSubAreas(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void UpdateObjectSubNets(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
    private System.Void UpdateObjectSubObjects(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost);
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_SaveInstanceQuery`  

```csharp
private Unity.Entities.EntityQuery m_SaveInstanceQuery;
```


## Constructors

- `public ApplyPrefabsSystem()`  

```csharp
[Preserve]
	public ApplyPrefabsSystem()
	{
	}
```


## Methods

- `public static AddComponent<T>(Game.Prefabs.PrefabBase asset) : T`  

```csharp
public static T AddComponent<T>(Game.Prefabs.PrefabBase asset);
```

- `private static CheckCachedValue(Unity.Mathematics.float3& value, Unity.Mathematics.float3 cached) : System.Void`  

```csharp
private static void CheckCachedValue(ref quaternion value, quaternion cached)
	{
		if (MathUtils.RotationAngle(value, cached) < MathF.PI / 180f)
		{
			value = cached;
		}
	}
```

- `private static CheckCachedValue(Unity.Mathematics.quaternion& value, Unity.Mathematics.quaternion cached) : System.Void`  

```csharp
private static void CheckCachedValue(ref quaternion value, quaternion cached)
	{
		if (MathUtils.RotationAngle(value, cached) < MathF.PI / 180f)
		{
			value = cached;
		}
	}
```

- `private CreateRequirementArray(Game.Prefabs.NetPieceRequirements[] requirementMap, Game.Prefabs.CompositionFlags flags) : Game.Prefabs.NetPieceRequirements[]`  

```csharp
private NetPieceRequirements[] CreateRequirementArray(NetPieceRequirements[] requirementMap, CompositionFlags flags)
	{
		List<NetPieceRequirements> list = new List<NetPieceRequirements>(10);
		if (flags.m_Left != 0)
		{
			for (int i = 0; i < 32; i++)
			{
				if (((uint)flags.m_Left & (uint)(1 << i)) != 0)
				{
					list.Add(requirementMap[i]);
				}
			}
		}
		if (flags.m_General != 0)
		{
			for (int j = 0; j < 32; j++)
			{
				if (((uint)flags.m_General & (uint)(1 << j)) != 0)
				{
					list.Add(requirementMap[j + 32]);
				}
			}
		}
		if (flags.m_Right != 0)
		{
			for (int k = 0; k < 32; k++)
			{
				if (((uint)flags.m_Right & (uint)(1 << k)) != 0)
				{
					list.Add(requirementMap[k + 64]);
				}
			}
		}
		if (list.Count != 0)
		{
			return list.ToArray();
		}
		return null;
	}
```

- `private CreateRequirementMap() : Game.Prefabs.NetPieceRequirements[]`  

```csharp
private NetPieceRequirements[] CreateRequirementMap()
	{
		NetPieceRequirements[] array = new NetPieceRequirements[96];
		foreach (NetPieceRequirements value in Enum.GetValues(typeof(NetPieceRequirements)))
		{
			CompositionFlags compositionFlags = default(CompositionFlags);
			NetSectionFlags sectionFlags = (NetSectionFlags)0;
			NetCompositionHelpers.GetRequirementFlags(value, ref compositionFlags, ref sectionFlags);
			if (compositionFlags.m_Left != 0)
			{
				for (int i = 0; i < 32; i++)
				{
					if (((uint)compositionFlags.m_Left & (uint)(1 << i)) != 0)
					{
						array[i] = value;
					}
				}
			}
			if (compositionFlags.m_General != 0)
			{
				for (int j = 0; j < 32; j++)
				{
					if (((uint)compositionFlags.m_General & (uint)(1 << j)) != 0)
					{
						array[j + 32] = value;
					}
				}
			}
			if (compositionFlags.m_Right == (CompositionFlags.Side)0u)
			{
				continue;
			}
			for (int k = 0; k < 32; k++)
			{
				if (((uint)compositionFlags.m_Right & (uint)(1 << k)) != 0)
				{
					array[k + 64] = value;
				}
			}
		}
		return array;
	}
```

- `private GetNodeIndex(Unity.Entities.Entity node, System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.Int32> dictionary) : System.Int32`  

```csharp
private int GetNodeIndex(Entity node, Dictionary<Entity, int> dictionary)
	{
		if (!dictionary.TryGetValue(node, out var value))
		{
			value = dictionary.Count;
			dictionary.Add(node, value);
		}
		return value;
	}
```

- `private GetParentMesh(Unity.Entities.Entity node) : System.Int32`  

```csharp
private int GetParentMesh(Entity node)
	{
		if (base.EntityManager.TryGetComponent<LocalTransformCache>(node, out var component))
		{
			return component.m_ParentMesh;
		}
		return -1;
	}
```

- `private HasEdgeStartOrEnd(Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.Entity node, Unity.Entities.Entity instanceEntity) : System.Boolean`  

```csharp
private bool HasEdgeStartOrEnd(DynamicBuffer<ConnectedEdge> connectedEdges, Entity node, Entity instanceEntity)
	{
		for (int i = 0; i < connectedEdges.Length; i++)
		{
			Entity edge = connectedEdges[i].m_Edge;
			if (base.EntityManager.TryGetComponent<Edge>(edge, out var component) && (component.m_Start == node || component.m_End == node) && base.EntityManager.TryGetComponent<Owner>(edge, out var component2) && component2.m_Owner == instanceEntity)
			{
				return true;
			}
		}
		return false;
	}
```

- `private ListObjectSubAreas(Unity.Entities.Entity instanceEntity, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Collections.Generic.List<Game.Prefabs.ObjectSubAreaInfo>`  

```csharp
private List<ObjectSubAreaInfo> ListObjectSubAreas(Entity instanceEntity, ref uint constructionCost, ref uint upKeepCost)
	{
		if (base.EntityManager.HasComponent<Game.Areas.SubArea>(instanceEntity))
		{
			DynamicBuffer<Game.Areas.SubArea> buffer = base.EntityManager.GetBuffer<Game.Areas.SubArea>(instanceEntity, isReadOnly: true);
			if (buffer.Length != 0)
			{
				Game.Objects.Transform inverseParentTransform = default(Game.Objects.Transform);
				bool flag = false;
				if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(instanceEntity, out var component))
				{
					inverseParentTransform.m_Position = -component.m_Position;
					inverseParentTransform.m_Rotation = math.inverse(component.m_Rotation);
					flag = true;
				}
				List<ObjectSubAreaInfo> list = new List<ObjectSubAreaInfo>(buffer.Length);
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity area = buffer[i].m_Area;
					if (!base.EntityManager.TryGetComponent<Owner>(area, out var component2) || base.EntityManager.HasComponent<Secondary>(area) || !(component2.m_Owner == instanceEntity))
					{
						continue;
					}
					ObjectSubAreaInfo objectSubAreaInfo = new ObjectSubAreaInfo();
					PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(area);
					objectSubAreaInfo.m_AreaPrefab = m_PrefabSystem.GetPrefab<AreaPrefab>(componentData);
					if (base.EntityManager.TryGetBuffer(area, isReadOnly: true, out DynamicBuffer<Game.Areas.Node> buffer2))
					{
						DynamicBuffer<LocalNodeCache> dynamicBuffer = default(DynamicBuffer<LocalNodeCache>);
						if (base.EntityManager.HasComponent<LocalNodeCache>(area))
						{
							dynamicBuffer = base.EntityManager.GetBuffer<LocalNodeCache>(area, isReadOnly: true);
						}
						objectSubAreaInfo.m_NodePositions = new float3[buffer2.Length];
						objectSubAreaInfo.m_ParentMeshes = new int[buffer2.Length];
						bool flag2 = false;
						for (int j = 0; j < buffer2.Length; j++)
						{
							if (flag)
							{
								objectSubAreaInfo.m_NodePositions[j] = ObjectUtils.WorldToLocal(inverseParentTransform, buffer2[j].m_Position);
							}
							else
							{
								objectSubAreaInfo.m_NodePositions[j] = buffer2[j].m_Position;
							}
							if (dynamicBuffer.IsCreated)
							{
								CheckCachedValue(ref objectSubAreaInfo.m_NodePositions[j], dynamicBuffer[j].m_Position);
								objectSubAreaInfo.m_ParentMeshes[j] = dynamicBuffer[j].m_ParentMesh;
								flag2 |= dynamicBuffer[j].m_ParentMesh >= 0;
							}
							else
							{
								objectSubAreaInfo.m_ParentMeshes[j] = -1;
							}
						}
						if (!flag2)
						{
							objectSubAreaInfo.m_ParentMeshes = null;
						}
					}
					list.Add(objectSubAreaInfo);
				}
				return list;
			}
		}
		return null;
	}
```

- `private ListObjectSubNets(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubNetInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subNetList, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubLaneInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLaneList, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private void ListObjectSubNets(Entity instanceEntity, out List<ObjectSubNetInfo> subNetList, out List<ObjectSubLaneInfo> subLaneList, ref uint constructionCost, ref uint upKeepCost)
	{
		if (base.EntityManager.HasComponent<Game.Net.SubNet>(instanceEntity))
		{
			DynamicBuffer<Game.Net.SubNet> buffer = base.EntityManager.GetBuffer<Game.Net.SubNet>(instanceEntity, isReadOnly: true);
			if (buffer.Length != 0)
			{
				Game.Objects.Transform transform = default(Game.Objects.Transform);
				bool flag = false;
				if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(instanceEntity, out var component))
				{
					transform.m_Position = -component.m_Position;
					transform.m_Rotation = math.inverse(component.m_Rotation);
					flag = true;
				}
				subNetList = new List<ObjectSubNetInfo>(buffer.Length);
				subLaneList = new List<ObjectSubLaneInfo>(buffer.Length);
				Dictionary<Entity, int> dictionary = new Dictionary<Entity, int>(buffer.Length * 2);
				Dictionary<Entity, int> dictionary2 = new Dictionary<Entity, int>(buffer.Length * 2);
				NetPieceRequirements[] array = null;
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity subNet = buffer[i].m_SubNet;
					if (!base.EntityManager.TryGetComponent<Owner>(subNet, out var component2) || !(component2.m_Owner == instanceEntity))
					{
						continue;
					}
					NetPieceRequirements[] array2 = null;
					CompositionFlags compositionFlags = default(CompositionFlags);
					if (base.EntityManager.HasComponent<Edge>(subNet) && base.EntityManager.TryGetComponent<Composition>(subNet, out var component3) && base.EntityManager.TryGetComponent<NetCompositionData>(component3.m_Edge, out var component4))
					{
						compositionFlags.m_General |= component4.m_Flags.m_General & CompositionFlags.General.Elevated;
					}
					if (base.EntityManager.TryGetComponent<Upgraded>(subNet, out var component5) || compositionFlags != default(CompositionFlags))
					{
						if (array == null)
						{
							array = CreateRequirementMap();
						}
						array2 = CreateRequirementArray(array, component5.m_Flags | compositionFlags);
					}
					Game.Net.Node component14;
					DynamicBuffer<ConnectedEdge> buffer2;
					if (base.EntityManager.TryGetComponent<Edge>(subNet, out var component6))
					{
						Bezier4x3 bezierCurve = default(Bezier4x3);
						if (base.EntityManager.TryGetComponent<Curve>(subNet, out var component7))
						{
							if (flag)
							{
								bezierCurve.a = math.mul(transform.m_Rotation, component7.m_Bezier.a + transform.m_Position);
								bezierCurve.b = math.mul(transform.m_Rotation, component7.m_Bezier.b + transform.m_Position);
								bezierCurve.c = math.mul(transform.m_Rotation, component7.m_Bezier.c + transform.m_Position);
								bezierCurve.d = math.mul(transform.m_Rotation, component7.m_Bezier.d + transform.m_Position);
							}
							else
							{
								bezierCurve = component7.m_Bezier;
							}
							if (base.EntityManager.TryGetComponent<LocalCurveCache>(subNet, out var component8))
							{
								CheckCachedValue(ref bezierCurve.a, component8.m_Curve.a);
								CheckCachedValue(ref bezierCurve.b, component8.m_Curve.b);
								CheckCachedValue(ref bezierCurve.c, component8.m_Curve.c);
								CheckCachedValue(ref bezierCurve.d, component8.m_Curve.d);
							}
							if (base.EntityManager.TryGetComponent<Composition>(subNet, out var component9) && base.EntityManager.TryGetComponent<PlaceableNetComposition>(component9.m_Edge, out var component10))
							{
								base.EntityManager.TryGetComponent<Game.Net.Elevation>(component6.m_Start, out var component11);
								base.EntityManager.TryGetComponent<Game.Net.Elevation>(component6.m_End, out var component12);
								constructionCost += (uint)NetUtils.GetConstructionCost(component7, component11, component12, component10);
								upKeepCost += (uint)NetUtils.GetUpkeepCost(component7, component10);
							}
						}
						if (base.EntityManager.TryGetComponent<EditorContainer>(subNet, out var component13))
						{
							subLaneList.Add(new ObjectSubLaneInfo
							{
								m_LanePrefab = m_PrefabSystem.GetPrefab<NetLanePrefab>(component13.m_Prefab),
								m_BezierCurve = bezierCurve,
								m_NodeIndex = new int2(GetNodeIndex(component6.m_Start, dictionary2), GetNodeIndex(component6.m_End, dictionary2)),
								m_ParentMesh = new int2(GetParentMesh(component6.m_Start), GetParentMesh(component6.m_End))
							});
						}
						else
						{
							subNetList.Add(new ObjectSubNetInfo
							{
								m_NetPrefab = m_PrefabSystem.GetPrefab<NetPrefab>(base.EntityManager.GetComponentData<PrefabRef>(subNet)),
								m_BezierCurve = bezierCurve,
								m_NodeIndex = new int2(GetNodeIndex(component6.m_Start, dictionary), GetNodeIndex(component6.m_End, dictionary)),
								m_ParentMesh = new int2(GetParentMesh(component6.m_Start), GetParentMesh(component6.m_End)),
								m_Upgrades = array2
							});
						}
					}
					else if (base.EntityManager.TryGetComponent<Game.Net.Node>(subNet, out component14) && (array2 != null || !base.EntityManager.TryGetBuffer(subNet, isReadOnly: true, out buffer2) || !HasEdgeStartOrEnd(buffer2, subNet, instanceEntity)))
					{
						Bezier4x3 bezierCurve2 = default(Bezier4x3);
						if (flag)
						{
							bezierCurve2.a = math.mul(transform.m_Rotation, component14.m_Position + transform.m_Position);
						}
						else
						{
							bezierCurve2.a = component14.m_Position;
						}
						if (base.EntityManager.TryGetComponent<LocalTransformCache>(subNet, out var component15))
						{
							CheckCachedValue(ref bezierCurve2.a, component15.m_Position);
						}
						bezierCurve2.b = bezierCurve2.a;
						bezierCurve2.c = bezierCurve2.a;
						bezierCurve2.d = bezierCurve2.a;
						if (base.EntityManager.TryGetComponent<EditorContainer>(subNet, out var component16))
						{
							subLaneList.Add(new ObjectSubLaneInfo
							{
								m_LanePrefab = m_PrefabSystem.GetPrefab<NetLanePrefab>(component16.m_Prefab),
								m_BezierCurve = bezierCurve2,
								m_NodeIndex = new int2(GetNodeIndex(subNet, dictionary2)),
								m_ParentMesh = new int2(GetParentMesh(subNet))
							});
						}
						else
						{
							subNetList.Add(new ObjectSubNetInfo
							{
								m_NetPrefab = m_PrefabSystem.GetPrefab<NetPrefab>(base.EntityManager.GetComponentData<PrefabRef>(subNet)),
								m_BezierCurve = bezierCurve2,
								m_NodeIndex = new int2(GetNodeIndex(subNet, dictionary)),
								m_ParentMesh = new int2(GetParentMesh(subNet)),
								m_Upgrades = array2
							});
						}
					}
				}
				return;
			}
		}
		subNetList = null;
		subLaneList = null;
	}
```

- `private ListObjectSubObjects(Unity.Entities.Entity instanceEntity, System.Collections.Generic.List`1[[Game.Prefabs.ObjectSubObjectInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subObjectList, System.Collections.Generic.List`1[[Game.Prefabs.EffectSource+EffectSettings, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subEffectList, System.Collections.Generic.List`1[[Game.Prefabs.ActivityLocation+LocationInfo, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subActivityList, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private void ListObjectSubObjects(Entity instanceEntity, out List<ObjectSubObjectInfo> subObjectList, out List<EffectSource.EffectSettings> subEffectList, out List<Game.Prefabs.ActivityLocation.LocationInfo> subActivityList, ref uint constructionCost, ref uint upKeepCost)
	{
		if (base.EntityManager.HasComponent<Game.Objects.SubObject>(instanceEntity))
		{
			DynamicBuffer<Game.Objects.SubObject> buffer = base.EntityManager.GetBuffer<Game.Objects.SubObject>(instanceEntity, isReadOnly: true);
			if (buffer.Length != 0)
			{
				Game.Objects.Transform inverseParentTransform = default(Game.Objects.Transform);
				bool flag = false;
				if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(instanceEntity, out var component))
				{
					inverseParentTransform.m_Position = -component.m_Position;
					inverseParentTransform.m_Rotation = math.inverse(component.m_Rotation);
					flag = true;
				}
				subObjectList = new List<ObjectSubObjectInfo>(buffer.Length);
				subEffectList = new List<EffectSource.EffectSettings>(buffer.Length);
				subActivityList = new List<Game.Prefabs.ActivityLocation.LocationInfo>(buffer.Length);
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity subObject = buffer[i].m_SubObject;
					if (!base.EntityManager.TryGetComponent<Owner>(subObject, out var component2) || base.EntityManager.HasComponent<Secondary>(subObject) || base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(subObject) || !(component2.m_Owner == instanceEntity))
					{
						continue;
					}
					int num = 0;
					int groupIndex = 0;
					int probability = 0;
					float3 value;
					quaternion value2;
					if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(subObject, out var component3))
					{
						if (flag)
						{
							Game.Objects.Transform transform = ObjectUtils.WorldToLocal(inverseParentTransform, component3);
							value = transform.m_Position;
							value2 = transform.m_Rotation;
						}
						else
						{
							value = component3.m_Position;
							value2 = component3.m_Rotation;
						}
						if (!base.EntityManager.TryGetComponent<LocalTransformCache>(subObject, out var component4))
						{
							num = ((!base.EntityManager.TryGetComponent<Game.Objects.Elevation>(subObject, out var component5)) ? (-1) : ObjectUtils.GetSubParentMesh(component5.m_Flags));
						}
						else
						{
							CheckCachedValue(ref value, component4.m_Position);
							CheckCachedValue(ref value2, component4.m_Rotation);
							num = component4.m_ParentMesh;
							groupIndex = component4.m_GroupIndex;
							probability = component4.m_Probability;
							if (base.EntityManager.TryGetComponent<EditorContainer>(subObject, out var component6))
							{
								if (base.EntityManager.HasComponent<EffectData>(component6.m_Prefab))
								{
									component4.m_PrefabSubIndex = subEffectList.Count;
								}
								else if (base.EntityManager.HasComponent<ActivityLocationData>(component6.m_Prefab))
								{
									component4.m_PrefabSubIndex = subActivityList.Count;
								}
							}
							else
							{
								component4.m_PrefabSubIndex = subObjectList.Count;
							}
							base.EntityManager.SetComponentData(subObject, component4);
						}
					}
					else
					{
						value = float3.zero;
						value2 = quaternion.identity;
						num = -1;
					}
					if (base.EntityManager.TryGetComponent<EditorContainer>(subObject, out var component7))
					{
						if (base.EntityManager.HasComponent<EffectData>(component7.m_Prefab))
						{
							subEffectList.Add(new EffectSource.EffectSettings
							{
								m_Effect = m_PrefabSystem.GetPrefab<EffectPrefab>(component7.m_Prefab),
								m_PositionOffset = value,
								m_Rotation = value2,
								m_Scale = component7.m_Scale,
								m_Intensity = component7.m_Intensity,
								m_ParentMesh = num,
								m_AnimationIndex = component7.m_GroupIndex
							});
						}
						else if (base.EntityManager.HasComponent<ActivityLocationData>(component7.m_Prefab))
						{
							subActivityList.Add(new Game.Prefabs.ActivityLocation.LocationInfo
							{
								m_Activity = m_PrefabSystem.GetPrefab<ActivityLocationPrefab>(component7.m_Prefab),
								m_Position = value,
								m_Rotation = value2
							});
						}
					}
					else
					{
						ObjectSubObjectInfo objectSubObjectInfo = new ObjectSubObjectInfo();
						PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(subObject);
						objectSubObjectInfo.m_Object = m_PrefabSystem.GetPrefab<ObjectPrefab>(componentData);
						if (base.EntityManager.TryGetComponent<PlaceableObjectData>(componentData.m_Prefab, out var component8))
						{
							constructionCost += component8.m_ConstructionCost;
						}
						if (base.EntityManager.TryGetComponent<ConsumptionData>(componentData.m_Prefab, out var component9))
						{
							upKeepCost += (uint)component9.m_Upkeep;
						}
						objectSubObjectInfo.m_Position = value;
						objectSubObjectInfo.m_Rotation = value2;
						objectSubObjectInfo.m_ParentMesh = num;
						objectSubObjectInfo.m_GroupIndex = groupIndex;
						objectSubObjectInfo.m_Probability = probability;
						subObjectList.Add(objectSubObjectInfo);
					}
				}
				return;
			}
		}
		subObjectList = null;
		subEffectList = null;
		subActivityList = null;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_SaveInstanceQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.Object>(), ComponentType.ReadOnly<SaveInstance>());
		RequireForUpdate(m_SaveInstanceQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeArray<Entity> nativeArray = m_SaveInstanceQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			base.EntityManager.RemoveComponent<SaveInstance>(m_SaveInstanceQuery);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i];
				base.EntityManager.RemoveComponent<SaveInstance>(entity);
				if (base.EntityManager.HasComponent<Game.Objects.SubObject>(entity) || base.EntityManager.HasComponent<Game.Net.SubNet>(entity) || base.EntityManager.HasComponent<Game.Areas.SubArea>(entity))
				{
					PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(entity);
					PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(componentData);
					uint constructionCost = 0u;
					uint upKeepCost = 0u;
					UpdateObjectSubObjects(entity, prefab, ref constructionCost, ref upKeepCost);
					UpdateObjectSubNets(entity, prefab, ref constructionCost, ref upKeepCost);
					UpdateObjectSubAreas(entity, prefab, ref constructionCost, ref upKeepCost);
					if (prefab is AssetStampPrefab)
					{
						AssetStampPrefab obj = prefab as AssetStampPrefab;
						obj.m_ConstructionCost = constructionCost;
						obj.m_UpKeepCost = upKeepCost;
					}
					m_PrefabSystem.UpdatePrefab(prefab, entity);
					prefab.asset?.MarkDirty();
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `public static RemoveComponent<T>(Game.Prefabs.PrefabBase asset) : System.Void`  

```csharp
public static System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase asset);
```

- `public static RemoveComponent(Game.Prefabs.PrefabBase asset, System.Type componentType) : System.Void`  

```csharp
public static void RemoveComponent(PrefabBase asset, Type componentType)
	{
		ComponentBase componentExactly = asset.GetComponentExactly(componentType);
		if (!(componentExactly == null))
		{
			asset.Remove(componentType);
			UnityEngine.Object.DestroyImmediate(componentExactly, allowDestroyingAssets: true);
		}
	}
```

- `private UpdateObjectSubAreas(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private void UpdateObjectSubAreas(Entity instanceEntity, PrefabBase prefabBase, ref uint constructionCost, ref uint upKeepCost)
	{
		List<ObjectSubAreaInfo> list = ListObjectSubAreas(instanceEntity, ref constructionCost, ref upKeepCost);
		if (list != null && list.Count != 0)
		{
			ObjectSubAreas objectSubAreas = prefabBase.GetComponent<ObjectSubAreas>();
			if (objectSubAreas == null)
			{
				objectSubAreas = AddComponent<ObjectSubAreas>(prefabBase);
			}
			objectSubAreas.m_SubAreas = list.ToArray();
		}
		else if (prefabBase.GetComponent<ObjectSubAreas>() != null)
		{
			RemoveComponent<ObjectSubAreas>(prefabBase);
		}
	}
```

- `private UpdateObjectSubNets(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private void UpdateObjectSubNets(Entity instanceEntity, PrefabBase prefabBase, ref uint constructionCost, ref uint upKeepCost)
	{
		ListObjectSubNets(instanceEntity, out var subNetList, out var subLaneList, ref constructionCost, ref upKeepCost);
		if (subNetList != null && subNetList.Count != 0)
		{
			ObjectSubNets objectSubNets = prefabBase.GetComponent<ObjectSubNets>();
			if (objectSubNets == null)
			{
				objectSubNets = AddComponent<ObjectSubNets>(prefabBase);
			}
			if (objectSubNets.m_InvertWhen == NetInvertMode.LefthandTraffic && m_CityConfigurationSystem.leftHandTraffic)
			{
				objectSubNets.m_InvertWhen = NetInvertMode.RighthandTraffic;
			}
			else if (objectSubNets.m_InvertWhen == NetInvertMode.RighthandTraffic && !m_CityConfigurationSystem.leftHandTraffic)
			{
				objectSubNets.m_InvertWhen = NetInvertMode.LefthandTraffic;
			}
			objectSubNets.m_SubNets = subNetList.ToArray();
		}
		else if (prefabBase.GetComponent<ObjectSubNets>() != null)
		{
			RemoveComponent<ObjectSubNets>(prefabBase);
		}
		if (subLaneList != null && subLaneList.Count != 0)
		{
			ObjectSubLanes objectSubLanes = prefabBase.GetComponent<ObjectSubLanes>();
			if (objectSubLanes == null)
			{
				objectSubLanes = AddComponent<ObjectSubLanes>(prefabBase);
			}
			objectSubLanes.m_SubLanes = subLaneList.ToArray();
		}
		else if (prefabBase.GetComponent<ObjectSubLanes>() != null)
		{
			RemoveComponent<ObjectSubLanes>(prefabBase);
		}
	}
```

- `private UpdateObjectSubObjects(Unity.Entities.Entity instanceEntity, Game.Prefabs.PrefabBase prefabBase, System.UInt32& constructionCost, System.UInt32& upKeepCost) : System.Void`  

```csharp
private void UpdateObjectSubObjects(Entity instanceEntity, PrefabBase prefabBase, ref uint constructionCost, ref uint upKeepCost)
	{
		ListObjectSubObjects(instanceEntity, out var subObjectList, out var subEffectList, out var subActivityList, ref constructionCost, ref upKeepCost);
		if (subObjectList != null && subObjectList.Count != 0)
		{
			ObjectSubObjects objectSubObjects = prefabBase.GetComponent<ObjectSubObjects>();
			if (objectSubObjects == null)
			{
				objectSubObjects = AddComponent<ObjectSubObjects>(prefabBase);
			}
			objectSubObjects.m_SubObjects = subObjectList.ToArray();
		}
		else if (prefabBase.GetComponent<ObjectSubObjects>() != null)
		{
			RemoveComponent<ObjectSubObjects>(prefabBase);
		}
		if (subEffectList != null && subEffectList.Count != 0)
		{
			EffectSource effectSource = prefabBase.GetComponent<EffectSource>();
			if (effectSource == null)
			{
				effectSource = AddComponent<EffectSource>(prefabBase);
			}
			effectSource.m_Effects = new List<EffectSource.EffectSettings>();
			effectSource.m_Effects.AddRange(subEffectList);
		}
		else if (prefabBase.GetComponent<EffectSource>() != null)
		{
			RemoveComponent<EffectSource>(prefabBase);
		}
		if (subActivityList != null && subActivityList.Count != 0)
		{
			Game.Prefabs.ActivityLocation activityLocation = prefabBase.GetComponent<Game.Prefabs.ActivityLocation>();
			if (activityLocation == null)
			{
				activityLocation = AddComponent<Game.Prefabs.ActivityLocation>(prefabBase);
			}
			activityLocation.m_Locations = subActivityList.ToArray();
		}
		else if (prefabBase.GetComponent<Game.Prefabs.ActivityLocation>() != null)
		{
			RemoveComponent<Game.Prefabs.ActivityLocation>(prefabBase);
		}
	}
```


