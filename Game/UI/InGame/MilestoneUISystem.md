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
public MilestoneUISystem();
```


## Methods

- `private <OnCreate>b__30_0() : System.Void`  

```csharp
private System.Void <OnCreate>b__30_0();
```

- `public AddMessage(Game.Simulation.XPMessage message) : System.Void`  

```csharp
public System.Void AddMessage(Game.Simulation.XPMessage message);
```

- `private BindAsset(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.MilestoneUISystem+AssetInfo asset, Game.Prefabs.PrefabBase assetPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> assetThemes) : System.Void`  

```csharp
private System.Void BindAsset(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.MilestoneUISystem+AssetInfo asset, Game.Prefabs.PrefabBase assetPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> assetThemes);
```

- `private BindAssetUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetEntity, System.Boolean locked) : System.Void`  

```csharp
private System.Void BindAssetUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetEntity, System.Boolean locked);
```

- `private BindFeatureUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity featureEntity, System.Boolean locked) : System.Void`  

```csharp
private System.Void BindFeatureUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity featureEntity, System.Boolean locked);
```

- `private BindMilestoneDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestone) : System.Void`  

```csharp
private System.Void BindMilestoneDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestone);
```

- `private BindMilestones(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindMilestones(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindMilestoneUnlocks(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestoneEntity) : System.Void`  

```csharp
private System.Void BindMilestoneUnlocks(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestoneEntity);
```

- `private BindPolicyUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity policyEntity, System.Boolean locked) : System.Void`  

```csharp
private System.Void BindPolicyUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity policyEntity, System.Boolean locked);
```

- `private BindServiceUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity, System.Boolean locked) : System.Void`  

```csharp
private System.Void BindServiceUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity, System.Boolean locked);
```

- `private BindUnlockDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity unlockEntity) : System.Void`  

```csharp
private System.Void BindUnlockDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity unlockEntity);
```

- `private FilterAndSortAssets(Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> result, Unity.Entities.Entity serviceEntity, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets) : System.Void`  

```csharp
private System.Void FilterAndSortAssets(Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> result, Unity.Entities.Entity serviceEntity, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets);
```

- `private FilterUnlockedPrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabs, Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> FilterUnlockedPrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabs, Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
```

- `private GetAchievedMilestone() : System.Int32`  

```csharp
private System.Int32 GetAchievedMilestone();
```

- `private GetAchievedMilestoneXP() : System.Int32`  

```csharp
private System.Int32 GetAchievedMilestoneXP();
```

- `private GetMilestoneIndex(Unity.Entities.Entity milestoneEntity) : System.Int32`  

```csharp
private System.Int32 GetMilestoneIndex(Unity.Entities.Entity milestoneEntity);
```

- `private GetNextMilestoneXP() : System.Int32`  

```csharp
private System.Int32 GetNextMilestoneXP();
```

- `private GetSortedMilestones(Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<Game.UI.InGame.MilestoneUISystem+ComparableMilestone>`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.MilestoneUISystem+ComparableMilestone> GetSortedMilestones(Unity.Collections.Allocator allocator);
```

- `private GetSortedPolicies(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedPolicies(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
```

- `private GetSortedServices(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedDevTreeServices, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+ServiceInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+ServiceInfo> GetSortedServices(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedDevTreeServices, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets, Unity.Collections.Allocator allocator);
```

- `private GetSortedUnlockedFeatures(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedUnlockedFeatures(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
```

- `private GetSortedZones(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedZones, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> GetSortedZones(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedZones, Unity.Collections.Allocator allocator);
```

- `private GetThemes(Unity.Collections.NativeList<Unity.Entities.Entity> result, Unity.Entities.Entity assetEntity) : System.Void`  

```csharp
private System.Void GetThemes(Unity.Collections.NativeList<Unity.Entities.Entity> result, Unity.Entities.Entity assetEntity);
```

- `private GetTotalXP() : System.Int32`  

```csharp
private System.Int32 GetTotalXP();
```

- `private GetUnlockedAssets(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> GetUnlockedAssets(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
```

- `private GetUnlockedDevTreeServices(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> GetUnlockedDevTreeServices(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
```

- `private GetUnlockedZones(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> GetUnlockedZones(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator);
```

- `private HasDevTree(Unity.Entities.Entity serviceEntity) : System.Boolean`  

```csharp
private System.Boolean HasDevTree(Unity.Entities.Entity serviceEntity);
```

- `private IsMaxMilestoneReached() : System.Boolean`  

```csharp
private System.Boolean IsMaxMilestoneReached();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PublishReachedMilestones() : System.Void`  

```csharp
private System.Void PublishReachedMilestones();
```


## Nested types

- `Game.UI.InGame.MilestoneUISystem+ComparableMilestone`  
- `Game.UI.InGame.MilestoneUISystem+ServiceInfo`  
- `Game.UI.InGame.MilestoneUISystem+AssetInfo`  

