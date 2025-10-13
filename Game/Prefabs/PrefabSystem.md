# Game.Prefabs.PrefabSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Colossal.Logging.ILog m_UnlockingLog;
    private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged;
    private Game.UpdateSystem m_UpdateSystem;
    private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs;
    private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs;
    private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable;
    private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable;
    private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs;
    private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices;
    private Unity.Entities.ComponentTypeSet m_UnlockableTypes;

    internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get; }

    public PrefabSystem();

    public System.Void AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData);
    public System.Void AddObsoleteID(Unity.Entities.Entity entity, Game.Prefabs.PrefabID id);
    public System.Boolean AddPrefab(Game.Prefabs.PrefabBase prefab, System.String parentName, Game.Prefabs.PrefabBase parentPrefab, Game.Prefabs.ComponentBase parentComponent);
    public System.Void AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase unlocked);
    public System.Void AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase[] unlocked);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Prefabs.PrefabBase DuplicatePrefab(Game.Prefabs.PrefabBase template, System.String name);
    public System.Collections.Generic.IEnumerable<Game.Prefabs.ContentPrefab> GetAvailableContentPrefabs();
    public System.String[] GetAvailablePrerequisitesNames();
    public Unity.Entities.DynamicBuffer<T> GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly);
    public T GetComponentData<T>(Game.Prefabs.PrefabBase prefab);
    public Unity.Entities.Entity GetEntity(Game.Prefabs.PrefabBase prefab);
    public Game.Prefabs.PrefabID GetLoadedObsoleteID(System.Int32 loadedIndex);
    public Game.Prefabs.PrefabID GetObsoleteID(Game.Prefabs.PrefabData prefabData);
    public Game.Prefabs.PrefabID GetObsoleteID(Unity.Entities.Entity entity);
    public T GetPrefab<T>(Game.Prefabs.PrefabData prefabData);
    public T GetPrefab<T>(Unity.Entities.Entity entity);
    public T GetPrefab<T>(Game.Prefabs.PrefabRef refData);
    public System.String GetPrefabName(Unity.Entities.Entity entity);
    public T GetSingletonPrefab<T>(Unity.Entities.EntityQuery group);
    public System.Boolean HasComponent<T>(Game.Prefabs.PrefabBase prefab);
    public System.Boolean HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab);
    public System.Boolean IsAvailable(Game.Prefabs.PrefabBase prefab);
    public System.Boolean IsUnlockable(Game.Prefabs.PrefabBase prefab);
    private System.Boolean IsUnlockableImpl(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase prefab);
    public System.Boolean RemovePrefab(Game.Prefabs.PrefabBase prefab);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Boolean TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
    public System.Boolean TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component);
    public System.Boolean TryGetEntity(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity& entity);
    public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab);
    public System.Boolean TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab);
    public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab);
    public System.Boolean TryGetPrefab(Game.Prefabs.PrefabID id, Game.Prefabs.PrefabBase& prefab);
    public System.Boolean TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab);
    public System.Void UpdateAvailabilityCache();
    public System.Void UpdateLoadedIndices();
    public System.Void UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance);
    private System.Boolean UpdatePrefabs();
}
```


## Fields

- `private Colossal.Logging.ILog m_UnlockingLog`  

```csharp
private Colossal.Logging.ILog m_UnlockingLog;
```

- `private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged`  

```csharp
private Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+ObsoleteData> m_ObsoleteIDs;
```

- `private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.PrefabSystem+LoadedIndexData> m_LoadedIndexData;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_UpdateMap;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, Unity.Entities.Entity> m_Entities;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabBase, System.Boolean> m_IsUnlockable;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.ContentPrefab, System.Boolean> m_IsAvailable;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Game.Prefabs.PrefabID> m_LoadedObsoleteIDs;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.PrefabID, System.Int32> m_PrefabIndices;
```

- `private Unity.Entities.ComponentTypeSet m_UnlockableTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_UnlockableTypes;
```


## Properties

- `internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get }`  

```csharp
internal System.Collections.Generic.IEnumerable<Game.Prefabs.PrefabBase> prefabs { internal get; }
```


## Constructors

- `public PrefabSystem()`  

```csharp
[Preserve]
	public PrefabSystem()
	{
	}
```


## Methods

- `public AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData) : System.Void`  

```csharp
public System.Void AddComponentData<T>(Game.Prefabs.PrefabBase prefab, T componentData);
```

- `public AddObsoleteID(Unity.Entities.Entity entity, Game.Prefabs.PrefabID id) : System.Void`  

```csharp
public void AddObsoleteID(Entity entity, PrefabID id)
	{
		m_ObsoleteIDs.Add(new ObsoleteData
		{
			m_Entity = entity,
			m_ID = id
		});
		COSystemBase.baseLog.WarnFormat("Unknown prefab ID: {0}", id);
	}
```

- `public AddPrefab(Game.Prefabs.PrefabBase prefab, System.String parentName = null, Game.Prefabs.PrefabBase parentPrefab = null, Game.Prefabs.ComponentBase parentComponent = null) : System.Boolean`  

```csharp
public bool AddPrefab(PrefabBase prefab, string parentName = null, PrefabBase parentPrefab = null, ComponentBase parentComponent = null)
	{
		if (prefab == null)
		{
			if (parentName != null)
			{
				COSystemBase.baseLog.WarnFormat("Trying to add null prefab in {0}", parentName);
			}
			else if (parentPrefab != null && parentComponent != null)
			{
				COSystemBase.baseLog.WarnFormat("Trying to add null prefab in {0}/{1}", parentPrefab.name, parentComponent.name);
			}
			else if (parentPrefab != null)
			{
				COSystemBase.baseLog.WarnFormat("Trying to add null prefab in {0}", parentPrefab.name);
			}
			else
			{
				COSystemBase.baseLog.WarnFormat("Trying to add null prefab");
			}
			return false;
		}
		try
		{
			if (!m_Entities.ContainsKey(prefab))
			{
				if (!IsAvailable(prefab))
				{
					if (parentPrefab != null)
					{
						if (parentComponent != null)
						{
							COSystemBase.baseLog.ErrorFormat(prefab, "Dependency not available in {0}/{1}: {2}", parentPrefab.name, parentComponent.name, prefab.name);
						}
						else
						{
							COSystemBase.baseLog.ErrorFormat(prefab, "Dependency not available in {0}: {1}", parentPrefab.name, prefab.name);
						}
					}
					return false;
				}
				COSystemBase.baseLog.VerboseFormat(prefab, "Adding prefab '{0}'", prefab.name);
				List<ComponentBase> list = new List<ComponentBase>();
				prefab.GetComponents(list);
				HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
				for (int i = 0; i < list.Count; i++)
				{
					list[i].GetPrefabComponents(hashSet);
				}
				if (IsUnlockable(prefab))
				{
					hashSet.Add(ComponentType.ReadWrite<UnlockRequirement>());
					hashSet.Add(ComponentType.ReadWrite<Locked>());
					m_UnlockingLog.DebugFormat("Prefab locked: {0}", prefab);
				}
				hashSet.Add(ComponentType.ReadWrite<Created>());
				hashSet.Add(ComponentType.ReadWrite<Updated>());
				Entity entity = base.EntityManager.CreateEntity(PrefabUtils.ToArray(hashSet));
				PrefabData componentData = new PrefabData
				{
					m_Index = m_Prefabs.Count
				};
				base.EntityManager.SetComponentData(entity, componentData);
				PrefabID prefabID = prefab.GetPrefabID();
				if (m_PrefabIndices.ContainsKey(prefabID))
				{
					COSystemBase.baseLog.WarnFormat(prefab, "Duplicate prefab ID: {0}", prefabID);
				}
				else
				{
					m_PrefabIndices.Add(prefabID, m_Prefabs.Count);
				}
				if (prefab.TryGet<ObsoleteIdentifiers>(out var component) && component.m_PrefabIdentifiers != null)
				{
					for (int j = 0; j < component.m_PrefabIdentifiers.Length; j++)
					{
						PrefabIdentifierInfo prefabIdentifierInfo = component.m_PrefabIdentifiers[j];
						prefabID = new PrefabID(prefabIdentifierInfo.m_Type, prefabIdentifierInfo.m_Name);
						if (m_PrefabIndices.ContainsKey(prefabID))
						{
							COSystemBase.baseLog.WarnFormat(prefab, "Duplicate prefab ID: {0} ({1})", prefabID, (prefab.asset != null) ? ((object)prefab.asset) : ((object)prefab.name));
						}
						else
						{
							m_PrefabIndices.Add(prefabID, m_Prefabs.Count);
						}
					}
				}
				m_Prefabs.Add(prefab);
				m_Entities.Add(prefab, entity);
				return true;
			}
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.ErrorFormat(prefab, exception, "Error when adding prefab: {0}", prefab.name);
		}
		return false;
	}
```

- `public AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase unlocked) : System.Void`  

```csharp
public void AddUnlockRequirement(PrefabBase unlocker, PrefabBase[] unlocked)
	{
		if (IsUnlockable(unlocker))
		{
			Entity entity = GetEntity(unlocker);
			for (int i = 0; i < unlocked.Length; i++)
			{
				if (IsUnlockable(unlocked[i]))
				{
					GetBuffer<UnlockRequirement>(unlocked[i], isReadOnly: false).Add(new UnlockRequirement(entity, UnlockFlags.RequireAll));
				}
				else
				{
					COSystemBase.baseLog.WarnFormat(unlocked[i], "{0} is trying to add unlock requirement to non-unlockable prefab {1}", unlocker.name, unlocked[i].name);
				}
			}
		}
		else
		{
			COSystemBase.baseLog.WarnFormat(unlocker, "{0} is trying to add unlock requirements, but is non-unlockable", unlocker.name);
		}
	}
```

- `public AddUnlockRequirement(Game.Prefabs.PrefabBase unlocker, Game.Prefabs.PrefabBase[] unlocked) : System.Void`  

```csharp
public void AddUnlockRequirement(PrefabBase unlocker, PrefabBase[] unlocked)
	{
		if (IsUnlockable(unlocker))
		{
			Entity entity = GetEntity(unlocker);
			for (int i = 0; i < unlocked.Length; i++)
			{
				if (IsUnlockable(unlocked[i]))
				{
					GetBuffer<UnlockRequirement>(unlocked[i], isReadOnly: false).Add(new UnlockRequirement(entity, UnlockFlags.RequireAll));
				}
				else
				{
					COSystemBase.baseLog.WarnFormat(unlocked[i], "{0} is trying to add unlock requirement to non-unlockable prefab {1}", unlocker.name, unlocked[i].name);
				}
			}
		}
		else
		{
			COSystemBase.baseLog.WarnFormat(unlocker, "{0} is trying to add unlock requirements, but is non-unlockable", unlocker.name);
		}
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public DuplicatePrefab(Game.Prefabs.PrefabBase template, System.String name = null) : Game.Prefabs.PrefabBase`  

```csharp
public PrefabBase DuplicatePrefab(PrefabBase template, string name = null)
	{
		PrefabBase prefabBase = template.Clone(name);
		prefabBase.Remove<ObsoleteIdentifiers>();
		AddPrefab(prefabBase);
		return prefabBase;
	}
```

- `public GetAvailableContentPrefabs() : System.Collections.Generic.IEnumerable<Game.Prefabs.ContentPrefab>`  

```csharp
public IEnumerable<ContentPrefab> GetAvailableContentPrefabs()
	{
		return from entry in m_IsAvailable
			where entry.Value
			select entry.Key;
	}
```

- `public GetAvailablePrerequisitesNames() : System.String[]`  

```csharp
public string[] GetAvailablePrerequisitesNames()
	{
		string[] array = (from entry in m_IsAvailable
			where entry.Value
			select entry.Key.name).ToArray();
		if (array.Length == 0)
		{
			return null;
		}
		return array;
	}
```

- `public GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly) : Unity.Entities.DynamicBuffer<T>`  

```csharp
public Unity.Entities.DynamicBuffer<T> GetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly);
```

- `public GetComponentData<T>(Game.Prefabs.PrefabBase prefab) : T`  

```csharp
public T GetComponentData<T>(Game.Prefabs.PrefabBase prefab);
```

- `public GetEntity(Game.Prefabs.PrefabBase prefab) : Unity.Entities.Entity`  

```csharp
public Entity GetEntity(PrefabBase prefab)
	{
		return m_Entities[prefab];
	}
```

- `public GetLoadedObsoleteID(System.Int32 loadedIndex) : Game.Prefabs.PrefabID`  

```csharp
public PrefabID GetLoadedObsoleteID(int loadedIndex)
	{
		if (!m_LoadedObsoleteIDs.TryGetValue(loadedIndex, out var value))
		{
			value = new PrefabID("[Missing]", "[Missing]");
		}
		return value;
	}
```

- `public GetObsoleteID(Game.Prefabs.PrefabData prefabData) : Game.Prefabs.PrefabID`  

```csharp
public PrefabID GetObsoleteID(Entity entity)
	{
		return GetObsoleteID(base.EntityManager.GetComponentData<PrefabData>(entity));
	}
```

- `public GetObsoleteID(Unity.Entities.Entity entity) : Game.Prefabs.PrefabID`  

```csharp
public PrefabID GetObsoleteID(Entity entity)
	{
		return GetObsoleteID(base.EntityManager.GetComponentData<PrefabData>(entity));
	}
```

- `public GetPrefab<T>(Game.Prefabs.PrefabData prefabData) : T`  

```csharp
public T GetPrefab<T>(Game.Prefabs.PrefabData prefabData);
```

- `public GetPrefab<T>(Unity.Entities.Entity entity) : T`  

```csharp
public T GetPrefab<T>(Unity.Entities.Entity entity);
```

- `public GetPrefab<T>(Game.Prefabs.PrefabRef refData) : T`  

```csharp
public T GetPrefab<T>(Game.Prefabs.PrefabRef refData);
```

- `public GetPrefabName(Unity.Entities.Entity entity) : System.String`  

```csharp
public string GetPrefabName(Entity entity)
	{
		if (base.EntityManager.TryGetComponent<PrefabData>(entity, out var component))
		{
			if (component.m_Index >= 0)
			{
				return m_Prefabs[component.m_Index].name;
			}
			return GetObsoleteID(component).GetName();
		}
		return entity.ToString();
	}
```

- `public GetSingletonPrefab<T>(Unity.Entities.EntityQuery group) : T`  

```csharp
public T GetSingletonPrefab<T>(Unity.Entities.EntityQuery group);
```

- `public HasComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean HasComponent<T>(Game.Prefabs.PrefabBase prefab);
```

- `public HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean HasEnabledComponent<T>(Game.Prefabs.PrefabBase prefab);
```

- `public IsAvailable(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public bool IsAvailable(PrefabBase prefab)
	{
		if (prefab.TryGet<ContentPrerequisite>(out var component))
		{
			if (!m_IsAvailable.TryGetValue(component.m_ContentPrerequisite, out var value))
			{
				value = component.m_ContentPrerequisite.IsAvailable();
				m_IsAvailable.Add(component.m_ContentPrerequisite, value);
				this.onContentAvailabilityChanged?.Invoke(component.m_ContentPrerequisite);
			}
			return value;
		}
		return true;
	}
```

- `public IsUnlockable(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public bool IsUnlockable(PrefabBase prefab)
	{
		if (m_IsUnlockable.TryGetValue(prefab, out var value))
		{
			return value;
		}
		if (prefab is UnlockRequirementPrefab)
		{
			m_IsUnlockable.Add(prefab, value: true);
			return true;
		}
		List<PrefabBase> dependencies = new List<PrefabBase>();
		List<ComponentBase> components = new List<ComponentBase>();
		value = IsUnlockableImpl(prefab, dependencies, components);
		m_IsUnlockable.Add(prefab, value);
		return value;
	}
```

- `private IsUnlockableImpl(Game.Prefabs.PrefabBase prefab, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies, System.Collections.Generic.List<Game.Prefabs.ComponentBase> components) : System.Boolean`  

```csharp
private bool IsUnlockableImpl(PrefabBase prefab, List<PrefabBase> dependencies, List<ComponentBase> components)
	{
		int count = dependencies.Count;
		try
		{
			try
			{
				bool canIgnoreUnlockDependencies = prefab.canIgnoreUnlockDependencies;
				prefab.GetComponents(components);
				for (int i = 0; i < components.Count; i++)
				{
					ComponentBase componentBase = components[i];
					if (componentBase is UnlockableBase)
					{
						return true;
					}
					if (!canIgnoreUnlockDependencies || !componentBase.ignoreUnlockDependencies)
					{
						componentBase.GetDependencies(dependencies);
					}
				}
			}
			finally
			{
				components.Clear();
			}
			for (int j = count; j < dependencies.Count; j++)
			{
				PrefabBase prefabBase = dependencies[j];
				if (prefabBase == null)
				{
					continue;
				}
				if (m_IsUnlockable.TryGetValue(prefabBase, out var value))
				{
					if (value)
					{
						return true;
					}
					continue;
				}
				if (prefabBase is UnlockRequirementPrefab)
				{
					m_IsUnlockable.Add(prefabBase, value: true);
					return true;
				}
				value = IsUnlockableImpl(prefabBase, dependencies, components);
				m_IsUnlockable.Add(prefabBase, value);
				if (value)
				{
					return true;
				}
			}
			return false;
		}
		finally
		{
			dependencies.RemoveRange(count, dependencies.Count - count);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdateSystem = base.World.GetOrCreateSystemManaged<UpdateSystem>();
		m_Prefabs = new List<PrefabBase>();
		m_ObsoleteIDs = new List<ObsoleteData>();
		m_LoadedIndexData = new List<LoadedIndexData>();
		m_UpdateMap = new Dictionary<PrefabBase, Entity>();
		m_Entities = new Dictionary<PrefabBase, Entity>();
		m_IsUnlockable = new Dictionary<PrefabBase, bool>();
		m_IsAvailable = new Dictionary<ContentPrefab, bool>();
		m_LoadedObsoleteIDs = new Dictionary<int, PrefabID>();
		m_PrefabIndices = new Dictionary<PrefabID, int>();
		m_UnlockingLog = LogManager.GetLogger("Unlocking");
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool num = UpdatePrefabs();
		m_UpdateSystem.Update(SystemUpdatePhase.PrefabUpdate);
		if (num)
		{
			base.World.GetOrCreateSystemManaged<ReplacePrefabSystem>().FinalizeReplaces();
		}
	}
```

- `public RemoveComponent<T>(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
public System.Void RemoveComponent<T>(Game.Prefabs.PrefabBase prefab);
```

- `public RemovePrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public bool RemovePrefab(PrefabBase prefab)
	{
		if (prefab == null)
		{
			COSystemBase.baseLog.WarnFormat("Trying to remove null prefab");
			return false;
		}
		try
		{
			if (m_Entities.TryGetValue(prefab, out var value))
			{
				COSystemBase.baseLog.VerboseFormat(prefab, "Removing prefab '{0}'", prefab.name);
				base.EntityManager.AddComponent<Deleted>(value);
				PrefabData componentData = base.EntityManager.GetComponentData<PrefabData>(value);
				PrefabID prefabID = prefab.GetPrefabID();
				if (m_PrefabIndices.TryGetValue(prefabID, out var value2) && value2 == componentData.m_Index)
				{
					m_PrefabIndices.Remove(prefabID);
				}
				if (prefab.TryGet<ObsoleteIdentifiers>(out var component) && component.m_PrefabIdentifiers != null)
				{
					for (int i = 0; i < component.m_PrefabIdentifiers.Length; i++)
					{
						PrefabIdentifierInfo prefabIdentifierInfo = component.m_PrefabIdentifiers[i];
						prefabID = new PrefabID(prefabIdentifierInfo.m_Type, prefabIdentifierInfo.m_Name);
						if (m_PrefabIndices.TryGetValue(prefabID, out value2) && value2 == componentData.m_Index)
						{
							m_PrefabIndices.Remove(prefabID);
						}
					}
				}
				if (componentData.m_Index != m_Prefabs.Count - 1)
				{
					PrefabBase prefabBase = m_Prefabs[m_Prefabs.Count - 1];
					Entity entity = m_Entities[prefabBase];
					PrefabData componentData2 = base.EntityManager.GetComponentData<PrefabData>(entity);
					PrefabID prefabID2 = prefabBase.GetPrefabID();
					if (m_PrefabIndices.TryGetValue(prefabID2, out var value3) && value3 == componentData2.m_Index)
					{
						m_PrefabIndices[prefabID2] = componentData.m_Index;
					}
					if (prefabBase.TryGet<ObsoleteIdentifiers>(out var component2) && component2.m_PrefabIdentifiers != null)
					{
						for (int j = 0; j < component2.m_PrefabIdentifiers.Length; j++)
						{
							PrefabIdentifierInfo prefabIdentifierInfo2 = component2.m_PrefabIdentifiers[j];
							prefabID2 = new PrefabID(prefabIdentifierInfo2.m_Type, prefabIdentifierInfo2.m_Name);
							if (m_PrefabIndices.TryGetValue(prefabID2, out value3) && value3 == componentData2.m_Index)
							{
								m_PrefabIndices[prefabID2] = componentData.m_Index;
							}
						}
					}
					componentData2.m_Index = componentData.m_Index;
					base.EntityManager.SetComponentData(entity, componentData2);
					m_Prefabs[componentData.m_Index] = prefabBase;
				}
				componentData.m_Index = -1000000000;
				base.EntityManager.SetComponentData(value, componentData);
				m_Prefabs.RemoveAt(m_Prefabs.Count - 1);
				m_Entities.Remove(prefab);
				m_IsUnlockable.Remove(prefab);
				return true;
			}
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.ErrorFormat(prefab, exception, "Error when removing prefab: {0}", prefab.name);
		}
		return false;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_ObsoleteIDs.Clear();
		m_LoadedObsoleteIDs.Clear();
		m_LoadedIndexData.Clear();
	}
```

- `public TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer) : System.Boolean`  

```csharp
public System.Boolean TryGetBuffer<T>(Game.Prefabs.PrefabBase prefab, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
```

- `public TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component) : System.Boolean`  

```csharp
public System.Boolean TryGetComponentData<T>(Game.Prefabs.PrefabBase prefab, T& component);
```

- `public TryGetEntity(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public bool TryGetEntity(PrefabBase prefab, out Entity entity)
	{
		return m_Entities.TryGetValue(prefab, out entity);
	}
```

- `public TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabData prefabData, T& prefab);
```

- `public TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab<T>(Unity.Entities.Entity entity, T& prefab);
```

- `public TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetPrefab<T>(Game.Prefabs.PrefabRef refData, T& prefab);
```

- `public TryGetPrefab(Game.Prefabs.PrefabID id, Game.Prefabs.PrefabBase& prefab) : System.Boolean`  

```csharp
public bool TryGetPrefab(PrefabID id, out PrefabBase prefab)
	{
		if (m_PrefabIndices.TryGetValue(id, out var value))
		{
			prefab = m_Prefabs[value];
			return true;
		}
		prefab = null;
		return false;
	}
```

- `public TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab) : System.Boolean`  

```csharp
public System.Boolean TryGetSingletonPrefab<T>(Unity.Entities.EntityQuery group, T& prefab);
```

- `public UpdateAvailabilityCache() : System.Void`  

```csharp
public void UpdateAvailabilityCache()
	{
		foreach (KeyValuePair<ContentPrefab, bool> item in m_IsAvailable.ToList())
		{
			bool value = item.Value;
			bool flag = item.Key.IsAvailable();
			m_IsAvailable[item.Key] = flag;
			if (flag != value)
			{
				this.onContentAvailabilityChanged?.Invoke(item.Key);
			}
		}
	}
```

- `public UpdateLoadedIndices() : System.Void`  

```csharp
public void UpdateLoadedIndices()
	{
		int count = m_Prefabs.Count;
		for (int i = 0; i < count; i++)
		{
			PrefabBase prefab = m_Prefabs[i];
			base.EntityManager.GetBuffer<LoadedIndex>(GetEntity(prefab)).Clear();
		}
		int count2 = m_LoadedIndexData.Count;
		for (int j = 0; j < count2; j++)
		{
			LoadedIndexData loadedIndexData = m_LoadedIndexData[j];
			base.EntityManager.GetBuffer<LoadedIndex>(loadedIndexData.m_Entity).Add(new LoadedIndex
			{
				m_Index = loadedIndexData.m_Index
			});
		}
	}
```

- `public UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance = null) : System.Void`  

```csharp
public System.Void UpdatePrefab(Game.Prefabs.PrefabBase prefab, Unity.Entities.Entity sourceInstance);
```

- `private UpdatePrefabs() : System.Boolean`  

```csharp
private bool UpdatePrefabs()
	{
		if (m_UpdateMap.Count == 0)
		{
			return false;
		}
		try
		{
			foreach (KeyValuePair<PrefabBase, Entity> item in m_UpdateMap)
			{
				PrefabBase key = item.Key;
				Entity value = item.Value;
				try
				{
					if (m_Entities.TryGetValue(key, out var value2))
					{
						base.EntityManager.AddComponent<Deleted>(value2);
						List<ComponentBase> list = new List<ComponentBase>();
						key.GetComponents(list);
						HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
						for (int i = 0; i < list.Count; i++)
						{
							list[i].GetPrefabComponents(hashSet);
						}
						bool num = IsUnlockable(key);
						if (num)
						{
							hashSet.Add(ComponentType.ReadWrite<UnlockRequirement>());
							hashSet.Add(ComponentType.ReadWrite<Locked>());
						}
						hashSet.Add(ComponentType.ReadWrite<Created>());
						hashSet.Add(ComponentType.ReadWrite<Updated>());
						Entity entity = base.EntityManager.CreateEntity(PrefabUtils.ToArray(hashSet));
						base.EntityManager.SetComponentData(entity, base.EntityManager.GetComponentData<PrefabData>(value2));
						if (num && !base.EntityManager.HasEnabledComponent<Locked>(value2))
						{
							base.EntityManager.SetComponentEnabled<Locked>(entity, value: false);
						}
						m_Entities[key] = entity;
						base.World.GetOrCreateSystemManaged<ReplacePrefabSystem>().ReplacePrefab(value2, entity, value);
					}
				}
				catch (Exception exception)
				{
					COSystemBase.baseLog.ErrorFormat(key, exception, "Error when updating prefab: {0}", key.name);
				}
			}
		}
		finally
		{
			m_UpdateMap.Clear();
		}
		return true;
	}
```


## Events

- `onContentAvailabilityChanged` : `Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged`  

```csharp
public event Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged onContentAvailabilityChanged;
```


## Nested types

- `Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged`  
- `Game.Prefabs.PrefabSystem+ObsoleteData`  
- `Game.Prefabs.PrefabSystem+LoadedIndexData`  
- `Game.Prefabs.PrefabSystem+<>c`  

