# Game.UI.InGame.PrefabUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Unity.Entities.Entity m_RequirementEntity`  
- `private Unity.Entities.Entity m_TutorialRequirementEntity`  
- `private Unity.Entities.EntityQuery m_ThemeQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedThemeQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  
- `private Unity.Entities.EntityQuery m_PollutionConfigQuery`  
- `private Unity.Entities.EntityQuery m_ManualUITagsConfigQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.Dictionary<System.String, System.String>> m_UITagsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ThemesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_PrefabDetailsBinding`  
- `private System.Int32 m_UnlockRequirementVersion`  
- `private System.Int32 m_UITagVersion`  
- `private System.Boolean m_Initialized`  
- `private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> <effectBinders>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <constructionCostBinders>k__BackingField`  
- `private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <propertyBinders>k__BackingField`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> effectBinders { get; private set }`  
- `public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> constructionCostBinders { get; private set }`  
- `public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> propertyBinders { get; private set }`  

## Constructors

- `public PrefabUISystem()`  

## Methods

- `private BindCitizenRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.CitizenRequirementPrefab cr) : System.Void`  
- `public BindConstructionCost(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private BindDevTreeNodeRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `public BindEffects(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private BindManualUITags() : System.Collections.Generic.Dictionary<System.String, System.String>`  
- `private BindMilestoneRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private BindObjectBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.StrictObjectBuiltRequirementPrefab prefab) : System.Void`  
- `private BindOnBuildRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ObjectBuiltRequirementPrefab prefab) : System.Void`  
- `private BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `public BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed) : System.Void`  
- `public BindPrefabRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private BindPrefabUnlockedRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.PrefabUnlockedRequirementPrefab prefab) : System.Void`  
- `private BindProcessingRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ProcessingRequirementPrefab prefab) : System.Void`  
- `public BindProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UnlockFlags flag, Unity.Entities.Entity milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  
- `private BindThemes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindTutorialRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private BindUIGroupRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  
- `private BindUnknownUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab) : System.Void`  
- `private BindUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private BindUnlockRequirementProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab) : System.Void`  
- `private BindZoneBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ZoneBuiltRequirementPrefab prefab) : System.Void`  
- `private static BuildDefaultConstructionCostBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder>`  
- `private static BuildDefaultEffectBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder>`  
- `private BuildDefaultPropertyBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder>`  
- `private FindLowestRequirements(Unity.Entities.Entity prefabEntity, Unity.Collections.NativeList<Unity.Entities.Entity> requirements, System.Int32 score = -1) : System.Int32`  
- `private GetRequirements(Unity.Entities.Entity prefabEntity, Unity.Entities.Entity& milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  
- `public GetTitleAndDescription(Unity.Entities.Entity prefabEntity, System.String& titleId, System.String& descriptionId) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private VerifyRequirements(Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

## Nested types

- `Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder`  
- `Game.UI.InGame.PrefabUISystem+CityModifierBinder`  
- `Game.UI.InGame.PrefabUISystem+LocalModifierBinder`  
- `Game.UI.InGame.PrefabUISystem+LeisureProviderBinder`  
- `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  
- `Game.UI.InGame.PrefabUISystem+IntPropertyBinder`  
- `Game.UI.InGame.PrefabUISystem+IntRangePropertyBinder`  
- `Game.UI.InGame.PrefabUISystem+Int2PropertyBinder`  
- `Game.UI.InGame.PrefabUISystem+ComponentIntPropertyBinder<T>`  
- `Game.UI.InGame.PrefabUISystem+ComponentIntRangePropertyBinder<T>`  
- `Game.UI.InGame.PrefabUISystem+ComponentInt2PropertyBinder<T>`  
- `Game.UI.InGame.PrefabUISystem+StringPropertyBinder`  
- `Game.UI.InGame.PrefabUISystem+ConstructionCostBinder`  
- `Game.UI.InGame.PrefabUISystem+ConsumptionBinder`  
- `Game.UI.InGame.PrefabUISystem+PollutionBinder`  
- `Game.UI.InGame.PrefabUISystem+ElectricityPropertyBinder`  
- `Game.UI.InGame.PrefabUISystem+UpkeepPropertyBinderSystem`  
- `Game.UI.InGame.PrefabUISystem+UpkeepIntProperty`  
- `Game.UI.InGame.PrefabUISystem+UpkeepInt2Property`  
- `Game.UI.InGame.PrefabUISystem+StorageLimitBinder`  
- `Game.UI.InGame.PrefabUISystem+PowerProductionBinder`  
- `Game.UI.InGame.PrefabUISystem+TransformerCapacityBinder`  
- `Game.UI.InGame.PrefabUISystem+TransformerInputBinder`  
- `Game.UI.InGame.PrefabUISystem+TransformerOutputBinder`  
- `Game.UI.InGame.PrefabUISystem+ElectricityConnectionBinder`  
- `Game.UI.InGame.PrefabUISystem+WaterConnectionBinder`  
- `Game.UI.InGame.PrefabUISystem+JailCapacityBinder`  
- `Game.UI.InGame.PrefabUISystem+TransportStopBinder`  
- `Game.UI.InGame.PrefabUISystem+RequiredResourceBinder`  
- `Game.UI.InGame.PrefabUISystem+UpkeepModifierBinder`  
- `Game.UI.InGame.PrefabUISystem+<>c`  

