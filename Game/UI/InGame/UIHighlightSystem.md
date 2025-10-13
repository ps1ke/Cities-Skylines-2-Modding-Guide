# Game.UI.InGame.UIHighlightSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UIHighlightSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
    private System.Boolean m_SkipUpdate;
    private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle;

    public UIHighlightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void SkipUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
```

- `private System.Boolean m_SkipUpdate`  

```csharp
private System.Boolean m_SkipUpdate;
```

- `private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.UIHighlightSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UIHighlightSystem()`  

```csharp
[Preserve]
	public UIHighlightSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_UnlockedPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		RequireForUpdate(m_UnlockedPrefabQuery);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_SkipUpdate)
		{
			m_SkipUpdate = false;
			return;
		}
		HighlightJob jobData = new HighlightJob
		{
			m_UnlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Unlock_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UIObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AssetCategories = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UIAssetCategoryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ToolbarGroups = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UIToolbarGroupData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_UnlockedPrefabQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<UIHighlight>());
		try
		{
			base.EntityManager.RemoveComponent<UIHighlight>(entityQuery);
		}
		finally
		{
			entityQuery.Dispose();
		}
		m_SkipUpdate = true;
	}
```

- `public SkipUpdate() : System.Void`  

```csharp
public void SkipUpdate()
	{
		m_SkipUpdate = true;
	}
```


## Nested types

- `Game.UI.InGame.UIHighlightSystem+HighlightJob`  
- `Game.UI.InGame.UIHighlightSystem+TypeHandle`  

