# Game.UI.InGame.FeatureUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class FeatureUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Unity.Entities.EntityQuery m_UnlockedFeatureQuery;
    private Unity.Entities.EntityQuery m_UnlocksQuery;
    private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding;
    private static const System.String kGroup;

    public FeatureUISystem();

    private System.Void BindLockedFeatures(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Unity.Entities.EntityQuery m_UnlockedFeatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedFeatureQuery;
```

- `private Unity.Entities.EntityQuery m_UnlocksQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlocksQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public FeatureUISystem()`  

```csharp
[Preserve]
	public FeatureUISystem()
	{
	}
```


## Methods

- `private BindLockedFeatures(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindLockedFeatures(IJsonWriter writer)
	{
		NativeArray<Entity> nativeArray = m_UnlockedFeatureQuery.ToEntityArray(Allocator.Temp);
		NativeArray<PrefabData> nativeArray2 = m_UnlockedFeatureQuery.ToComponentDataArray<PrefabData>(Allocator.Temp);
		writer.ArrayBegin(nativeArray2.Length);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity prefabEntity = nativeArray[i];
			PrefabData prefabData = nativeArray2[i];
			FeaturePrefab prefab = m_PrefabSystem.GetPrefab<FeaturePrefab>(prefabData);
			writer.TypeBegin("Game.UI.InGame.LockedFeature");
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("requirements");
			m_PrefabUISystem.BindPrefabRequirements(writer, prefabEntity);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_UnlockedFeatureQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<FeatureData>(), ComponentType.ReadOnly<Locked>());
		m_UnlocksQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		AddBinding(m_FeaturesBinding = new RawValueBinding("feature", "lockedFeatures", BindLockedFeatures));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_FeaturesBinding.Update();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (PrefabUtils.HasUnlockedPrefab<FeatureData>(base.EntityManager, m_UnlocksQuery))
		{
			m_FeaturesBinding.Update();
		}
	}
```


