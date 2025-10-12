# Game.UI.InGame.MilestoneUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Simulation.IXPMessageHandler`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.IXPSystem m_XPSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.IMilestoneSystem m_XpMilestoneSystem`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Tutorials.TutorialSystem m_TutorialSystem`  
- `private Unity.Entities.EntityQuery m_MilestoneLevelQuery`  
- `private Unity.Entities.EntityQuery m_MilestoneQuery`  
- `private Unity.Entities.EntityQuery m_LockedMilestoneQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedMilestoneQuery`  
- `private Unity.Entities.EntityQuery m_MilestoneReachedEventQuery`  
- `private Unity.Entities.EntityQuery m_UnlockableAssetQuery`  
- `private Unity.Entities.EntityQuery m_UnlockableZoneQuery`  
- `private Unity.Entities.EntityQuery m_DevTreeNodeQuery`  
- `private Unity.Entities.EntityQuery m_UnlockableFeatureQuery`  
- `private Unity.Entities.EntityQuery m_UnlockablePolicyQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MaxMilestoneReachedBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_AchievedMilestoneXPBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_NextMilestoneXPBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TotalXPBinding`  
- `private Colossal.UI.Binding.RawEventBinding m_XpMessageAddedBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_MilestonesBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_UnlockedMilestoneBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneDetailsBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_MilestoneUnlocksBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UnlockDetailsBinding`  
- `private static const System.String kGroup`  

## Constructors

- `public MilestoneUISystem()`  

## Methods

- `private <OnCreate>b__30_0() : System.Void`  
- `public AddMessage(Game.Simulation.XPMessage message) : System.Void`  
- `private BindAsset(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.MilestoneUISystem+AssetInfo asset, Game.Prefabs.PrefabBase assetPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> assetThemes) : System.Void`  
- `private BindAssetUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetEntity, System.Boolean locked) : System.Void`  
- `private BindFeatureUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity featureEntity, System.Boolean locked) : System.Void`  
- `private BindMilestoneDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestone) : System.Void`  
- `private BindMilestones(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindMilestoneUnlocks(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity milestoneEntity) : System.Void`  
- `private BindPolicyUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity policyEntity, System.Boolean locked) : System.Void`  
- `private BindServiceUnlock(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity, System.Boolean locked) : System.Void`  
- `private BindUnlockDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity unlockEntity) : System.Void`  
- `private FilterAndSortAssets(Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo> result, Unity.Entities.Entity serviceEntity, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets) : System.Void`  
- `private FilterUnlockedPrefabs(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabs, Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private GetAchievedMilestone() : System.Int32`  
- `private GetAchievedMilestoneXP() : System.Int32`  
- `private GetMilestoneIndex(Unity.Entities.Entity milestoneEntity) : System.Int32`  
- `private GetNextMilestoneXP() : System.Int32`  
- `private GetSortedMilestones(Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<Game.UI.InGame.MilestoneUISystem+ComparableMilestone>`  
- `private GetSortedPolicies(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `private GetSortedServices(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedDevTreeServices, Unity.Collections.NativeList<Unity.Entities.Entity> unlockedAssets, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+ServiceInfo>`  
- `private GetSortedUnlockedFeatures(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `private GetSortedZones(Unity.Collections.NativeList<Unity.Entities.Entity> unlockedZones, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.InGame.MilestoneUISystem+AssetInfo>`  
- `private GetThemes(Unity.Collections.NativeList<Unity.Entities.Entity> result, Unity.Entities.Entity assetEntity) : System.Void`  
- `private GetTotalXP() : System.Int32`  
- `private GetUnlockedAssets(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private GetUnlockedDevTreeServices(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private GetUnlockedZones(Unity.Entities.Entity milestoneEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private HasDevTree(Unity.Entities.Entity serviceEntity) : System.Boolean`  
- `private IsMaxMilestoneReached() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PublishReachedMilestones() : System.Void`  

## Nested types

- `Game.UI.InGame.MilestoneUISystem+ComparableMilestone`  
- `Game.UI.InGame.MilestoneUISystem+ServiceInfo`  
- `Game.UI.InGame.MilestoneUISystem+AssetInfo`  

