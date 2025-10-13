# Game.UI.NameSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NameSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names;

    public NameSystem();

    public System.Void BindFamilyName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity household);
    public System.Void BindName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    public System.Void BindNameForVirtualKeyboard(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    public System.Void Deserialize<TReader>(TReader reader);
    private System.String GetBrandId(Unity.Entities.Entity building);
    private Game.UI.NameSystem+Name GetCitizenName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    public System.String GetDebugName(Unity.Entities.Entity entity);
    private Game.UI.NameSystem+Name GetFamilyName(Unity.Entities.Entity household);
    private System.String GetGenderedLastNameId(Unity.Entities.Entity household, System.Boolean male);
    private System.String GetId(Unity.Entities.Entity entity, System.Boolean useRandomLocalization);
    private Game.UI.NameSystem+Name GetMarkerTransportStopName(Unity.Entities.Entity stop);
    public Game.UI.NameSystem+Name GetName(Unity.Entities.Entity entity, System.Boolean omitBrand);
    public Game.UI.NameSystem+Name GetNameForVirtualKeyboard(Unity.Entities.Entity entity);
    public System.String GetRenderedLabelName(Unity.Entities.Entity entity);
    private Game.UI.NameSystem+Name GetResidentName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private Game.UI.NameSystem+Name GetRouteName(Unity.Entities.Entity route, Unity.Entities.Entity prefab);
    private Game.UI.NameSystem+Name GetSpawnableBuildingName(Unity.Entities.Entity building, Unity.Entities.Entity zone, System.Boolean omitBrand);
    private Game.UI.NameSystem+Name GetStaticTransportStopName(Unity.Entities.Entity stop);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetCustomName(Unity.Entities.Entity entity, System.String name);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Boolean TryGetCustomName(Unity.Entities.Entity entity, System.String& customName);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names;
```


## Constructors

- `public NameSystem()`  

```csharp
[Preserve]
	public NameSystem()
	{
	}
```


## Methods

- `public BindFamilyName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity household) : System.Void`  

```csharp
public void BindFamilyName(IJsonWriter writer, Entity household)
	{
		writer.Write(GetFamilyName(household));
	}
```

- `public BindName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public void BindName(IJsonWriter writer, Entity entity)
	{
		writer.Write(GetName(entity));
	}
```

- `public BindNameForVirtualKeyboard(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public void BindNameForVirtualKeyboard(IJsonWriter writer, Entity entity)
	{
		writer.Write(GetNameForVirtualKeyboard(entity));
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private GetBrandId(Unity.Entities.Entity building) : System.String`  

```csharp
private string GetBrandId(Entity building)
	{
		DynamicBuffer<Renter> buffer = base.EntityManager.GetBuffer<Renter>(building, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			if (base.EntityManager.TryGetComponent<CompanyData>(buffer[i].m_Renter, out var component))
			{
				return GetId(component.m_Brand);
			}
		}
		return null;
	}
```

- `private GetCitizenName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  

```csharp
private Name GetCitizenName(Entity entity, Entity prefab)
	{
		string id = GetId(entity);
		HouseholdMember componentData = base.EntityManager.GetComponentData<HouseholdMember>(entity);
		Citizen component;
		bool male = base.EntityManager.TryGetComponent<Citizen>(entity, out component) && (component.m_State & CitizenFlags.Male) != 0;
		string genderedLastNameId = GetGenderedLastNameId(componentData.m_Household, male);
		return Name.FormattedName("Assets.CITIZEN_NAME_FORMAT", "FIRST_NAME", id, "LAST_NAME", genderedLastNameId);
	}
```

- `public GetDebugName(Unity.Entities.Entity entity) : System.String`  

```csharp
public string GetDebugName(Entity entity)
	{
		string arg = null;
		if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			arg = ((!base.EntityManager.HasComponent<PrefabData>(component.m_Prefab)) ? "(invalid prefab)" : ((!m_PrefabSystem.TryGetPrefab<PrefabBase>(component.m_Prefab, out var prefab)) ? m_PrefabSystem.GetObsoleteID(component.m_Prefab).GetName() : prefab.name));
		}
		return $"{arg} {entity.Index}";
	}
```

- `private GetFamilyName(Unity.Entities.Entity household) : Game.UI.NameSystem+Name`  

```csharp
private Name GetFamilyName(Entity household)
	{
		if (TryGetCustomName(household, out var customName))
		{
			return Name.CustomName(customName);
		}
		int num = 0;
		DynamicBuffer<HouseholdCitizen> buffer = base.EntityManager.GetBuffer<HouseholdCitizen>(household);
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity entity = buffer[i];
			if (base.EntityManager.TryGetComponent<Citizen>(entity, out var component) && (component.m_State & CitizenFlags.Male) != CitizenFlags.None)
			{
				num++;
			}
		}
		return Name.LocalizedName(GetGenderedLastNameId(household, num > 1));
	}
```

- `private GetGenderedLastNameId(Unity.Entities.Entity household, System.Boolean male) : System.String`  

```csharp
private string GetGenderedLastNameId(Entity household, bool male)
	{
		if (household == Entity.Null)
		{
			return null;
		}
		if (base.EntityManager.TryGetComponent<PrefabRef>(household, out var component) && m_PrefabSystem.GetPrefab<PrefabBase>(component).TryGet<RandomGenderedLocalization>(out var component2))
		{
			string text = (male ? component2.m_MaleID : component2.m_FemaleID);
			if (base.EntityManager.TryGetBuffer(household, isReadOnly: true, out DynamicBuffer<RandomLocalizationIndex> buffer) && buffer.Length > 0)
			{
				return LocalizationUtils.AppendIndex(text, buffer[0]);
			}
			return text;
		}
		return GetId(household);
	}
```

- `private GetId(Unity.Entities.Entity entity, System.Boolean useRandomLocalization = True) : System.String`  

```csharp
private string GetId(Entity entity, bool useRandomLocalization = true)
	{
		if (entity == Entity.Null)
		{
			return null;
		}
		Entity entity2 = Entity.Null;
		if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			entity2 = component.m_Prefab;
		}
		if (!base.EntityManager.HasComponent<SignatureBuildingData>(entity2) && base.EntityManager.TryGetComponent<SpawnableBuildingData>(entity2, out var component2))
		{
			entity2 = component2.m_ZonePrefab;
		}
		if (base.EntityManager.HasComponent<ChirperAccountData>(entity) || base.EntityManager.HasComponent<BrandData>(entity))
		{
			entity2 = entity;
		}
		if (entity2 != Entity.Null)
		{
			if (m_PrefabSystem.TryGetPrefab<PrefabBase>(entity2, out var prefab))
			{
				if (prefab.TryGet<Game.Prefabs.Localization>(out var component3))
				{
					if (useRandomLocalization && component3 is RandomLocalization && base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<RandomLocalizationIndex> buffer) && buffer.Length > 0)
					{
						return LocalizationUtils.AppendIndex(component3.m_LocalizationID, buffer[0]);
					}
					return component3.m_LocalizationID;
				}
				m_PrefabUISystem.GetTitleAndDescription(entity2, out var titleId, out var _);
				return titleId;
			}
			return m_PrefabSystem.GetObsoleteID(entity2).GetName();
		}
		return string.Empty;
	}
```

- `private GetMarkerTransportStopName(Unity.Entities.Entity stop) : Game.UI.NameSystem+Name`  

```csharp
private Name GetMarkerTransportStopName(Entity stop)
	{
		Entity entity = stop;
		for (int i = 0; i < 8; i++)
		{
			if (!base.EntityManager.TryGetComponent<Owner>(entity, out var component))
			{
				break;
			}
			entity = component.m_Owner;
		}
		return Name.LocalizedName(GetId(entity));
	}
```

- `public GetName(Unity.Entities.Entity entity, System.Boolean omitBrand = False) : Game.UI.NameSystem+Name`  

```csharp
public Name GetName(Entity entity, bool omitBrand = false)
	{
		Entity entity2 = Entity.Null;
		if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			entity2 = component.m_Prefab;
		}
		if (base.EntityManager.TryGetComponent<Controller>(entity, out var component2))
		{
			entity = component2.m_Controller;
		}
		if (TryGetCustomName(entity, out var customName))
		{
			return Name.CustomName(customName);
		}
		if (base.EntityManager.TryGetComponent<CompanyData>(entity, out var component3))
		{
			string id = GetId(component3.m_Brand);
			if (id == null)
			{
				return Name.CustomName(m_PrefabSystem.GetPrefab<PrefabBase>(entity2).name + " brand is null!");
			}
			return Name.LocalizedName(id);
		}
		if (entity2 != Entity.Null && !base.EntityManager.HasComponent<SignatureBuildingData>(entity2) && base.EntityManager.TryGetComponent<SpawnableBuildingData>(entity2, out var component4))
		{
			return GetSpawnableBuildingName(entity, component4.m_ZonePrefab, omitBrand);
		}
		if (base.EntityManager.HasComponent<Game.Routes.TransportStop>(entity) && !base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(entity))
		{
			if (base.EntityManager.HasComponent<Marker>(entity))
			{
				return GetMarkerTransportStopName(entity);
			}
			return GetStaticTransportStopName(entity);
		}
		if (entity2 != Entity.Null && base.EntityManager.HasComponent<TransportLine>(entity))
		{
			return GetRouteName(entity, entity2);
		}
		if (entity2 != Entity.Null && base.EntityManager.HasComponent<Citizen>(entity))
		{
			return GetCitizenName(entity, entity2);
		}
		if (entity2 != Entity.Null && base.EntityManager.HasComponent<Game.Creatures.Resident>(entity))
		{
			return GetResidentName(entity, entity2);
		}
		if (base.EntityManager.HasComponent<Game.Events.TrafficAccident>(entity))
		{
			return Name.LocalizedName("SelectedInfoPanel.TRAFFIC_ACCIDENT");
		}
		return Name.LocalizedName(GetId(entity));
	}
```

- `public GetNameForVirtualKeyboard(Unity.Entities.Entity entity) : Game.UI.NameSystem+Name`  

```csharp
public Name GetNameForVirtualKeyboard(Entity entity)
	{
		Entity entity2 = Entity.Null;
		if (base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			entity2 = component.m_Prefab;
		}
		if (entity2 != Entity.Null && base.EntityManager.HasComponent<TransportLine>(entity))
		{
			RoutePrefab prefab = m_PrefabSystem.GetPrefab<RoutePrefab>(entity2);
			return Name.LocalizedName(prefab.m_LocaleID + "[" + prefab.name + "]");
		}
		if (base.EntityManager.TryGetComponent<Controller>(entity, out var component2))
		{
			entity = component2.m_Controller;
		}
		return Name.LocalizedName(GetId(entity, useRandomLocalization: false));
	}
```

- `public GetRenderedLabelName(Unity.Entities.Entity entity) : System.String`  

```csharp
public string GetRenderedLabelName(Entity entity)
	{
		if (TryGetCustomName(entity, out var customName))
		{
			return customName;
		}
		string id = GetId(entity);
		if (!GameManager.instance.localizationManager.activeDictionary.TryGetValue(id, out var value))
		{
			return id;
		}
		return value;
	}
```

- `private GetResidentName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  

```csharp
private Name GetResidentName(Entity entity, Entity prefab)
	{
		base.EntityManager.TryGetComponent<PseudoRandomSeed>(entity, out var component);
		base.EntityManager.TryGetComponent<CreatureData>(prefab, out var component2);
		Random random = component.GetRandom(PseudoRandomSeed.kDummyName);
		bool flag = false;
		if (component2.m_Gender == GenderMask.Male)
		{
			flag = true;
		}
		else if (component2.m_Gender != GenderMask.Female)
		{
			flag = random.NextBool();
		}
		string text = (flag ? "Assets.CITIZEN_NAME_MALE" : "Assets.CITIZEN_NAME_FEMALE");
		string text2 = (flag ? "Assets.CITIZEN_SURNAME_MALE" : "Assets.CITIZEN_SURNAME_FEMALE");
		PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(prefab);
		int localizationIndexCount = RandomLocalization.GetLocalizationIndexCount(prefab2, text);
		int localizationIndexCount2 = RandomLocalization.GetLocalizationIndexCount(prefab2, text2);
		string text3 = LocalizationUtils.AppendIndex(text, new RandomLocalizationIndex(random.NextInt(localizationIndexCount)));
		string text4 = LocalizationUtils.AppendIndex(text2, new RandomLocalizationIndex(random.NextInt(localizationIndexCount2)));
		return Name.FormattedName("Assets.CITIZEN_NAME_FORMAT", "FIRST_NAME", text3, "LAST_NAME", text4);
	}
```

- `private GetRouteName(Unity.Entities.Entity route, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  

```csharp
private Name GetRouteName(Entity route, Entity prefab)
	{
		RoutePrefab prefab2 = m_PrefabSystem.GetPrefab<RoutePrefab>(prefab);
		RouteNumber componentData = base.EntityManager.GetComponentData<RouteNumber>(route);
		return Name.FormattedName(prefab2.m_LocaleID + "[" + prefab2.name + "]", "NUMBER", componentData.m_Number.ToString());
	}
```

- `private GetSpawnableBuildingName(Unity.Entities.Entity building, Unity.Entities.Entity zone, System.Boolean omitBrand = False) : Game.UI.NameSystem+Name`  

```csharp
private Name GetSpawnableBuildingName(Entity building, Entity zone, bool omitBrand = false)
	{
		BuildingUtils.GetAddress(base.EntityManager, building, out var road, out var number);
		if (!TryGetCustomName(road, out var customName))
		{
			customName = GetId(road);
		}
		if (customName == null)
		{
			return Name.LocalizedName(GetId(building));
		}
		if (!omitBrand && base.EntityManager.TryGetComponent<ZoneData>(zone, out var component) && component.m_AreaType != AreaType.Residential)
		{
			string brandId = GetBrandId(building);
			if (brandId != null)
			{
				return Name.FormattedName("Assets.NAMED_ADDRESS_NAME_FORMAT", "NAME", brandId, "ROAD", customName, "NUMBER", number.ToString());
			}
		}
		return Name.FormattedName("Assets.ADDRESS_NAME_FORMAT", "ROAD", customName, "NUMBER", number.ToString());
	}
```

- `private GetStaticTransportStopName(Unity.Entities.Entity stop) : Game.UI.NameSystem+Name`  

```csharp
private Name GetStaticTransportStopName(Entity stop)
	{
		BuildingUtils.GetAddress(base.EntityManager, stop, out var road, out var number);
		if (!TryGetCustomName(road, out var customName))
		{
			customName = GetId(road);
		}
		if (customName == null)
		{
			return Name.LocalizedName(GetId(stop));
		}
		return Name.FormattedName("Assets.ADDRESS_NAME_FORMAT", "ROAD", customName, "NUMBER", number.ToString());
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_DeletedQuery = GetEntityQuery(ComponentType.ReadOnly<CustomName>(), ComponentType.ReadOnly<Deleted>());
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_Names = new Dictionary<Entity, string>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_DeletedQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Entity> nativeArray = m_DeletedQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (m_Names.ContainsKey(nativeArray[i]))
				{
					m_Names.Remove(nativeArray[i]);
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetCustomName(Unity.Entities.Entity entity, System.String name) : System.Void`  

```csharp
public void SetCustomName(Entity entity, string name)
	{
		if (entity == Entity.Null)
		{
			return;
		}
		if (base.EntityManager.TryGetComponent<Controller>(entity, out var component))
		{
			entity = component.m_Controller;
		}
		if (name == string.Empty || string.IsNullOrWhiteSpace(name))
		{
			if (m_Names.ContainsKey(entity))
			{
				EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
				entityCommandBuffer.RemoveComponent<CustomName>(entity);
				entityCommandBuffer.AddComponent<BatchesUpdated>(entity);
				m_Names.Remove(entity);
			}
		}
		else
		{
			m_Names[entity] = name;
			EntityCommandBuffer entityCommandBuffer2 = m_EndFrameBarrier.CreateCommandBuffer();
			entityCommandBuffer2.AddComponent<CustomName>(entity);
			entityCommandBuffer2.AddComponent<BatchesUpdated>(entity);
		}
	}
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_Names.Clear();
	}
```

- `public TryGetCustomName(Unity.Entities.Entity entity, System.String& customName) : System.Boolean`  

```csharp
public bool TryGetCustomName(Entity entity, out string customName)
	{
		return m_Names.TryGetValue(entity, out customName);
	}
```


## Nested types

- `Game.UI.NameSystem+NameType`  
- `Game.UI.NameSystem+Name`  

