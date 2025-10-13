# Game.UI.Editor.BuildingLotFieldBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public abstract class BuildingLotFieldBase : Game.UI.Widgets.IFieldBuilderFactory
{
    private static readonly System.Int32 kMaxSize;
    private static readonly System.Int32 kMinSize;

    protected BuildingLotFieldBase();

    private static System.Void AddCells(Game.Prefabs.BuildingPrefab prefab, Game.UI.Widgets.IWidget widget, Unity.Mathematics.int2 dir, System.Int32 count);
    public abstract Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
    protected Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes, System.Boolean horizontal);
    private static System.Boolean TryGetBuildingPrefab(Game.Reflection.IValueAccessor accessor, Game.Prefabs.BuildingPrefab& prefab);
}
```


## Fields

- `private static readonly System.Int32 kMaxSize`  

```csharp
private static readonly System.Int32 kMaxSize;
```

- `private static readonly System.Int32 kMinSize`  

```csharp
private static readonly System.Int32 kMinSize;
```


## Constructors

- `protected BuildingLotFieldBase()`  

```csharp
protected BuildingLotFieldBase();
```


## Methods

- `private static AddCells(Game.Prefabs.BuildingPrefab prefab, Game.UI.Widgets.IWidget widget, Unity.Mathematics.int2 dir, System.Int32 count = 1) : System.Void`  

```csharp
private static void AddCells(BuildingPrefab prefab, IWidget widget, int2 dir, int count = 1)
	{
		int2 @int = new int2(prefab.m_LotWidth, prefab.m_LotDepth);
		int2 int2 = new int2(@int.x + math.abs(dir.x) * count, @int.y + math.abs(dir.y) * count);
		float2 @float = 4f * (float2)dir * (int2 - @int);
		float3 float2 = new float3(@float.x, 0f, @float.y);
		prefab.m_LotWidth = int2.x;
		prefab.m_LotDepth = int2.y;
		Entity entity = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>().GetEntity(prefab);
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		ObjectMeshInfo[] meshes = prefab.m_Meshes;
		for (int i = 0; i < meshes.Length; i++)
		{
			meshes[i].m_Position += float2;
		}
		DynamicBuffer<SubMesh> buffer = entityManager.GetBuffer<SubMesh>(entity);
		for (int j = 0; j < buffer.Length; j++)
		{
			SubMesh value = buffer[j];
			value.m_Position += float2;
			buffer[j] = value;
		}
		if (prefab.TryGet<ObjectSubObjects>(out var component))
		{
			for (int num = component.m_SubObjects.Length - 1; num >= 0; num--)
			{
				component.m_SubObjects[num].m_Position += float2;
			}
		}
		if (prefab.TryGet<ObjectSubAreas>(out var component2))
		{
			for (int num2 = component2.m_SubAreas.Length - 1; num2 >= 0; num2--)
			{
				ObjectSubAreaInfo objectSubAreaInfo = component2.m_SubAreas[num2];
				for (int k = 0; k < objectSubAreaInfo.m_NodePositions.Length; k++)
				{
					objectSubAreaInfo.m_NodePositions[k] += float2;
				}
			}
		}
		if (prefab.TryGet<ObjectSubLanes>(out var component3))
		{
			for (int num3 = component3.m_SubLanes.Length - 1; num3 >= 0; num3--)
			{
				ObjectSubLaneInfo objectSubLaneInfo = component3.m_SubLanes[num3];
				objectSubLaneInfo.m_BezierCurve = new Bezier4x3
				{
					a = objectSubLaneInfo.m_BezierCurve.a + float2,
					b = objectSubLaneInfo.m_BezierCurve.b + float2,
					c = objectSubLaneInfo.m_BezierCurve.c + float2,
					d = objectSubLaneInfo.m_BezierCurve.d + float2
				};
			}
		}
		if (prefab.TryGet<ObjectSubNets>(out var component4))
		{
			for (int num4 = component4.m_SubNets.Length - 1; num4 >= 0; num4--)
			{
				ObjectSubNetInfo objectSubNetInfo = component4.m_SubNets[num4];
				objectSubNetInfo.m_BezierCurve = new Bezier4x3
				{
					a = objectSubNetInfo.m_BezierCurve.a + float2,
					b = objectSubNetInfo.m_BezierCurve.b + float2,
					c = objectSubNetInfo.m_BezierCurve.c + float2,
					d = objectSubNetInfo.m_BezierCurve.d + float2
				};
			}
		}
		if (prefab.TryGet<EffectSource>(out var component5))
		{
			for (int num5 = component5.m_Effects.Count - 1; num5 >= 0; num5--)
			{
				component5.m_Effects[num5].m_PositionOffset += float2;
			}
		}
		World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<EditorPanelUISystem>()?.OnValueChanged(widget);
	}
```

- `public abstract TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
protected FieldBuilder TryCreate(Type memberType, object[] attributes, bool horizontal)
	{
		return delegate(IValueAccessor accessor)
		{
			IntInputField intInputField = new IntInputField
			{
				displayName = (horizontal ? "Lot Width" : "Lot Depth"),
				accessor = new CastAccessor<int>(accessor, (object input) => (int)input, (int input) => input),
				min = kMinSize,
				max = kMaxSize
			};
			if (TryGetBuildingPrefab(accessor, out var prefab))
			{
				Button button1 = new Button
				{
					displayName = (horizontal ? "Expand Left" : "Expand Front")
				};
				button1.action = delegate
				{
					AddCells(prefab, button1, new int2(horizontal ? (-1) : 0, (!horizontal) ? (-1) : 0));
				};
				button1.disabled = () => (!horizontal) ? (prefab.m_LotDepth >= kMaxSize) : (prefab.m_LotWidth >= kMaxSize);
				Button button2 = new Button
				{
					displayName = (horizontal ? "Expand Right" : "Expand Back")
				};
				button2.action = delegate
				{
					AddCells(prefab, button2, new int2(horizontal ? 1 : 0, (!horizontal) ? 1 : 0));
				};
				button2.disabled = () => (!horizontal) ? (prefab.m_LotDepth >= kMaxSize) : (prefab.m_LotWidth >= kMaxSize);
				Button button3 = new Button
				{
					displayName = (horizontal ? "Shrink Left" : "Shrink Front")
				};
				button3.action = delegate
				{
					AddCells(prefab, button3, new int2(horizontal ? (-1) : 0, (!horizontal) ? (-1) : 0), -1);
				};
				button3.disabled = () => (!horizontal) ? (prefab.m_LotDepth <= kMinSize) : (prefab.m_LotWidth <= kMinSize);
				Button button4 = new Button
				{
					displayName = (horizontal ? "Shrink Right" : "Shrink Back")
				};
				button4.action = delegate
				{
					AddCells(prefab, button4, new int2(horizontal ? 1 : 0, (!horizontal) ? 1 : 0), -1);
				};
				button4.disabled = () => (!horizontal) ? (prefab.m_LotDepth <= kMinSize) : (prefab.m_LotWidth <= kMinSize);
				return new Column
				{
					children = new IWidget[3]
					{
						intInputField,
						new ButtonRow
						{
							children = new Button[2] { button1, button3 }
						},
						new ButtonRow
						{
							children = new Button[2] { button2, button4 }
						}
					}
				};
			}
			return intInputField;
		};
	}
```

- `protected TryCreate(System.Type memberType, System.Object[] attributes, System.Boolean horizontal) : Game.UI.Widgets.FieldBuilder`  

```csharp
protected FieldBuilder TryCreate(Type memberType, object[] attributes, bool horizontal)
	{
		return delegate(IValueAccessor accessor)
		{
			IntInputField intInputField = new IntInputField
			{
				displayName = (horizontal ? "Lot Width" : "Lot Depth"),
				accessor = new CastAccessor<int>(accessor, (object input) => (int)input, (int input) => input),
				min = kMinSize,
				max = kMaxSize
			};
			if (TryGetBuildingPrefab(accessor, out var prefab))
			{
				Button button1 = new Button
				{
					displayName = (horizontal ? "Expand Left" : "Expand Front")
				};
				button1.action = delegate
				{
					AddCells(prefab, button1, new int2(horizontal ? (-1) : 0, (!horizontal) ? (-1) : 0));
				};
				button1.disabled = () => (!horizontal) ? (prefab.m_LotDepth >= kMaxSize) : (prefab.m_LotWidth >= kMaxSize);
				Button button2 = new Button
				{
					displayName = (horizontal ? "Expand Right" : "Expand Back")
				};
				button2.action = delegate
				{
					AddCells(prefab, button2, new int2(horizontal ? 1 : 0, (!horizontal) ? 1 : 0));
				};
				button2.disabled = () => (!horizontal) ? (prefab.m_LotDepth >= kMaxSize) : (prefab.m_LotWidth >= kMaxSize);
				Button button3 = new Button
				{
					displayName = (horizontal ? "Shrink Left" : "Shrink Front")
				};
				button3.action = delegate
				{
					AddCells(prefab, button3, new int2(horizontal ? (-1) : 0, (!horizontal) ? (-1) : 0), -1);
				};
				button3.disabled = () => (!horizontal) ? (prefab.m_LotDepth <= kMinSize) : (prefab.m_LotWidth <= kMinSize);
				Button button4 = new Button
				{
					displayName = (horizontal ? "Shrink Right" : "Shrink Back")
				};
				button4.action = delegate
				{
					AddCells(prefab, button4, new int2(horizontal ? 1 : 0, (!horizontal) ? 1 : 0), -1);
				};
				button4.disabled = () => (!horizontal) ? (prefab.m_LotDepth <= kMinSize) : (prefab.m_LotWidth <= kMinSize);
				return new Column
				{
					children = new IWidget[3]
					{
						intInputField,
						new ButtonRow
						{
							children = new Button[2] { button1, button3 }
						},
						new ButtonRow
						{
							children = new Button[2] { button2, button4 }
						}
					}
				};
			}
			return intInputField;
		};
	}
```

- `private static TryGetBuildingPrefab(Game.Reflection.IValueAccessor accessor, Game.Prefabs.BuildingPrefab& prefab) : System.Boolean`  

```csharp
private static bool TryGetBuildingPrefab(IValueAccessor accessor, out BuildingPrefab prefab)
	{
		if (accessor is FieldAccessor { parent: ObjectAccessor<object> parent })
		{
			prefab = parent.GetValue() as BuildingPrefab;
			return prefab != null;
		}
		prefab = null;
		return false;
	}
```


## Nested types

- `Game.UI.Editor.BuildingLotFieldBase+<>c`  
- `Game.UI.Editor.BuildingLotFieldBase+<>c__DisplayClass3_0`  
- `Game.UI.Editor.BuildingLotFieldBase+<>c__DisplayClass3_1`  
- `Game.UI.Editor.BuildingLotFieldBase+<>c__DisplayClass3_2`  

