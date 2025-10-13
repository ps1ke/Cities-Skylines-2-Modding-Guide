# Game.UI.InGame.UniqueAssetTrackingSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.InGame.IUniqueAssetTrackingSystem`  

## Code

```csharp
public class UniqueAssetTrackingSystem : Game.GameSystemBase, Game.UI.InGame.IUniqueAssetTrackingSystem
{
    private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery;
    private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery;
    private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery;
    private System.Boolean m_Loaded;
    private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField;
    private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField;

    public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set; }
    public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set; }

    public UniqueAssetTrackingSystem();

    private System.Boolean GetLoaded();
    public System.Boolean IsPlacedUniqueAsset(Unity.Entities.Entity entity);
    public System.Boolean IsUniqueAsset(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery;
```

- `private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField`  

```csharp
private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField;
```

- `private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField`  

```csharp
private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField;
```


## Properties

- `public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set }`  

```csharp
public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set; }
```

- `public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set }`  

```csharp
public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set; }
```


## Constructors

- `public UniqueAssetTrackingSystem()`  

```csharp
[Preserve]
	public UniqueAssetTrackingSystem()
	{
	}
```


## Methods

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public IsPlacedUniqueAsset(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public bool IsPlacedUniqueAsset(Entity entity)
	{
		if (IsUniqueAsset(entity))
		{
			return placedUniqueAssets.Contains(entity);
		}
		return false;
	}
```

- `public IsUniqueAsset(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public bool IsUniqueAsset(Entity entity)
	{
		if (base.EntityManager.TryGetComponent<PlaceableObjectData>(entity, out var component))
		{
			return (component.m_Flags & PlacementFlags.Unique) != 0;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoadedUniqueAssetQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>());
		m_DeletedUniqueAssetQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_PlacedUniqueAssetQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		placedUniqueAssets = new NativeParallelHashSet<Entity>(32, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		placedUniqueAssets.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		placedUniqueAssets.Clear();
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (GetLoaded() && !m_LoadedUniqueAssetQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<PrefabRef> nativeArray = m_LoadedUniqueAssetQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				placedUniqueAssets.Add(nativeArray[i].m_Prefab);
				EventUniqueAssetStatusChanged?.Invoke(nativeArray[i].m_Prefab, arg2: true);
			}
			nativeArray.Dispose();
		}
		if (!m_PlacedUniqueAssetQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<PrefabRef> nativeArray2 = m_PlacedUniqueAssetQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				placedUniqueAssets.Add(nativeArray2[j].m_Prefab);
				EventUniqueAssetStatusChanged?.Invoke(nativeArray2[j].m_Prefab, arg2: true);
			}
			nativeArray2.Dispose();
		}
		if (!m_DeletedUniqueAssetQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<PrefabRef> nativeArray3 = m_DeletedUniqueAssetQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			for (int k = 0; k < nativeArray3.Length; k++)
			{
				placedUniqueAssets.Remove(nativeArray3[k].m_Prefab);
				EventUniqueAssetStatusChanged?.Invoke(nativeArray3[k].m_Prefab, arg2: false);
			}
			nativeArray3.Dispose();
		}
	}
```


