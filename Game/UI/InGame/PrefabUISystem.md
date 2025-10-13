# Game.UI.InGame.PrefabUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.Entity m_RequirementEntity;
    private Unity.Entities.Entity m_TutorialRequirementEntity;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    private Unity.Entities.EntityQuery m_ModifiedThemeQuery;
    private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
    private Unity.Entities.EntityQuery m_PollutionConfigQuery;
    private Unity.Entities.EntityQuery m_ManualUITagsConfigQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.Dictionary<System.String, System.String>> m_UITagsBinding;
    private Colossal.UI.Binding.RawValueBinding m_ThemesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_PrefabDetailsBinding;
    private System.Int32 m_UnlockRequirementVersion;
    private System.Int32 m_UITagVersion;
    private System.Boolean m_Initialized;
    private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> <effectBinders>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <constructionCostBinders>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <propertyBinders>k__BackingField;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> effectBinders { get; private set; }
    public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> constructionCostBinders { get; private set; }
    public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> propertyBinders { get; private set; }

    public PrefabUISystem();

    private System.Void BindCitizenRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.CitizenRequirementPrefab cr);
    public System.Void BindConstructionCost(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity);
    private System.Void BindDevTreeNodeRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    public System.Void BindEffects(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity);
    private System.Collections.Generic.Dictionary<System.String, System.String> BindManualUITags();
    private System.Void BindMilestoneRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindObjectBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.StrictObjectBuiltRequirementPrefab prefab);
    private System.Void BindOnBuildRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ObjectBuiltRequirementPrefab prefab);
    private System.Void BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    public System.Void BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed);
    public System.Void BindPrefabRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
    private System.Void BindPrefabUnlockedRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.PrefabUnlockedRequirementPrefab prefab);
    private System.Void BindProcessingRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ProcessingRequirementPrefab prefab);
    public System.Void BindProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity);
    private System.Void BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
    private System.Void BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UnlockFlags flag, Unity.Entities.Entity milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements);
    private System.Void BindThemes(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindTutorialRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindUIGroupRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
    private System.Void BindUnknownUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab);
    private System.Void BindUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindUnlockRequirementProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab);
    private System.Void BindZoneBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ZoneBuiltRequirementPrefab prefab);
    private static System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> BuildDefaultConstructionCostBinders();
    private static System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> BuildDefaultEffectBinders();
    private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> BuildDefaultPropertyBinders();
    private System.Int32 FindLowestRequirements(Unity.Entities.Entity prefabEntity, Unity.Collections.NativeList<Unity.Entities.Entity> requirements, System.Int32 score);
    private System.Void GetRequirements(Unity.Entities.Entity prefabEntity, Unity.Entities.Entity& milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements);
    public System.Void GetTitleAndDescription(Unity.Entities.Entity prefabEntity, System.String& titleId, System.String& descriptionId);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void VerifyRequirements(Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  

```csharp
private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.Entity m_RequirementEntity`  

```csharp
private Unity.Entities.Entity m_RequirementEntity;
```

- `private Unity.Entities.Entity m_TutorialRequirementEntity`  

```csharp
private Unity.Entities.Entity m_TutorialRequirementEntity;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedThemeQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PollutionConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionConfigQuery;
```

- `private Unity.Entities.EntityQuery m_ManualUITagsConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ManualUITagsConfigQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.Dictionary<System.String, System.String>> m_UITagsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.Dictionary<System.String, System.String>> m_UITagsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ThemesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ThemesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_PrefabDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_PrefabDetailsBinding;
```

- `private System.Int32 m_UnlockRequirementVersion`  

```csharp
private System.Int32 m_UnlockRequirementVersion;
```

- `private System.Int32 m_UITagVersion`  

```csharp
private System.Int32 m_UITagVersion;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> <effectBinders>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> <effectBinders>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <constructionCostBinders>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <constructionCostBinders>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <propertyBinders>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> <propertyBinders>k__BackingField;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> effectBinders { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> effectBinders { get; private set; }
```

- `public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> constructionCostBinders { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> constructionCostBinders { get; private set; }
```

- `public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> propertyBinders { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> propertyBinders { get; private set; }
```


## Constructors

- `public PrefabUISystem()`  

```csharp
public PrefabUISystem();
```


## Methods

- `private BindCitizenRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.CitizenRequirementPrefab cr) : System.Void`  

```csharp
private System.Void BindCitizenRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.CitizenRequirementPrefab cr);
```

- `public BindConstructionCost(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public System.Void BindConstructionCost(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity);
```

- `private BindDevTreeNodeRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindDevTreeNodeRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `public BindEffects(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public System.Void BindEffects(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity);
```

- `private BindManualUITags() : System.Collections.Generic.Dictionary<System.String, System.String>`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.String> BindManualUITags();
```

- `private BindMilestoneRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindMilestoneRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private BindObjectBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.StrictObjectBuiltRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindObjectBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.StrictObjectBuiltRequirementPrefab prefab);
```

- `private BindOnBuildRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ObjectBuiltRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindOnBuildRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ObjectBuiltRequirementPrefab prefab);
```

- `private BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `public BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed) : System.Void`  

```csharp
public System.Void BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed);
```

- `public BindPrefabRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public System.Void BindPrefabRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
```

- `private BindPrefabUnlockedRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.PrefabUnlockedRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindPrefabUnlockedRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.PrefabUnlockedRequirementPrefab prefab);
```

- `private BindProcessingRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ProcessingRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindProcessingRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ProcessingRequirementPrefab prefab);
```

- `public BindProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public System.Void BindProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity);
```

- `private BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
private System.Void BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
```

- `private BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UnlockFlags flag, Unity.Entities.Entity milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

```csharp
private System.Void BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UnlockFlags flag, Unity.Entities.Entity milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements);
```

- `private BindThemes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindThemes(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindTutorialRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindTutorialRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private BindUIGroupRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
private System.Void BindUIGroupRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity);
```

- `private BindUnknownUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindUnknownUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab);
```

- `private BindUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private BindUnlockRequirementProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindUnlockRequirementProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab);
```

- `private BindZoneBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ZoneBuiltRequirementPrefab prefab) : System.Void`  

```csharp
private System.Void BindZoneBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ZoneBuiltRequirementPrefab prefab);
```

- `private static BuildDefaultConstructionCostBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder>`  

```csharp
private static System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> BuildDefaultConstructionCostBinders();
```

- `private static BuildDefaultEffectBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder>`  

```csharp
private static System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder> BuildDefaultEffectBinders();
```

- `private BuildDefaultPropertyBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder>`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder> BuildDefaultPropertyBinders();
```

- `private FindLowestRequirements(Unity.Entities.Entity prefabEntity, Unity.Collections.NativeList<Unity.Entities.Entity> requirements, System.Int32 score = -1) : System.Int32`  

```csharp
private System.Int32 FindLowestRequirements(Unity.Entities.Entity prefabEntity, Unity.Collections.NativeList<Unity.Entities.Entity> requirements, System.Int32 score);
```

- `private GetRequirements(Unity.Entities.Entity prefabEntity, Unity.Entities.Entity& milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

```csharp
private System.Void GetRequirements(Unity.Entities.Entity prefabEntity, Unity.Entities.Entity& milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements);
```

- `public GetTitleAndDescription(Unity.Entities.Entity prefabEntity, System.String& titleId, System.String& descriptionId) : System.Void`  

```csharp
public System.Void GetTitleAndDescription(Unity.Entities.Entity prefabEntity, System.String& titleId, System.String& descriptionId);
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

- `private VerifyRequirements(Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

```csharp
private System.Void VerifyRequirements(Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements);
```


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

