# Game.UI.InGame.MilestoneUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Simulation.IXPMessageHandler`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MilestoneUISystem : Game.UI.UISystemBase, Game.Simulation.IXPMessageHandler
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.IXPSystem m_XPSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.IMilestoneSystem m_XpMilestoneSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tutorials.TutorialSystem m_TutorialSystem;
    private Unity.Entities.EntityQuery m_MilestoneLevelQuery;
    private Unity.Entities.EntityQuery m_MilestoneQuery;
    private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
    private Unity.Entities.EntityQuery m_ModifiedMilestoneQuery;
    private Unity.Entities.EntityQuery m_MilestoneReachedEventQuery;
    private Unity.Entities.EntityQuery m_UnlockableAssetQuery;
    private Unity.Entities.EntityQuery m_UnlockableZoneQuery;
    private Unity.Entities.EntityQuery m_DevTreeNodeQuery;
    private Unity.Entities.EntityQuery m_UnlockableFeatureQuery;
    private Unity.Entities.EntityQuery m_UnlockablePolicyQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MaxMilestoneReachedBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneXPBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_NextMilestoneXPBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalXPBinding;
    private Colossal.UI.Binding.RawEventBinding m_XpMessageAddedBinding;
    private Colossal.UI.Binding.RawValueBinding m_MilestonesBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_UnlockedMilestoneBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneUnlocksBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockDetailsBinding;
    private static const System.String kGroup;

    public MilestoneUISystem();

    private System.Void <OnCreate>b__30_0();
    public System.Void AddMessage(Game.Simulation.XPMessage message);
    private System.Void BindAsset(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.MilestoneUISystem+AssetInfo asset, Game.Prefabs.PrefabBase assetPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> assetThemes);
    private System.Void BindAssetUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetEntity, System.Boolean locked);
    private System.Void BindFeatureUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity featureEntity, System.Boolean locked);
    private System.Void BindMilestoneDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestone);
    private System.Void BindMilestones(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindMilestoneUnlocks(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestoneEntity);
    private System.Void BindPolicyUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity policyEntity, System.Boolean locked);
    private System.Void BindServiceUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity, System.Boolean locked);
    private System.Void BindUnlockDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity unlockEntity);
    private System.Void FilterAndSortAssets(Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> result, Unity.Entities.Entity serviceEntity, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets);
    private Unity.Collections.NativeList<Unity.Entities.Entity> FilterUnlockedPrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabs, Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
    private System.Int32 GetAchievedMilestone();
    private System.Int32 GetAchievedMilestoneXP();
    private System.Int32 GetMilestoneIndex(Unity.Entities.Entity milestoneEntity);
    private System.Int32 GetNextMilestoneXP();
    private Unity.Collections.NativeArray<Game.UI.InGame.MilestoneUISystem+ComparableMilestone> GetSortedMilestones(Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedPolicies(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+ServiceInfo> GetSortedServices(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedDevTreeServices, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets, Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedUnlockedFeatures(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> GetSortedZones(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedZones, Unity.Collections.Allocator allocator);
    private System.Void GetThemes(Unity.Collections.NativeList<Unity.Entities.Entity> result, Unity.Entities.Entity assetEntity);
    private System.Int32 GetTotalXP();
    private Unity.Collections.NativeList<Unity.Entities.Entity> GetUnlockedAssets(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Unity.Entities.Entity> GetUnlockedDevTreeServices(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Unity.Entities.Entity> GetUnlockedZones(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
    private System.Boolean HasDevTree(Unity.Entities.Entity serviceEntity);
    private System.Boolean IsMaxMilestoneReached();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void PublishReachedMilestones();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.IXPSystem m_XPSystem`  

```csharp
private Game.Simulation.IXPSystem m_XPSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.IMilestoneSystem m_XpMilestoneSystem`  

```csharp
private Game.Simulation.IMilestoneSystem m_XpMilestoneSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tutorials.TutorialSystem m_TutorialSystem`  

```csharp
private Game.Tutorials.TutorialSystem m_TutorialSystem;
```

- `private Unity.Entities.EntityQuery m_MilestoneLevelQuery`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneLevelQuery;
```

- `private Unity.Entities.EntityQuery m_MilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_LockedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedMilestoneQuery;
```

- `private Unity.Entities.EntityQuery m_MilestoneReachedEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_MilestoneReachedEventQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockableAssetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockableAssetQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockableZoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockableZoneQuery;
```

- `private Unity.Entities.EntityQuery m_DevTreeNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_DevTreeNodeQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockableFeatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockableFeatureQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockablePolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockablePolicyQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MaxMilestoneReachedBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MaxMilestoneReachedBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneXPBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneXPBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_NextMilestoneXPBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_NextMilestoneXPBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalXPBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalXPBinding;
```

- `private Colossal.UI.Binding.RawEventBinding m_XpMessageAddedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_XpMessageAddedBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_MilestonesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_MilestonesBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_UnlockedMilestoneBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_UnlockedMilestoneBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneUnlocksBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneUnlocksBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockDetailsBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public MilestoneUISystem()`  

```csharp
[Preserve]
	public MilestoneUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__30_0() : System.Void`  

```csharp
private System.Void <OnCreate>b__30_0();
```

- `public AddMessage(Game.Simulation.XPMessage message) : System.Void`  

```csharp
public void AddMessage(XPMessage message)
	{
		if (m_XpMessageAddedBinding.active)
		{
			IJsonWriter jsonWriter = m_XpMessageAddedBinding.EventBegin();
			jsonWriter.TypeBegin("milestone.XPMessage");
			jsonWriter.PropertyName("amount");
			jsonWriter.Write(message.amount);
			jsonWriter.PropertyName("reason");
			jsonWriter.Write(Enum.GetName(typeof(XPReason), message.reason));
			jsonWriter.TypeEnd();
			m_XpMessageAddedBinding.EventEnd();
		}
	}
```

- `private BindAsset(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.MilestoneUISystem+AssetInfo asset, Game.Prefabs.PrefabBase assetPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> assetThemes) : System.Void`  

```csharp
private void BindAsset(IJsonWriter writer, AssetInfo asset, PrefabBase assetPrefab, NativeList<Entity> assetThemes)
	{
		writer.TypeBegin("milestone.Asset");
		writer.PropertyName("entity");
		writer.Write(asset.m_Entity);
		writer.PropertyName("name");
		writer.Write(assetPrefab.name);
		writer.PropertyName("icon");
		writer.Write(ImageSystem.GetThumbnail(assetPrefab) ?? m_ImageSystem.placeholderIcon);
		writer.PropertyName("themes");
		GetThemes(assetThemes, asset.m_Entity);
		writer.ArrayBegin(assetThemes.Length);
		for (int i = 0; i < assetThemes.Length; i++)
		{
			writer.Write(assetThemes[i]);
		}
		writer.ArrayEnd();
		writer.TypeEnd();
	}
```

- `private BindAssetUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetEntity, System.Boolean locked) : System.Void`  

```csharp
private void BindAssetUnlock(IJsonWriter writer, Entity assetEntity, bool locked)
	{
		PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(assetEntity);
		writer.TypeBegin("milestone.UnlockDetails");
		writer.PropertyName("entity");
		writer.Write(assetEntity);
		writer.PropertyName("icon");
		writer.Write(ImageSystem.GetThumbnail(prefab) ?? m_ImageSystem.placeholderIcon);
		writer.PropertyName("titleId");
		writer.Write("Assets.NAME[" + prefab.name + "]");
		writer.PropertyName("descriptionId");
		writer.Write("Assets.DESCRIPTION[" + prefab.name + "]");
		writer.PropertyName("locked");
		writer.Write(locked);
		writer.PropertyName("hasDevTree");
		writer.Write(value: false);
		writer.TypeEnd();
	}
```

- `private BindFeatureUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity featureEntity, System.Boolean locked) : System.Void`  

```csharp
private void BindFeatureUnlock(IJsonWriter writer, Entity featureEntity, bool locked)
	{
		FeaturePrefab prefab = m_PrefabSystem.GetPrefab<FeaturePrefab>(featureEntity);
		UIObject component = prefab.GetComponent<UIObject>();
		writer.TypeBegin("milestone.UnlockDetails");
		writer.PropertyName("entity");
		writer.Write(featureEntity);
		writer.PropertyName("icon");
		writer.Write(component.m_Icon);
		writer.PropertyName("titleId");
		writer.Write("Assets.NAME[" + prefab.name + "]");
		writer.PropertyName("descriptionId");
		writer.Write("Assets.DESCRIPTION[" + prefab.name + "]");
		writer.PropertyName("locked");
		writer.Write(locked);
		writer.PropertyName("hasDevTree");
		writer.Write(value: false);
		writer.TypeEnd();
	}
```

- `private BindMilestoneDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestone) : System.Void`  

```csharp
private void BindMilestoneDetails(IJsonWriter writer, Entity milestone)
	{
		if (milestone != Entity.Null && base.EntityManager.TryGetComponent<MilestoneData>(milestone, out var component))
		{
			bool value = base.EntityManager.HasEnabledComponent<Locked>(milestone);
			writer.TypeBegin("milestone.MilestoneDetails");
			writer.PropertyName("entity");
			writer.Write(milestone);
			writer.PropertyName("index");
			writer.Write(component.m_Index);
			writer.PropertyName("xpRequirement");
			writer.Write(component.m_XpRequried);
			writer.PropertyName("reward");
			writer.Write(component.m_Reward);
			writer.PropertyName("devTreePoints");
			writer.Write(component.m_DevTreePoints);
			writer.PropertyName("mapTiles");
			writer.Write((!m_CityConfigurationSystem.unlockMapTiles) ? component.m_MapTiles : 0);
			writer.PropertyName("loanLimit");
			writer.Write(component.m_LoanLimit);
			MilestonePrefab prefab = m_PrefabSystem.GetPrefab<MilestonePrefab>(milestone);
			writer.PropertyName("image");
			writer.Write(prefab.m_Image);
			writer.PropertyName("backgroundColor");
			writer.Write(prefab.m_BackgroundColor);
			writer.PropertyName("accentColor");
			writer.Write(prefab.m_AccentColor);
			writer.PropertyName("textColor");
			writer.Write(prefab.m_TextColor);
			writer.PropertyName("locked");
			writer.Write(value);
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `private BindMilestones(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindMilestones(IJsonWriter writer)
	{
		NativeArray<ComparableMilestone> sortedMilestones = GetSortedMilestones(Allocator.TempJob);
		writer.ArrayBegin(sortedMilestones.Length);
		for (int i = 0; i < sortedMilestones.Length; i++)
		{
			Entity entity = sortedMilestones[i].m_Entity;
			MilestoneData milestoneData = sortedMilestones[i].m_Data;
			writer.TypeBegin("milestone.Milestone");
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.PropertyName("index");
			writer.Write(milestoneData.m_Index);
			writer.PropertyName("major");
			writer.Write(milestoneData.m_Major);
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(entity));
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		sortedMilestones.Dispose();
	}
```

- `private BindMilestoneUnlocks(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestoneEntity) : System.Void`  

```csharp
private void BindMilestoneUnlocks(IJsonWriter writer, Entity milestoneEntity)
	{
		NativeList<Entity> unlockedDevTreeServices = GetUnlockedDevTreeServices(milestoneEntity, Allocator.TempJob);
		NativeList<Entity> unlockedZones = GetUnlockedZones(milestoneEntity, Allocator.TempJob);
		NativeList<Entity> unlockedAssets = GetUnlockedAssets(milestoneEntity, Allocator.TempJob);
		NativeList<UIObjectInfo> sortedUnlockedFeatures = GetSortedUnlockedFeatures(milestoneEntity, Allocator.TempJob);
		NativeList<ServiceInfo> sortedServices = GetSortedServices(unlockedDevTreeServices, unlockedAssets, Allocator.TempJob);
		NativeList<AssetInfo> sortedZones = GetSortedZones(unlockedZones, Allocator.TempJob);
		NativeList<UIObjectInfo> sortedPolicies = GetSortedPolicies(milestoneEntity, Allocator.TempJob);
		NativeList<AssetInfo> result = new NativeList<AssetInfo>(20, Allocator.TempJob);
		NativeList<Entity> assetThemes = new NativeList<Entity>(10, Allocator.TempJob);
		writer.ArrayBegin(sortedUnlockedFeatures.Length + sortedZones.Length + sortedServices.Length + sortedPolicies.Length);
		for (int i = 0; i < sortedUnlockedFeatures.Length; i++)
		{
			UIObjectInfo uIObjectInfo = sortedUnlockedFeatures[i];
			FeaturePrefab prefab = m_PrefabSystem.GetPrefab<FeaturePrefab>(uIObjectInfo.prefabData);
			UIObject component = prefab.GetComponent<UIObject>();
			writer.TypeBegin("milestone.Feature");
			writer.PropertyName("entity");
			writer.Write(uIObjectInfo.entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("icon");
			writer.Write(component.m_Icon);
			writer.TypeEnd();
		}
		for (int j = 0; j < sortedZones.Length; j++)
		{
			AssetInfo asset = sortedZones[j];
			PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(asset.m_PrefabData);
			BindAsset(writer, asset, prefab2, assetThemes);
		}
		for (int k = 0; k < sortedServices.Length; k++)
		{
			ServiceInfo serviceInfo = sortedServices[k];
			ServicePrefab prefab3 = m_PrefabSystem.GetPrefab<ServicePrefab>(serviceInfo.m_PrefabData);
			UIObject component2 = prefab3.GetComponent<UIObject>();
			FilterAndSortAssets(result, serviceInfo.m_Entity, unlockedAssets);
			writer.TypeBegin("milestone.Service");
			writer.PropertyName("entity");
			writer.Write(serviceInfo.m_Entity);
			writer.PropertyName("name");
			writer.Write(prefab3.name);
			writer.PropertyName("icon");
			writer.Write(component2.m_Icon);
			writer.PropertyName("devTreeUnlocked");
			writer.Write(serviceInfo.m_DevTreeUnlocked);
			writer.PropertyName("assets");
			writer.ArrayBegin(result.Length);
			for (int l = 0; l < result.Length; l++)
			{
				AssetInfo asset2 = result[l];
				PrefabBase prefab4 = m_PrefabSystem.GetPrefab<PrefabBase>(asset2.m_PrefabData);
				BindAsset(writer, asset2, prefab4, assetThemes);
			}
			writer.ArrayEnd();
			writer.TypeEnd();
		}
		for (int m = 0; m < sortedPolicies.Length; m++)
		{
			UIObjectInfo uIObjectInfo2 = sortedPolicies[m];
			PolicyPrefab prefab5 = m_PrefabSystem.GetPrefab<PolicyPrefab>(uIObjectInfo2.prefabData);
			UIObject component3 = prefab5.GetComponent<UIObject>();
			writer.TypeBegin("milestone.Policy");
			writer.PropertyName("entity");
			writer.Write(uIObjectInfo2.entity);
			writer.PropertyName("name");
			writer.Write(prefab5.name);
			writer.PropertyName("icon");
			writer.Write(component3.m_Icon);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		unlockedDevTreeServices.Dispose();
		unlockedAssets.Dispose();
		unlockedZones.Dispose();
		sortedUnlockedFeatures.Dispose();
		sortedServices.Dispose();
		result.Dispose();
		sortedZones.Dispose();
		sortedPolicies.Dispose();
		assetThemes.Dispose();
	}
```

- `private BindPolicyUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity policyEntity, System.Boolean locked) : System.Void`  

```csharp
private void BindPolicyUnlock(IJsonWriter writer, Entity policyEntity, bool locked)
	{
		PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(policyEntity);
		UIObject component = prefab.GetComponent<UIObject>();
		writer.TypeBegin("milestone.UnlockDetails");
		writer.PropertyName("entity");
		writer.Write(policyEntity);
		writer.PropertyName("icon");
		writer.Write(component.m_Icon);
		writer.PropertyName("titleId");
		writer.Write("Policy.TITLE[" + prefab.name + "]");
		writer.PropertyName("descriptionId");
		writer.Write("Policy.DESCRIPTION[" + prefab.name + "]");
		writer.PropertyName("locked");
		writer.Write(locked);
		writer.PropertyName("hasDevTree");
		writer.Write(value: false);
		writer.TypeEnd();
	}
```

- `private BindServiceUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity, System.Boolean locked) : System.Void`  

```csharp
private void BindServiceUnlock(IJsonWriter writer, Entity serviceEntity, bool locked)
	{
		ServicePrefab prefab = m_PrefabSystem.GetPrefab<ServicePrefab>(serviceEntity);
		UIObject component = prefab.GetComponent<UIObject>();
		writer.TypeBegin("milestone.UnlockDetails");
		writer.PropertyName("entity");
		writer.Write(serviceEntity);
		writer.PropertyName("icon");
		writer.Write(component.m_Icon);
		writer.PropertyName("titleId");
		writer.Write("Services.NAME[" + prefab.name + "]");
		writer.PropertyName("descriptionId");
		writer.Write("Services.DESCRIPTION[" + prefab.name + "]");
		writer.PropertyName("locked");
		writer.Write(locked);
		writer.PropertyName("hasDevTree");
		writer.Write(HasDevTree(serviceEntity));
		writer.TypeEnd();
	}
```

- `private BindUnlockDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity unlockEntity) : System.Void`  

```csharp
private void BindUnlockDetails(IJsonWriter writer, Entity unlockEntity)
	{
		if (unlockEntity != Entity.Null && base.EntityManager.HasComponent<PrefabData>(unlockEntity) && base.EntityManager.HasComponent<UIObjectData>(unlockEntity))
		{
			bool locked = base.EntityManager.HasEnabledComponent<Locked>(unlockEntity);
			if (base.EntityManager.HasComponent<FeatureData>(unlockEntity))
			{
				BindFeatureUnlock(writer, unlockEntity, locked);
			}
			else if (base.EntityManager.HasComponent<ServiceData>(unlockEntity))
			{
				BindServiceUnlock(writer, unlockEntity, locked);
			}
			else if (base.EntityManager.HasComponent<ServiceObjectData>(unlockEntity) || base.EntityManager.HasComponent<PlaceableObjectData>(unlockEntity) || base.EntityManager.HasComponent<ZoneData>(unlockEntity))
			{
				BindAssetUnlock(writer, unlockEntity, locked);
			}
			else if (base.EntityManager.HasComponent<PolicyData>(unlockEntity))
			{
				BindPolicyUnlock(writer, unlockEntity, locked);
			}
			else
			{
				writer.WriteNull();
			}
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `private FilterAndSortAssets(Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> result, Unity.Entities.Entity serviceEntity, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets) : System.Void`  

```csharp
private void FilterAndSortAssets(NativeList<AssetInfo> result, Entity serviceEntity, NativeList<Entity> unlockedAssets)
	{
		result.Clear();
		for (int i = 0; i < unlockedAssets.Length; i++)
		{
			Entity entity = unlockedAssets[i];
			if (base.EntityManager.GetComponentData<ServiceObjectData>(entity).m_Service == serviceEntity)
			{
				PrefabData componentData = base.EntityManager.GetComponentData<PrefabData>(entity);
				UIObjectData componentData2 = base.EntityManager.GetComponentData<UIObjectData>(entity);
				int uIPriority = int.MinValue;
				if (componentData2.m_Group != Entity.Null && base.EntityManager.TryGetComponent<UIObjectData>(componentData2.m_Group, out var component))
				{
					uIPriority = component.m_Priority;
				}
				result.Add(new AssetInfo
				{
					m_Entity = entity,
					m_PrefabData = componentData,
					m_UIPriority1 = uIPriority,
					m_UIPriority2 = componentData2.m_Priority
				});
			}
		}
		result.Sort();
	}
```

- `private FilterUnlockedPrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabs, Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private NativeList<Entity> FilterUnlockedPrefabs(NativeArray<Entity> prefabs, Entity milestoneEntity, Allocator allocator)
	{
		NativeParallelHashMap<Entity, UnlockFlags> requiredPrefabs = new NativeParallelHashMap<Entity, UnlockFlags>(10, Allocator.TempJob);
		NativeList<Entity> result = new NativeList<Entity>(20, allocator);
		for (int i = 0; i < prefabs.Length; i++)
		{
			Entity value = prefabs[i];
			requiredPrefabs.Clear();
			ProgressionUtils.CollectSubRequirements(base.EntityManager, value, requiredPrefabs);
			Entity entity = Entity.Null;
			int num = -1;
			foreach (KeyValue<Entity, UnlockFlags> item in requiredPrefabs)
			{
				if ((item.Value & UnlockFlags.RequireAll) != 0)
				{
					if (base.EntityManager.HasComponent<DevTreeNodeData>(item.Key) || base.EntityManager.HasComponent<UnlockRequirementData>(item.Key))
					{
						entity = Entity.Null;
						break;
					}
					if (base.EntityManager.TryGetComponent<MilestoneData>(item.Key, out var component) && component.m_Index > num)
					{
						entity = item.Key;
						num = component.m_Index;
					}
				}
			}
			if (entity == milestoneEntity && entity != Entity.Null)
			{
				result.Add(in value);
			}
		}
		requiredPrefabs.Dispose();
		return result;
	}
```

- `private GetAchievedMilestone() : System.Int32`  

```csharp
private int GetAchievedMilestone()
	{
		if (m_MilestoneLevelQuery.IsEmptyIgnoreFilter)
		{
			return 0;
		}
		return m_MilestoneLevelQuery.GetSingleton<MilestoneLevel>().m_AchievedMilestone;
	}
```

- `private GetAchievedMilestoneXP() : System.Int32`  

```csharp
private int GetAchievedMilestoneXP()
	{
		return m_XpMilestoneSystem.lastRequiredXP;
	}
```

- `private GetMilestoneIndex(Unity.Entities.Entity milestoneEntity) : System.Int32`  

```csharp
private int GetMilestoneIndex(Entity milestoneEntity)
	{
		if (!(milestoneEntity != Entity.Null) || !base.EntityManager.TryGetComponent<MilestoneData>(milestoneEntity, out var component))
		{
			return -1;
		}
		return component.m_Index;
	}
```

- `private GetNextMilestoneXP() : System.Int32`  

```csharp
private int GetNextMilestoneXP()
	{
		return m_XpMilestoneSystem.nextRequiredXP;
	}
```

- `private GetSortedMilestones(Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<Game.UI.InGame.MilestoneUISystem+ComparableMilestone>`  

```csharp
private NativeArray<ComparableMilestone> GetSortedMilestones(Allocator allocator)
	{
		NativeArray<Entity> nativeArray = m_MilestoneQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<MilestoneData> nativeArray2 = m_MilestoneQuery.ToComponentDataArray<MilestoneData>(Allocator.TempJob);
		NativeArray<ComparableMilestone> nativeArray3 = new NativeArray<ComparableMilestone>(nativeArray2.Length, allocator);
		for (int i = 0; i < nativeArray2.Length; i++)
		{
			nativeArray3[i] = new ComparableMilestone
			{
				m_Entity = nativeArray[i],
				m_Data = nativeArray2[i]
			};
		}
		nativeArray3.Sort();
		nativeArray.Dispose();
		nativeArray2.Dispose();
		return nativeArray3;
	}
```

- `private GetSortedPolicies(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private NativeList<UIObjectInfo> GetSortedPolicies(Entity milestoneEntity, Allocator allocator)
	{
		NativeArray<Entity> prefabs = m_UnlockablePolicyQuery.ToEntityArray(Allocator.TempJob);
		NativeList<Entity> entities = FilterUnlockedPrefabs(prefabs, milestoneEntity, Allocator.TempJob);
		NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(base.EntityManager, entities, allocator);
		prefabs.Dispose();
		entities.Dispose();
		return sortedObjects;
	}
```

- `private GetSortedServices(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedDevTreeServices, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+ServiceInfo>`  

```csharp
private NativeList<ServiceInfo> GetSortedServices(NativeList<Entity> unlockedDevTreeServices, NativeList<Entity> unlockedAssets, Allocator allocator)
	{
		NativeParallelHashSet<Entity> nativeParallelHashSet = new NativeParallelHashSet<Entity>(10, Allocator.TempJob);
		NativeList<ServiceInfo> nativeList = new NativeList<ServiceInfo>(10, allocator);
		for (int i = 0; i < unlockedDevTreeServices.Length; i++)
		{
			Entity entity = unlockedDevTreeServices[i];
			if (nativeParallelHashSet.Add(entity) && base.EntityManager.TryGetComponent<UIObjectData>(entity, out var component))
			{
				PrefabData componentData = base.EntityManager.GetComponentData<PrefabData>(entity);
				ServiceInfo value = new ServiceInfo
				{
					m_Entity = entity,
					m_PrefabData = componentData,
					m_UIPriority = component.m_Priority,
					m_DevTreeUnlocked = true
				};
				nativeList.Add(in value);
			}
		}
		for (int j = 0; j < unlockedAssets.Length; j++)
		{
			Entity service = base.EntityManager.GetComponentData<ServiceObjectData>(unlockedAssets[j]).m_Service;
			if (nativeParallelHashSet.Add(service) && base.EntityManager.TryGetComponent<UIObjectData>(service, out var component2))
			{
				PrefabData componentData2 = base.EntityManager.GetComponentData<PrefabData>(service);
				ServiceInfo value = new ServiceInfo
				{
					m_Entity = service,
					m_PrefabData = componentData2,
					m_UIPriority = component2.m_Priority,
					m_DevTreeUnlocked = false
				};
				nativeList.Add(in value);
			}
		}
		nativeList.Sort();
		nativeParallelHashSet.Dispose();
		return nativeList;
	}
```

- `private GetSortedUnlockedFeatures(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private NativeList<UIObjectInfo> GetSortedUnlockedFeatures(Entity milestoneEntity, Allocator allocator)
	{
		NativeArray<Entity> prefabs = m_UnlockableFeatureQuery.ToEntityArray(Allocator.TempJob);
		NativeList<Entity> entities = FilterUnlockedPrefabs(prefabs, milestoneEntity, Allocator.TempJob);
		NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(base.EntityManager, entities, allocator);
		prefabs.Dispose();
		entities.Dispose();
		if (m_CityConfigurationSystem.unlockMapTiles)
		{
			int num = -1;
			for (int i = 0; i < sortedObjects.Length; i++)
			{
				UIObjectInfo uIObjectInfo = sortedObjects[i];
				if (m_PrefabSystem.GetPrefab<PrefabBase>(uIObjectInfo.prefabData).name == "Map Tiles")
				{
					num = i;
					break;
				}
			}
			if (num != -1)
			{
				sortedObjects.RemoveAt(num);
			}
		}
		return sortedObjects;
	}
```

- `private GetSortedZones(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedZones, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo>`  

```csharp
private NativeList<AssetInfo> GetSortedZones(NativeList<Entity> unlockedZones, Allocator allocator)
	{
		NativeList<AssetInfo> nativeList = new NativeList<AssetInfo>(10, allocator);
		for (int i = 0; i < unlockedZones.Length; i++)
		{
			Entity entity = unlockedZones[i];
			PrefabData componentData = base.EntityManager.GetComponentData<PrefabData>(entity);
			UIObjectData componentData2 = base.EntityManager.GetComponentData<UIObjectData>(entity);
			int uIPriority = int.MinValue;
			if (componentData2.m_Group != Entity.Null && base.EntityManager.TryGetComponent<UIObjectData>(componentData2.m_Group, out var component))
			{
				uIPriority = component.m_Priority;
			}
			nativeList.Add(new AssetInfo
			{
				m_Entity = entity,
				m_PrefabData = componentData,
				m_UIPriority1 = uIPriority,
				m_UIPriority2 = componentData2.m_Priority
			});
		}
		nativeList.Sort();
		return nativeList;
	}
```

- `private GetThemes(Unity.Collections.NativeList<Unity.Entities.Entity> result, Unity.Entities.Entity assetEntity) : System.Void`  

```csharp
private void GetThemes(NativeList<Entity> result, Entity assetEntity)
	{
		result.Clear();
		if (!base.EntityManager.TryGetBuffer(assetEntity, isReadOnly: true, out DynamicBuffer<ObjectRequirementElement> buffer))
		{
			return;
		}
		foreach (ObjectRequirementElement item in buffer)
		{
			ObjectRequirementElement current = item;
			if (base.EntityManager.HasComponent<ThemeData>(current.m_Requirement))
			{
				result.Add(in current.m_Requirement);
			}
		}
	}
```

- `private GetTotalXP() : System.Int32`  

```csharp
private int GetTotalXP()
	{
		return m_CitySystem.XP;
	}
```

- `private GetUnlockedAssets(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private NativeList<Entity> GetUnlockedAssets(Entity milestoneEntity, Allocator allocator)
	{
		NativeArray<Entity> prefabs = m_UnlockableAssetQuery.ToEntityArray(Allocator.TempJob);
		NativeList<Entity> result = FilterUnlockedPrefabs(prefabs, milestoneEntity, allocator);
		prefabs.Dispose();
		return result;
	}
```

- `private GetUnlockedDevTreeServices(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private NativeList<Entity> GetUnlockedDevTreeServices(Entity milestoneEntity, Allocator allocator)
	{
		NativeArray<DevTreeNodeData> nativeArray = m_DevTreeNodeQuery.ToComponentDataArray<DevTreeNodeData>(Allocator.TempJob);
		NativeParallelHashSet<Entity> nativeParallelHashSet = new NativeParallelHashSet<Entity>(10, Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			nativeParallelHashSet.Add(nativeArray[i].m_Service);
		}
		NativeArray<Entity> prefabs = nativeParallelHashSet.ToNativeArray(Allocator.TempJob);
		NativeList<Entity> result = FilterUnlockedPrefabs(prefabs, milestoneEntity, allocator);
		nativeArray.Dispose();
		nativeParallelHashSet.Dispose();
		prefabs.Dispose();
		return result;
	}
```

- `private GetUnlockedZones(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private NativeList<Entity> GetUnlockedZones(Entity milestoneEntity, Allocator allocator)
	{
		NativeArray<Entity> prefabs = m_UnlockableZoneQuery.ToEntityArray(Allocator.TempJob);
		NativeList<Entity> result = FilterUnlockedPrefabs(prefabs, milestoneEntity, allocator);
		prefabs.Dispose();
		return result;
	}
```

- `private HasDevTree(Unity.Entities.Entity serviceEntity) : System.Boolean`  

```csharp
private bool HasDevTree(Entity serviceEntity)
	{
		using NativeArray<DevTreeNodeData> nativeArray = m_DevTreeNodeQuery.ToComponentDataArray<DevTreeNodeData>(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray[i].m_Service == serviceEntity)
			{
				return true;
			}
		}
		return false;
	}
```

- `private IsMaxMilestoneReached() : System.Boolean`  

```csharp
private bool IsMaxMilestoneReached()
	{
		return m_LockedMilestoneQuery.IsEmpty;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_XPSystem = base.World.GetOrCreateSystemManaged<XPSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_XpMilestoneSystem = base.World.GetOrCreateSystemManaged<MilestoneSystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TutorialSystem = base.World.GetOrCreateSystemManaged<TutorialSystem>();
		m_MilestoneLevelQuery = GetEntityQuery(ComponentType.ReadOnly<MilestoneLevel>());
		m_MilestoneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<MilestoneData>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_LockedMilestoneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<MilestoneData>(),
				ComponentType.ReadOnly<Locked>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ModifiedMilestoneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<MilestoneData>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_MilestoneReachedEventQuery = GetEntityQuery(ComponentType.ReadOnly<MilestoneReachedEvent>());
		m_UnlockableAssetQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<UIObjectData>(),
				ComponentType.ReadOnly<ServiceObjectData>(),
				ComponentType.ReadOnly<UnlockRequirement>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_UnlockableZoneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<UIObjectData>(),
				ComponentType.ReadOnly<ZoneData>(),
				ComponentType.ReadOnly<UnlockRequirement>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[5]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<UIObjectData>(),
				ComponentType.ReadOnly<PlaceholderBuildingData>(),
				ComponentType.ReadOnly<PlaceableObjectData>(),
				ComponentType.ReadOnly<UnlockRequirement>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_DevTreeNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<DevTreeNodeData>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_UnlockableFeatureQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<FeatureData>(),
				ComponentType.ReadOnly<UIObjectData>(),
				ComponentType.ReadOnly<UnlockRequirement>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_UnlockablePolicyQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<PolicyData>(), ComponentType.ReadOnly<UIObjectData>(), ComponentType.ReadOnly<UnlockRequirement>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		AddBinding(m_AchievedMilestoneBinding = new GetterValueBinding<int>("milestone", "achievedMilestone", GetAchievedMilestone));
		AddBinding(m_MaxMilestoneReachedBinding = new GetterValueBinding<bool>("milestone", "maxMilestoneReached", IsMaxMilestoneReached));
		AddBinding(m_AchievedMilestoneXPBinding = new GetterValueBinding<int>("milestone", "achievedMilestoneXP", GetAchievedMilestoneXP));
		AddBinding(m_NextMilestoneXPBinding = new GetterValueBinding<int>("milestone", "nextMilestoneXP", GetNextMilestoneXP));
		AddBinding(m_TotalXPBinding = new GetterValueBinding<int>("milestone", "totalXP", GetTotalXP));
		AddBinding(m_XpMessageAddedBinding = new RawEventBinding("milestone", "xpMessageAdded"));
		AddBinding(m_MilestonesBinding = new RawValueBinding("milestone", "milestones", BindMilestones));
		AddBinding(m_UnlockedMilestoneBinding = new ValueBinding<Entity>("milestone", "unlockedMilestone", Entity.Null));
		AddBinding(new TriggerBinding("milestone", "clearUnlockedMilestone", delegate
		{
			m_UnlockedMilestoneBinding.Update(Entity.Null);
		}));
		AddBinding(m_MilestoneDetailsBinding = new RawMapBinding<Entity>("milestone", "milestoneDetails", BindMilestoneDetails));
		AddBinding(m_MilestoneUnlocksBinding = new RawMapBinding<Entity>("milestone", "milestoneUnlocks", BindMilestoneUnlocks));
		AddBinding(m_UnlockDetailsBinding = new RawMapBinding<Entity>("milestone", "unlockDetails", BindUnlockDetails));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_UnlockedMilestoneBinding.Update(Entity.Null);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_AchievedMilestoneBinding.Update();
		m_MaxMilestoneReachedBinding.Update();
		m_TotalXPBinding.Update();
		m_AchievedMilestoneXPBinding.Update();
		m_NextMilestoneXPBinding.Update();
		if (!m_MilestoneReachedEventQuery.IsEmptyIgnoreFilter)
		{
			PublishReachedMilestones();
		}
		if (!m_MilestoneReachedEventQuery.IsEmptyIgnoreFilter || !m_ModifiedMilestoneQuery.IsEmptyIgnoreFilter)
		{
			m_MilestonesBinding.Update();
			m_MilestoneDetailsBinding.Update();
		}
		m_XPSystem.TransferMessages(this);
	}
```

- `private PublishReachedMilestones() : System.Void`  

```csharp
private void PublishReachedMilestones()
	{
		Entity newValue = m_UnlockedMilestoneBinding.value;
		int num = GetMilestoneIndex(m_UnlockedMilestoneBinding.value);
		NativeArray<MilestoneReachedEvent> nativeArray = m_MilestoneReachedEventQuery.ToComponentDataArray<MilestoneReachedEvent>(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray[i].m_Index > num)
			{
				newValue = nativeArray[i].m_Milestone;
				num = nativeArray[i].m_Index;
			}
		}
		nativeArray.Dispose();
		Telemetry.MilestoneUnlocked(num);
		PlatformManager.instance.IndicateAchievementProgress(Game.Achievements.Achievements.TheLastMileMarker, num);
		if (SharedSettings.instance.userInterface.blockingPopupsEnabled && !m_CityConfigurationSystem.unlockAll)
		{
			m_UnlockedMilestoneBinding.Update(newValue);
		}
	}
```


## Nested types

- `Game.UI.InGame.MilestoneUISystem+ComparableMilestone`  
- `Game.UI.InGame.MilestoneUISystem+ServiceInfo`  
- `Game.UI.InGame.MilestoneUISystem+AssetInfo`  

