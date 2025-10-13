# Game.UI.ImageSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ImageSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private static const System.String kPlaceholderIcon;
    private static const System.String kCitizenIcon;
    private static const System.String kTouristIcon;
    private static const System.String kCommuterIcon;
    private static const System.String kAnimalIcon;
    private static const System.String kPetIcon;
    private static const System.String kHealthcareIcon;
    private static const System.String kDeathcareIcon;
    private static const System.String kPoliceIcon;
    private static const System.String kGarbageIcon;
    private static const System.String kFireIcon;
    private static const System.String kPostIcon;
    private static const System.String kDeliveryIcon;

    public System.String placeholderIcon { get; }

    public ImageSystem();

    public System.String GetGroupIcon(Unity.Entities.Entity prefabEntity);
    public static System.String GetIcon(Game.Prefabs.PrefabBase prefab);
    public System.String GetIconOrGroupIcon(Unity.Entities.Entity prefabEntity);
    public System.String GetInstanceIcon(Unity.Entities.Entity instanceEntity);
    public System.String GetInstanceIcon(Unity.Entities.Entity instanceEntity, Unity.Entities.Entity prefabEntity);
    public System.String GetThumbnail(Unity.Entities.Entity prefabEntity);
    public static System.String GetThumbnail(Game.Prefabs.PrefabBase prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private static const System.String kPlaceholderIcon`  

```csharp
private static const System.String kPlaceholderIcon;
```

- `private static const System.String kCitizenIcon`  

```csharp
private static const System.String kCitizenIcon;
```

- `private static const System.String kTouristIcon`  

```csharp
private static const System.String kTouristIcon;
```

- `private static const System.String kCommuterIcon`  

```csharp
private static const System.String kCommuterIcon;
```

- `private static const System.String kAnimalIcon`  

```csharp
private static const System.String kAnimalIcon;
```

- `private static const System.String kPetIcon`  

```csharp
private static const System.String kPetIcon;
```

- `private static const System.String kHealthcareIcon`  

```csharp
private static const System.String kHealthcareIcon;
```

- `private static const System.String kDeathcareIcon`  

```csharp
private static const System.String kDeathcareIcon;
```

- `private static const System.String kPoliceIcon`  

```csharp
private static const System.String kPoliceIcon;
```

- `private static const System.String kGarbageIcon`  

```csharp
private static const System.String kGarbageIcon;
```

- `private static const System.String kFireIcon`  

```csharp
private static const System.String kFireIcon;
```

- `private static const System.String kPostIcon`  

```csharp
private static const System.String kPostIcon;
```

- `private static const System.String kDeliveryIcon`  

```csharp
private static const System.String kDeliveryIcon;
```


## Properties

- `public System.String placeholderIcon { get }`  

```csharp
public System.String placeholderIcon { get; }
```


## Constructors

- `public ImageSystem()`  

```csharp
[Preserve]
	public ImageSystem()
	{
	}
```


## Methods

- `public GetGroupIcon(Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
[CanBeNull]
	public string GetGroupIcon(Entity prefabEntity)
	{
		if (base.EntityManager.TryGetComponent<UIObjectData>(prefabEntity, out var component) && component.m_Group != Entity.Null && m_PrefabSystem.TryGetPrefab<PrefabBase>(component.m_Group, out var prefab))
		{
			return GetIcon(prefab);
		}
		return null;
	}
```

- `public static GetIcon(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
[CanBeNull]
	public static string GetIcon(PrefabBase prefab)
	{
		if (prefab.TryGet<UIObject>(out var component) && !string.IsNullOrEmpty(component.m_Icon))
		{
			return component.m_Icon;
		}
		return null;
	}
```

- `public GetIconOrGroupIcon(Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
[CanBeNull]
	public string GetIconOrGroupIcon(Entity prefabEntity)
	{
		if (m_PrefabSystem.TryGetPrefab<PrefabBase>(prefabEntity, out var prefab))
		{
			return GetIcon(prefab) ?? GetGroupIcon(prefabEntity);
		}
		return null;
	}
```

- `public GetInstanceIcon(Unity.Entities.Entity instanceEntity) : System.String`  

```csharp
[CanBeNull]
	public string GetInstanceIcon(Entity instanceEntity, Entity prefabEntity)
	{
		if (base.EntityManager.TryGetComponent<SpawnableBuildingData>(prefabEntity, out var component))
		{
			string iconOrGroupIcon = GetIconOrGroupIcon(component.m_ZonePrefab);
			if (iconOrGroupIcon != null)
			{
				return iconOrGroupIcon;
			}
		}
		string iconOrGroupIcon2 = GetIconOrGroupIcon(prefabEntity);
		if (iconOrGroupIcon2 != null)
		{
			return iconOrGroupIcon2;
		}
		if (base.EntityManager.HasComponent<Citizen>(instanceEntity) && base.EntityManager.TryGetComponent<HouseholdMember>(instanceEntity, out var component2))
		{
			if (base.EntityManager.HasChunkComponent<CommuterHousehold>(component2.m_Household))
			{
				return "Media/Game/Icons/Commuter.svg";
			}
			if (base.EntityManager.HasComponent<TouristHousehold>(component2.m_Household))
			{
				return "Media/Game/Icons/Tourist.svg";
			}
			return "Media/Game/Icons/Citizen.svg";
		}
		if (base.EntityManager.HasComponent<Animal>(instanceEntity))
		{
			return "Media/Game/Icons/Animal.svg";
		}
		if (base.EntityManager.HasComponent<HouseholdPet>(instanceEntity))
		{
			return "Media/Game/Icons/Pet.svg";
		}
		if (base.EntityManager.HasComponent<AmbulanceData>(prefabEntity))
		{
			return "Media/Game/Icons/Healthcare.svg";
		}
		if (base.EntityManager.HasComponent<PoliceCarData>(prefabEntity))
		{
			return "Media/Game/Icons/Police.svg";
		}
		if (base.EntityManager.HasComponent<FireEngineData>(prefabEntity))
		{
			return "Media/Game/Icons/FireSafety.svg";
		}
		if (base.EntityManager.HasComponent<DeliveryTruckData>(prefabEntity))
		{
			return "Media/Game/Icons/DeliveryVan.svg";
		}
		if (base.EntityManager.HasComponent<PostVanData>(prefabEntity))
		{
			return "Media/Game/Icons/PostService.svg";
		}
		if (base.EntityManager.HasComponent<HearseData>(prefabEntity))
		{
			return "Media/Game/Icons/Deathcare.svg";
		}
		if (base.EntityManager.HasComponent<GarbageTruckData>(prefabEntity))
		{
			return "Media/Game/Icons/Garbage.svg";
		}
		if (base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(instanceEntity) && base.EntityManager.TryGetComponent<Owner>(instanceEntity, out var component3) && base.EntityManager.TryGetComponent<PrefabRef>(component3.m_Owner, out var component4))
		{
			instanceEntity = component3.m_Owner;
			prefabEntity = component4.m_Prefab;
		}
		if (base.EntityManager.TryGetComponent<ServiceObjectData>(prefabEntity, out var component5))
		{
			string iconOrGroupIcon3 = GetIconOrGroupIcon(component5.m_Service);
			if (iconOrGroupIcon3 != null)
			{
				return iconOrGroupIcon3;
			}
		}
		if (base.EntityManager.TryGetBuffer(instanceEntity, isReadOnly: true, out DynamicBuffer<AggregateElement> buffer) && buffer.Length != 0 && base.EntityManager.TryGetComponent<PrefabRef>(buffer[0].m_Edge, out var component6))
		{
			string iconOrGroupIcon4 = GetIconOrGroupIcon(component6.m_Prefab);
			if (iconOrGroupIcon4 != null)
			{
				return iconOrGroupIcon4;
			}
		}
		if (base.EntityManager.TryGetComponent<Owner>(instanceEntity, out var component7) && base.EntityManager.TryGetComponent<PropertyRenter>(component7.m_Owner, out var component8) && base.EntityManager.TryGetComponent<PrefabRef>(component8.m_Property, out var component9))
		{
			SpawnableBuildingData component10;
			Entity prefabEntity2 = (base.EntityManager.TryGetComponent<SpawnableBuildingData>(component9.m_Prefab, out component10) ? component10.m_ZonePrefab : component9.m_Prefab);
			string iconOrGroupIcon5 = GetIconOrGroupIcon(prefabEntity2);
			if (iconOrGroupIcon5 != null)
			{
				return iconOrGroupIcon5;
			}
		}
		return null;
	}
```

- `public GetInstanceIcon(Unity.Entities.Entity instanceEntity, Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
[CanBeNull]
	public string GetInstanceIcon(Entity instanceEntity, Entity prefabEntity)
	{
		if (base.EntityManager.TryGetComponent<SpawnableBuildingData>(prefabEntity, out var component))
		{
			string iconOrGroupIcon = GetIconOrGroupIcon(component.m_ZonePrefab);
			if (iconOrGroupIcon != null)
			{
				return iconOrGroupIcon;
			}
		}
		string iconOrGroupIcon2 = GetIconOrGroupIcon(prefabEntity);
		if (iconOrGroupIcon2 != null)
		{
			return iconOrGroupIcon2;
		}
		if (base.EntityManager.HasComponent<Citizen>(instanceEntity) && base.EntityManager.TryGetComponent<HouseholdMember>(instanceEntity, out var component2))
		{
			if (base.EntityManager.HasChunkComponent<CommuterHousehold>(component2.m_Household))
			{
				return "Media/Game/Icons/Commuter.svg";
			}
			if (base.EntityManager.HasComponent<TouristHousehold>(component2.m_Household))
			{
				return "Media/Game/Icons/Tourist.svg";
			}
			return "Media/Game/Icons/Citizen.svg";
		}
		if (base.EntityManager.HasComponent<Animal>(instanceEntity))
		{
			return "Media/Game/Icons/Animal.svg";
		}
		if (base.EntityManager.HasComponent<HouseholdPet>(instanceEntity))
		{
			return "Media/Game/Icons/Pet.svg";
		}
		if (base.EntityManager.HasComponent<AmbulanceData>(prefabEntity))
		{
			return "Media/Game/Icons/Healthcare.svg";
		}
		if (base.EntityManager.HasComponent<PoliceCarData>(prefabEntity))
		{
			return "Media/Game/Icons/Police.svg";
		}
		if (base.EntityManager.HasComponent<FireEngineData>(prefabEntity))
		{
			return "Media/Game/Icons/FireSafety.svg";
		}
		if (base.EntityManager.HasComponent<DeliveryTruckData>(prefabEntity))
		{
			return "Media/Game/Icons/DeliveryVan.svg";
		}
		if (base.EntityManager.HasComponent<PostVanData>(prefabEntity))
		{
			return "Media/Game/Icons/PostService.svg";
		}
		if (base.EntityManager.HasComponent<HearseData>(prefabEntity))
		{
			return "Media/Game/Icons/Deathcare.svg";
		}
		if (base.EntityManager.HasComponent<GarbageTruckData>(prefabEntity))
		{
			return "Media/Game/Icons/Garbage.svg";
		}
		if (base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(instanceEntity) && base.EntityManager.TryGetComponent<Owner>(instanceEntity, out var component3) && base.EntityManager.TryGetComponent<PrefabRef>(component3.m_Owner, out var component4))
		{
			instanceEntity = component3.m_Owner;
			prefabEntity = component4.m_Prefab;
		}
		if (base.EntityManager.TryGetComponent<ServiceObjectData>(prefabEntity, out var component5))
		{
			string iconOrGroupIcon3 = GetIconOrGroupIcon(component5.m_Service);
			if (iconOrGroupIcon3 != null)
			{
				return iconOrGroupIcon3;
			}
		}
		if (base.EntityManager.TryGetBuffer(instanceEntity, isReadOnly: true, out DynamicBuffer<AggregateElement> buffer) && buffer.Length != 0 && base.EntityManager.TryGetComponent<PrefabRef>(buffer[0].m_Edge, out var component6))
		{
			string iconOrGroupIcon4 = GetIconOrGroupIcon(component6.m_Prefab);
			if (iconOrGroupIcon4 != null)
			{
				return iconOrGroupIcon4;
			}
		}
		if (base.EntityManager.TryGetComponent<Owner>(instanceEntity, out var component7) && base.EntityManager.TryGetComponent<PropertyRenter>(component7.m_Owner, out var component8) && base.EntityManager.TryGetComponent<PrefabRef>(component8.m_Property, out var component9))
		{
			SpawnableBuildingData component10;
			Entity prefabEntity2 = (base.EntityManager.TryGetComponent<SpawnableBuildingData>(component9.m_Prefab, out component10) ? component10.m_ZonePrefab : component9.m_Prefab);
			string iconOrGroupIcon5 = GetIconOrGroupIcon(prefabEntity2);
			if (iconOrGroupIcon5 != null)
			{
				return iconOrGroupIcon5;
			}
		}
		return null;
	}
```

- `public GetThumbnail(Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
[CanBeNull]
	public static string GetThumbnail(PrefabBase prefab)
	{
		string icon = GetIcon(prefab);
		if (icon != null)
		{
			return icon;
		}
		if (GameManager.instance.configuration.noThumbnails)
		{
			return "Media/Placeholder.svg";
		}
		string text = $"{prefab.thumbnailUrl}?width={128}&height={128}";
		COSystemBase.baseLog.VerboseFormat("GetThumbnail - {0}", text);
		return text;
	}
```

- `public static GetThumbnail(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
[CanBeNull]
	public static string GetThumbnail(PrefabBase prefab)
	{
		string icon = GetIcon(prefab);
		if (icon != null)
		{
			return icon;
		}
		if (GameManager.instance.configuration.noThumbnails)
		{
			return "Media/Placeholder.svg";
		}
		string text = $"{prefab.thumbnailUrl}?width={128}&height={128}";
		COSystemBase.baseLog.VerboseFormat("GetThumbnail - {0}", text);
		return text;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```


