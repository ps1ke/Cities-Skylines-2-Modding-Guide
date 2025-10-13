# Game.UI.InGame.ChirperUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ChirperUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem;
    private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_ModifiedChirpQuery;
    private Unity.Entities.EntityQuery m_CreatedChirpQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding;
    private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding;
    private static const System.String kGroup;
    private static const System.Int32 kBrandIconSize;

    public ChirperUISystem();

    private System.Void AddLike(Unity.Entities.Entity entity);
    public System.Void BindChirp(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity chirpEntity, System.Boolean newChirp);
    private System.Void BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, System.Int32 linkIndex);
    public System.Void BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.UI.NameSystem+Name name);
    private System.Void BindChirpSender(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.String GetAvatar(Unity.Entities.Entity chirpEntity);
    public System.String GetMessageID(Unity.Entities.Entity chirp);
    private System.Int32 GetRandomIndex(Unity.Entities.Entity chirpEntity);
    private Unity.Collections.NativeArray<Unity.Entities.Entity> GetSortedChirps(Unity.Entities.EntityQuery chirpQuery);
    private System.UInt32 GetTicks(System.UInt32 frameIndex);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void PublishAddedChirps();
    private System.Void RemoveLike(Unity.Entities.Entity entity);
    private System.Void SelectLink(System.String target);
    private System.Void UpdateChirps(Colossal.UI.Binding.IJsonWriter binder);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem`  

```csharp
private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem;
```

- `private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem`  

```csharp
private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding;
```

- `private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Int32 kBrandIconSize`  

```csharp
private static const System.Int32 kBrandIconSize;
```


## Constructors

- `public ChirperUISystem()`  

```csharp
[Preserve]
	public ChirperUISystem()
	{
	}
```


## Methods

- `private AddLike(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void AddLike(Entity entity)
	{
		Game.Triggers.Chirp componentData = base.EntityManager.GetComponentData<Game.Triggers.Chirp>(entity);
		componentData.m_Flags |= ChirpFlags.Liked;
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		entityCommandBuffer.SetComponent(entity, componentData);
		entityCommandBuffer.AddComponent(entity, default(Updated));
	}
```

- `public BindChirp(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity chirpEntity, System.Boolean newChirp = False) : System.Void`  

```csharp
public void BindChirp(IJsonWriter binder, Entity chirpEntity, bool newChirp = false)
	{
		string messageID = GetMessageID(chirpEntity);
		Game.Triggers.Chirp componentData = base.EntityManager.GetComponentData<Game.Triggers.Chirp>(chirpEntity);
		binder.TypeBegin("chirper.Chirp");
		binder.PropertyName("entity");
		binder.Write(chirpEntity);
		binder.PropertyName("sender");
		BindChirpSender(binder, chirpEntity);
		if (newChirp && base.EntityManager.HasComponent<ChirperAccountData>(componentData.m_Sender))
		{
			Telemetry.Chirp(base.EntityManager.GetComponentData<PrefabRef>(chirpEntity).m_Prefab, componentData.m_Likes);
		}
		binder.PropertyName("date");
		binder.Write(GetTicks(componentData.m_CreationFrame));
		binder.PropertyName("messageId");
		binder.Write(messageID);
		binder.PropertyName("links");
		if (base.EntityManager.TryGetBuffer(chirpEntity, isReadOnly: true, out DynamicBuffer<ChirpEntity> buffer))
		{
			int length = buffer.Length;
			binder.ArrayBegin(length);
			for (int i = 0; i < length; i++)
			{
				BindChirpLink(binder, chirpEntity, i);
			}
			binder.ArrayEnd();
		}
		else
		{
			binder.WriteEmptyArray();
		}
		binder.PropertyName("likes");
		binder.Write(componentData.m_Likes);
		binder.PropertyName("liked");
		binder.Write((componentData.m_Flags & ChirpFlags.Liked) != 0);
		binder.TypeEnd();
	}
```

- `private BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, System.Int32 linkIndex) : System.Void`  

```csharp
public void BindChirpLink(IJsonWriter binder, Entity entity, NameSystem.Name name)
	{
		binder.TypeBegin("chirper.ChirpLink");
		binder.PropertyName("name");
		binder.Write(name);
		binder.PropertyName("target");
		if (base.EntityManager.HasComponent<CompanyData>(entity) && base.EntityManager.TryGetComponent<PropertyRenter>(entity, out var component))
		{
			entity = component.m_Property;
		}
		string value = ((entity != Entity.Null) ? URI.FromEntity(entity) : string.Empty);
		if (base.EntityManager.HasComponent<ChirperAccountData>(entity))
		{
			ChirperAccount prefab = m_PrefabSystem.GetPrefab<ChirperAccount>(entity);
			value = URI.FromInfoView(m_PrefabSystem.GetEntity(prefab.m_InfoView));
		}
		binder.Write(value);
		binder.TypeEnd();
	}
```

- `public BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.UI.NameSystem+Name name) : System.Void`  

```csharp
public void BindChirpLink(IJsonWriter binder, Entity entity, NameSystem.Name name)
	{
		binder.TypeBegin("chirper.ChirpLink");
		binder.PropertyName("name");
		binder.Write(name);
		binder.PropertyName("target");
		if (base.EntityManager.HasComponent<CompanyData>(entity) && base.EntityManager.TryGetComponent<PropertyRenter>(entity, out var component))
		{
			entity = component.m_Property;
		}
		string value = ((entity != Entity.Null) ? URI.FromEntity(entity) : string.Empty);
		if (base.EntityManager.HasComponent<ChirperAccountData>(entity))
		{
			ChirperAccount prefab = m_PrefabSystem.GetPrefab<ChirperAccount>(entity);
			value = URI.FromInfoView(m_PrefabSystem.GetEntity(prefab.m_InfoView));
		}
		binder.Write(value);
		binder.TypeEnd();
	}
```

- `private BindChirpSender(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindChirpSender(IJsonWriter binder, Entity entity)
	{
		Game.Triggers.Chirp componentData = base.EntityManager.GetComponentData<Game.Triggers.Chirp>(entity);
		binder.TypeBegin("chirper.ChirpSender");
		ChirpLinkSystem.CachedChirpData data;
		if (base.EntityManager.Exists(componentData.m_Sender))
		{
			binder.PropertyName("entity");
			binder.Write(componentData.m_Sender);
			binder.PropertyName("link");
			BindChirpLink(binder, componentData.m_Sender, m_NameSystem.GetName(componentData.m_Sender));
		}
		else if (m_ChirpLinkSystem.TryGetData(entity, out data))
		{
			binder.PropertyName("entity");
			binder.Write(data.m_Sender.m_Entity);
			binder.PropertyName("link");
			BindChirpLink(binder, Entity.Null, data.m_Sender.m_Name);
		}
		else
		{
			binder.PropertyName("entity");
			binder.Write(Entity.Null);
			binder.PropertyName("link");
			BindChirpLink(binder, Entity.Null, NameSystem.Name.CustomName(string.Empty));
		}
		binder.TypeEnd();
	}
```

- `private GetAvatar(Unity.Entities.Entity chirpEntity) : System.String`  

```csharp
[CanBeNull]
	private string GetAvatar(Entity chirpEntity)
	{
		if (base.EntityManager.TryGetComponent<Game.Triggers.Chirp>(chirpEntity, out var component))
		{
			Entity entity = component.m_Sender;
			if (base.EntityManager.TryGetComponent<CompanyData>(entity, out var component2))
			{
				entity = component2.m_Brand;
			}
			if (base.EntityManager.TryGetComponent<PrefabData>(entity, out var component3) && m_PrefabSystem.TryGetPrefab<PrefabBase>(component3, out var prefab))
			{
				string icon = ImageSystem.GetIcon(prefab);
				if (icon != null)
				{
					return icon;
				}
				if (prefab is ChirperAccount chirperAccount && chirperAccount.m_InfoView != null)
				{
					return chirperAccount.m_InfoView.m_IconPath;
				}
				if (prefab is BrandPrefab brandPrefab)
				{
					return $"{brandPrefab.thumbnailUrl}?width={32}&height={32}";
				}
			}
		}
		return null;
	}
```

- `public GetMessageID(Unity.Entities.Entity chirp) : System.String`  

```csharp
public string GetMessageID(Entity chirp)
	{
		if (base.EntityManager.TryGetComponent<PrefabRef>(chirp, out var component) && base.EntityManager.TryGetBuffer(chirp, isReadOnly: true, out DynamicBuffer<RandomLocalizationIndex> buffer) && buffer.Length > 0 && m_PrefabSystem.TryGetPrefab<PrefabBase>(component.m_Prefab, out var prefab) && prefab.TryGet<RandomLocalization>(out var component2))
		{
			return LocalizationUtils.AppendIndex(component2.m_LocalizationID, buffer[0]);
		}
		return string.Empty;
	}
```

- `private GetRandomIndex(Unity.Entities.Entity chirpEntity) : System.Int32`  

```csharp
private int GetRandomIndex(Entity chirpEntity)
	{
		if (base.EntityManager.TryGetComponent<Game.Triggers.Chirp>(chirpEntity, out var component) && base.EntityManager.TryGetBuffer(component.m_Sender, isReadOnly: true, out DynamicBuffer<RandomLocalizationIndex> buffer) && buffer.Length > 0)
		{
			return buffer[0].m_Index;
		}
		return 0;
	}
```

- `private GetSortedChirps(Unity.Entities.EntityQuery chirpQuery) : Unity.Collections.NativeArray<Unity.Entities.Entity>`  

```csharp
private NativeArray<Entity> GetSortedChirps(EntityQuery chirpQuery)
	{
		NativeArray<Entity> nativeArray = chirpQuery.ToEntityArray(Allocator.Temp);
		nativeArray.Sort(new ChirpComparer(base.EntityManager));
		return nativeArray;
	}
```

- `private GetTicks(System.UInt32 frameIndex) : System.UInt32`  

```csharp
private uint GetTicks(uint frameIndex)
	{
		return frameIndex - TimeData.GetSingleton(m_TimeDataQuery).m_FirstFrame;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_SelectedInfoUISystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_InfoviewsUISystem = base.World.GetOrCreateSystemManaged<InfoviewsUISystem>();
		m_ChirpLinkSystem = base.World.GetOrCreateSystemManaged<ChirpLinkSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_ChirpQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Triggers.Chirp>(),
				ComponentType.ReadOnly<RandomLocalizationIndex>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ModifiedChirpQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Triggers.Chirp>(),
				ComponentType.ReadOnly<PrefabRef>()
			}
		});
		m_ModifiedChirpQuery.AddOrderVersionFilter();
		m_ModifiedChirpQuery.AddChangedVersionFilter(ComponentType.ReadOnly<Game.Triggers.Chirp>());
		m_CreatedChirpQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Triggers.Chirp>(),
				ComponentType.ReadOnly<RandomLocalizationIndex>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Created>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		AddBinding(m_ChirpsBinding = new RawValueBinding("chirper", "chirps", UpdateChirps));
		AddBinding(m_ChirpAddedBinding = new RawEventBinding("chirper", "chirpAdded"));
		AddBinding(new TriggerBinding<Entity>("chirper", "addLike", AddLike));
		AddBinding(new TriggerBinding<Entity>("chirper", "removeLike", RemoveLike));
		AddBinding(new TriggerBinding<string>("chirper", "selectLink", SelectLink));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ModifiedChirpQuery.IsEmpty)
		{
			m_ChirpsBinding.Update();
		}
		if (m_ChirpAddedBinding.active && !m_CreatedChirpQuery.IsEmptyIgnoreFilter)
		{
			PublishAddedChirps();
		}
	}
```

- `private PublishAddedChirps() : System.Void`  

```csharp
private void PublishAddedChirps()
	{
		NativeArray<Entity> sortedChirps = GetSortedChirps(m_CreatedChirpQuery);
		int length = sortedChirps.Length;
		for (int i = 0; i < length; i++)
		{
			IJsonWriter binder = m_ChirpAddedBinding.EventBegin();
			BindChirp(binder, sortedChirps[i], newChirp: true);
			m_ChirpAddedBinding.EventEnd();
		}
	}
```

- `private RemoveLike(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void RemoveLike(Entity entity)
	{
		Game.Triggers.Chirp componentData = base.EntityManager.GetComponentData<Game.Triggers.Chirp>(entity);
		componentData.m_Flags &= ~ChirpFlags.Liked;
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		entityCommandBuffer.SetComponent(entity, componentData);
		entityCommandBuffer.AddComponent(entity, default(Updated));
	}
```

- `private SelectLink(System.String target) : System.Void`  

```csharp
private void SelectLink(string target)
	{
		if (URI.TryParseEntity(target, out var entity) && base.EntityManager.Exists(entity))
		{
			m_SelectedInfoUISystem.SetSelection(entity);
			m_SelectedInfoUISystem.Focus(entity);
		}
		if (URI.TryParseInfoview(target, out var entity2) && base.EntityManager.Exists(entity2))
		{
			m_InfoviewsUISystem.SetActiveInfoview(entity2);
		}
	}
```

- `private UpdateChirps(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void UpdateChirps(IJsonWriter binder)
	{
		NativeArray<Entity> sortedChirps = GetSortedChirps(m_ChirpQuery);
		binder.ArrayBegin(sortedChirps.Length);
		for (int i = 0; i < sortedChirps.Length; i++)
		{
			BindChirp(binder, sortedChirps[i]);
		}
		binder.ArrayEnd();
	}
```


## Nested types

- `Game.UI.InGame.ChirperUISystem+ChirpComparer`  

