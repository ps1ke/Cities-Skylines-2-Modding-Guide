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
[Preserve]
	public PrefabUISystem()
	{
	}
```


## Methods

- `private BindCitizenRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.CitizenRequirementPrefab cr) : System.Void`  

```csharp
private void BindCitizenRequirement(IJsonWriter binder, Entity entity, CitizenRequirementPrefab cr)
	{
		binder.TypeBegin("prefabs.CitizenRequirement");
		BindUnlockRequirementProperties(binder, entity, cr);
		binder.PropertyName("minimumPopulation");
		binder.Write(cr.m_MinimumPopulation);
		binder.PropertyName("minimumHappiness");
		binder.Write(cr.m_MinimumHappiness);
		binder.TypeEnd();
	}
```

- `public BindConstructionCost(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public void BindConstructionCost(IJsonWriter binder, Entity prefabEntity)
	{
		if (m_Initialized)
		{
			foreach (IPrefabPropertyBinder constructionCostBinder in constructionCostBinders)
			{
				if (constructionCostBinder.Matches(base.EntityManager, prefabEntity))
				{
					constructionCostBinder.Bind(binder, base.EntityManager, prefabEntity);
					return;
				}
			}
		}
		binder.WriteNull();
	}
```

- `private BindDevTreeNodeRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindDevTreeNodeRequirement(IJsonWriter binder, Entity entity)
	{
		DevTreeNodePrefab prefab = m_PrefabSystem.GetPrefab<DevTreeNodePrefab>(entity);
		bool value = base.EntityManager.HasEnabledComponent<Locked>(entity);
		binder.TypeBegin("prefabs.DevTreeNodeRequirement");
		binder.PropertyName("entity");
		binder.Write(entity);
		binder.PropertyName("name");
		binder.Write(prefab.name);
		binder.PropertyName("locked");
		binder.Write(value);
		binder.TypeEnd();
	}
```

- `public BindEffects(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public void BindEffects(IJsonWriter binder, Entity prefabEntity)
	{
		int num = 0;
		foreach (IPrefabEffectBinder effectBinder in effectBinders)
		{
			if (effectBinder.Matches(base.EntityManager, prefabEntity))
			{
				num++;
			}
		}
		binder.ArrayBegin(num);
		foreach (IPrefabEffectBinder effectBinder2 in effectBinders)
		{
			if (effectBinder2.Matches(base.EntityManager, prefabEntity))
			{
				effectBinder2.Bind(binder, base.EntityManager, prefabEntity);
			}
		}
		binder.ArrayEnd();
	}
```

- `private BindManualUITags() : System.Collections.Generic.Dictionary<System.String, System.String>`  

```csharp
private Dictionary<string, string> BindManualUITags()
	{
		if (m_ManualUITagsConfigQuery.IsEmptyIgnoreFilter)
		{
			return null;
		}
		Entity singletonEntity = m_ManualUITagsConfigQuery.GetSingletonEntity();
		ManualUITagsConfiguration prefab = m_PrefabSystem.GetPrefab<ManualUITagsConfiguration>(singletonEntity);
		Dictionary<string, string> dictionary = new Dictionary<string, string>();
		FieldInfo[] fields = typeof(ManualUITagsConfiguration).GetFields();
		foreach (FieldInfo fieldInfo in fields)
		{
			UITagPrefab uITagPrefab = fieldInfo.GetValue(prefab) as UITagPrefab;
			if (uITagPrefab != null)
			{
				string key = fieldInfo.Name[2].ToString().ToLower() + fieldInfo.Name.Remove(0, 3);
				dictionary[key] = uITagPrefab.uiTag;
			}
		}
		return dictionary;
	}
```

- `private BindMilestoneRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindMilestoneRequirement(IJsonWriter binder, Entity entity)
	{
		MilestoneData componentData = base.EntityManager.GetComponentData<MilestoneData>(entity);
		bool value = base.EntityManager.HasEnabledComponent<Locked>(entity);
		binder.TypeBegin("prefabs.MilestoneRequirement");
		binder.PropertyName("entity");
		binder.Write(entity);
		binder.PropertyName("index");
		binder.Write(componentData.m_Index);
		binder.PropertyName("locked");
		binder.Write(value);
		binder.TypeEnd();
	}
```

- `private BindObjectBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.StrictObjectBuiltRequirementPrefab prefab) : System.Void`  

```csharp
private void BindObjectBuiltRequirement(IJsonWriter binder, Entity entity, StrictObjectBuiltRequirementPrefab prefab)
	{
		binder.TypeBegin("prefabs.StrictObjectBuiltRequirement");
		BindUnlockRequirementProperties(binder, entity, prefab);
		binder.PropertyName("icon");
		binder.Write(ImageSystem.GetThumbnail(prefab.m_Requirement) ?? m_ImageSystem.placeholderIcon);
		binder.PropertyName("requirement");
		binder.Write(prefab.m_Requirement.name);
		binder.PropertyName("minimumCount");
		binder.Write(prefab.m_MinimumCount);
		binder.PropertyName("isUpgrade");
		binder.Write(prefab.m_Requirement.Has<Game.Prefabs.ServiceUpgrade>());
		binder.TypeEnd();
	}
```

- `private BindOnBuildRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ObjectBuiltRequirementPrefab prefab) : System.Void`  

```csharp
private void BindOnBuildRequirement(IJsonWriter binder, Entity entity, ObjectBuiltRequirementPrefab prefab)
	{
		binder.TypeBegin("prefabs.ObjectBuiltRequirement");
		BindUnlockRequirementProperties(binder, entity, prefab);
		binder.PropertyName("name");
		binder.Write(prefab.name);
		binder.PropertyName("minimumCount");
		binder.Write(prefab.m_MinimumCount);
		binder.TypeEnd();
	}
```

- `private BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public void BindPrefabDetails(IJsonWriter writer, Entity entity, bool unique, bool placed)
	{
		if (!m_Initialized)
		{
			writer.WriteNull();
			return;
		}
		Entity entity2 = entity;
		if (base.EntityManager.HasComponent<NetData>(entity2) && base.EntityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<SubObject> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				SubObject subObject = buffer[i];
				if ((subObject.m_Flags & SubObjectFlags.MakeOwner) != 0)
				{
					entity2 = subObject.m_Prefab;
					break;
				}
			}
		}
		if (base.EntityManager.Exists(entity) && base.EntityManager.TryGetEnabledComponent<PrefabData>(entity2, out var component) && base.EntityManager.TryGetEnabledComponent<PrefabData>(entity, out var component2))
		{
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(component2);
			PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(component);
			GetTitleAndDescription(entity2, out var titleId, out var descriptionId);
			string contentPrerequisite = PrefabUtils.GetContentPrerequisite(prefab);
			writer.TypeBegin("prefabs.PrefabDetails");
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("uiTag");
			writer.Write(prefab.uiTag);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetThumbnail(prefab) ?? m_ImageSystem.placeholderIcon);
			writer.PropertyName("dlc");
			if (contentPrerequisite != null)
			{
				writer.Write("Media/DLC/" + contentPrerequisite + ".svg");
			}
			else
			{
				writer.WriteNull();
			}
			writer.PropertyName("preview");
			writer.Write(prefab2.TryGet<SignatureBuilding>(out var component3) ? component3.m_UnlockEventImage : null);
			writer.PropertyName("titleId");
			writer.Write(titleId);
			writer.PropertyName("descriptionId");
			writer.Write(descriptionId);
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(entity));
			writer.PropertyName("unique");
			writer.Write(unique);
			writer.PropertyName("placed");
			writer.Write(placed);
			writer.PropertyName("constructionCost");
			BindConstructionCost(writer, entity2);
			writer.PropertyName("effects");
			BindEffects(writer, entity2);
			writer.PropertyName("properties");
			BindProperties(writer, entity2);
			writer.PropertyName("requirements");
			BindPrefabRequirements(writer, entity);
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `public BindPrefabDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed) : System.Void`  

```csharp
public void BindPrefabDetails(IJsonWriter writer, Entity entity, bool unique, bool placed)
	{
		if (!m_Initialized)
		{
			writer.WriteNull();
			return;
		}
		Entity entity2 = entity;
		if (base.EntityManager.HasComponent<NetData>(entity2) && base.EntityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<SubObject> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				SubObject subObject = buffer[i];
				if ((subObject.m_Flags & SubObjectFlags.MakeOwner) != 0)
				{
					entity2 = subObject.m_Prefab;
					break;
				}
			}
		}
		if (base.EntityManager.Exists(entity) && base.EntityManager.TryGetEnabledComponent<PrefabData>(entity2, out var component) && base.EntityManager.TryGetEnabledComponent<PrefabData>(entity, out var component2))
		{
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(component2);
			PrefabBase prefab2 = m_PrefabSystem.GetPrefab<PrefabBase>(component);
			GetTitleAndDescription(entity2, out var titleId, out var descriptionId);
			string contentPrerequisite = PrefabUtils.GetContentPrerequisite(prefab);
			writer.TypeBegin("prefabs.PrefabDetails");
			writer.PropertyName("entity");
			writer.Write(entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("uiTag");
			writer.Write(prefab.uiTag);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetThumbnail(prefab) ?? m_ImageSystem.placeholderIcon);
			writer.PropertyName("dlc");
			if (contentPrerequisite != null)
			{
				writer.Write("Media/DLC/" + contentPrerequisite + ".svg");
			}
			else
			{
				writer.WriteNull();
			}
			writer.PropertyName("preview");
			writer.Write(prefab2.TryGet<SignatureBuilding>(out var component3) ? component3.m_UnlockEventImage : null);
			writer.PropertyName("titleId");
			writer.Write(titleId);
			writer.PropertyName("descriptionId");
			writer.Write(descriptionId);
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(entity));
			writer.PropertyName("unique");
			writer.Write(unique);
			writer.PropertyName("placed");
			writer.Write(placed);
			writer.PropertyName("constructionCost");
			BindConstructionCost(writer, entity2);
			writer.PropertyName("effects");
			BindEffects(writer, entity2);
			writer.PropertyName("properties");
			BindProperties(writer, entity2);
			writer.PropertyName("requirements");
			BindPrefabRequirements(writer, entity);
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `public BindPrefabRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public void BindPrefabRequirements(IJsonWriter writer, Entity prefabEntity)
	{
		if (base.EntityManager.HasComponent<UIGroupElement>(prefabEntity))
		{
			BindUIGroupRequirements(writer, prefabEntity);
		}
		else
		{
			BindRequirements(writer, prefabEntity);
		}
	}
```

- `private BindPrefabUnlockedRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.PrefabUnlockedRequirementPrefab prefab) : System.Void`  

```csharp
private void BindPrefabUnlockedRequirement(IJsonWriter binder, Entity entity, PrefabUnlockedRequirementPrefab prefab)
	{
		binder.TypeBegin("prefabs.PrefabUnlockedRequirement");
		BindUnlockRequirementProperties(binder, entity, prefab);
		binder.TypeEnd();
	}
```

- `private BindProcessingRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ProcessingRequirementPrefab prefab) : System.Void`  

```csharp
private void BindProcessingRequirement(IJsonWriter binder, Entity entity, ProcessingRequirementPrefab prefab)
	{
		binder.TypeBegin("prefabs.ProcessingRequirement");
		BindUnlockRequirementProperties(binder, entity, prefab);
		binder.PropertyName("icon");
		binder.Write(ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon);
		binder.PropertyName("resourceType");
		binder.Write(Enum.GetName(typeof(ResourceInEditor), prefab.m_ResourceType));
		binder.PropertyName("minimumProducedAmount");
		binder.Write(prefab.m_MinimumProducedAmount);
		binder.TypeEnd();
	}
```

- `public BindProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
public void BindProperties(IJsonWriter binder, Entity prefabEntity)
	{
		int num = 0;
		foreach (IPrefabPropertyBinder propertyBinder in propertyBinders)
		{
			if (propertyBinder.Matches(base.EntityManager, prefabEntity))
			{
				num++;
			}
		}
		binder.ArrayBegin(num);
		foreach (IPrefabPropertyBinder propertyBinder2 in propertyBinders)
		{
			if (propertyBinder2.Matches(base.EntityManager, prefabEntity))
			{
				propertyBinder2.Bind(binder, base.EntityManager, prefabEntity);
			}
		}
		binder.ArrayEnd();
	}
```

- `private BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
private void BindRequirements(IJsonWriter writer, UnlockFlags flag, Entity milestone, NativeParallelHashMap<Entity, UnlockFlags> devTreeNodes, NativeParallelHashMap<Entity, UnlockFlags> unlockRequirements)
	{
		NativeList<Entity> nativeList = new NativeList<Entity>(2, Allocator.TempJob);
		NativeList<Entity> nativeList2 = new NativeList<Entity>(4, Allocator.TempJob);
		foreach (KeyValue<Entity, UnlockFlags> item in devTreeNodes)
		{
			if ((item.Value & flag) != 0)
			{
				nativeList.Add(item.Key);
			}
		}
		for (int i = 0; i < nativeList.Length; i++)
		{
			devTreeNodes.Remove(nativeList[i]);
		}
		foreach (KeyValue<Entity, UnlockFlags> item2 in unlockRequirements)
		{
			if ((item2.Value & flag) != 0)
			{
				nativeList2.Add(item2.Key);
			}
		}
		for (int j = 0; j < nativeList2.Length; j++)
		{
			unlockRequirements.Remove(nativeList2[j]);
		}
		writer.PropertyName((flag == UnlockFlags.RequireAll) ? "requireAll" : "requireAny");
		writer.ArrayBegin(((milestone != Entity.Null) ? 1 : 0) + nativeList.Length + nativeList2.Length);
		if (milestone != Entity.Null)
		{
			BindMilestoneRequirement(writer, milestone);
		}
		for (int k = 0; k < nativeList.Length; k++)
		{
			BindDevTreeNodeRequirement(writer, nativeList[k]);
		}
		for (int l = 0; l < nativeList2.Length; l++)
		{
			BindUnlockRequirement(writer, nativeList2[l]);
		}
		writer.ArrayEnd();
		nativeList.Dispose();
		nativeList2.Dispose();
	}
```

- `private BindRequirements(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UnlockFlags flag, Unity.Entities.Entity milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

```csharp
private void BindRequirements(IJsonWriter writer, UnlockFlags flag, Entity milestone, NativeParallelHashMap<Entity, UnlockFlags> devTreeNodes, NativeParallelHashMap<Entity, UnlockFlags> unlockRequirements)
	{
		NativeList<Entity> nativeList = new NativeList<Entity>(2, Allocator.TempJob);
		NativeList<Entity> nativeList2 = new NativeList<Entity>(4, Allocator.TempJob);
		foreach (KeyValue<Entity, UnlockFlags> item in devTreeNodes)
		{
			if ((item.Value & flag) != 0)
			{
				nativeList.Add(item.Key);
			}
		}
		for (int i = 0; i < nativeList.Length; i++)
		{
			devTreeNodes.Remove(nativeList[i]);
		}
		foreach (KeyValue<Entity, UnlockFlags> item2 in unlockRequirements)
		{
			if ((item2.Value & flag) != 0)
			{
				nativeList2.Add(item2.Key);
			}
		}
		for (int j = 0; j < nativeList2.Length; j++)
		{
			unlockRequirements.Remove(nativeList2[j]);
		}
		writer.PropertyName((flag == UnlockFlags.RequireAll) ? "requireAll" : "requireAny");
		writer.ArrayBegin(((milestone != Entity.Null) ? 1 : 0) + nativeList.Length + nativeList2.Length);
		if (milestone != Entity.Null)
		{
			BindMilestoneRequirement(writer, milestone);
		}
		for (int k = 0; k < nativeList.Length; k++)
		{
			BindDevTreeNodeRequirement(writer, nativeList[k]);
		}
		for (int l = 0; l < nativeList2.Length; l++)
		{
			BindUnlockRequirement(writer, nativeList2[l]);
		}
		writer.ArrayEnd();
		nativeList.Dispose();
		nativeList2.Dispose();
	}
```

- `private BindThemes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindThemes(IJsonWriter writer)
	{
		NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(m_ThemeQuery, Allocator.TempJob);
		writer.ArrayBegin(sortedObjects.Length);
		for (int i = 0; i < sortedObjects.Length; i++)
		{
			ThemePrefab prefab = m_PrefabSystem.GetPrefab<ThemePrefab>(sortedObjects[i].prefabData);
			writer.TypeBegin("prefabs.Theme");
			writer.PropertyName("entity");
			writer.Write(sortedObjects[i].entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		sortedObjects.Dispose();
	}
```

- `private BindTutorialRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindTutorialRequirement(IJsonWriter binder, Entity entity)
	{
		binder.TypeBegin("prefabs.TutorialRequirement");
		binder.PropertyName("entity");
		binder.Write(entity);
		binder.PropertyName("locked");
		binder.Write(value: true);
		binder.TypeEnd();
	}
```

- `private BindUIGroupRequirements(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity prefabEntity) : System.Void`  

```csharp
private void BindUIGroupRequirements(IJsonWriter writer, Entity prefabEntity)
	{
		if (base.EntityManager.TryGetComponent<ForceUnlockRequirementData>(prefabEntity, out var component))
		{
			BindRequirements(writer, component.m_Prefab);
			return;
		}
		NativeList<Entity> requirements = new NativeList<Entity>(4, Allocator.TempJob);
		NativeList<UnlockRequirement> list = new NativeList<UnlockRequirement>(4, Allocator.TempJob);
		FindLowestRequirements(prefabEntity, requirements);
		if (requirements.Length > 1)
		{
			DynamicBuffer<UnlockRequirement> buffer = base.EntityManager.GetBuffer<UnlockRequirement>(m_RequirementEntity);
			for (int i = 0; i < requirements.Length; i++)
			{
				Entity entity = requirements[i];
				if (!base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<UnlockRequirement> buffer2))
				{
					continue;
				}
				for (int j = 0; j < buffer2.Length; j++)
				{
					if (buffer2[j].m_Prefab != entity && !list.Contains(buffer2[j]))
					{
						list.Add(buffer2[j]);
						buffer.Add(new UnlockRequirement
						{
							m_Prefab = buffer2[j].m_Prefab,
							m_Flags = UnlockFlags.RequireAny
						});
					}
				}
			}
			BindRequirements(writer, m_RequirementEntity);
			buffer.Clear();
		}
		else if (requirements.Length > 0)
		{
			BindRequirements(writer, requirements[0]);
		}
		else
		{
			BindRequirements(writer, m_RequirementEntity);
		}
		requirements.Dispose();
		list.Dispose();
	}
```

- `private BindUnknownUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab) : System.Void`  

```csharp
private void BindUnknownUnlockRequirement(IJsonWriter binder, Entity entity, UnlockRequirementPrefab prefab)
	{
		binder.TypeBegin("prefabs.UnlockRequirement");
		BindUnlockRequirementProperties(binder, entity, prefab);
		binder.TypeEnd();
	}
```

- `private BindUnlockRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void BindUnlockRequirement(IJsonWriter binder, Entity entity)
	{
		if (entity == m_TutorialRequirementEntity)
		{
			BindTutorialRequirement(binder, entity);
			return;
		}
		PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(entity);
		if (prefab is StrictObjectBuiltRequirementPrefab prefab2)
		{
			BindObjectBuiltRequirement(binder, entity, prefab2);
		}
		else if (prefab is ZoneBuiltRequirementPrefab prefab3)
		{
			BindZoneBuiltRequirement(binder, entity, prefab3);
		}
		else if (prefab is CitizenRequirementPrefab cr)
		{
			BindCitizenRequirement(binder, entity, cr);
		}
		else if (prefab is ProcessingRequirementPrefab prefab4)
		{
			BindProcessingRequirement(binder, entity, prefab4);
		}
		else if (prefab is ObjectBuiltRequirementPrefab prefab5)
		{
			BindOnBuildRequirement(binder, entity, prefab5);
		}
		else if (prefab is PrefabUnlockedRequirementPrefab prefab6)
		{
			BindPrefabUnlockedRequirement(binder, entity, prefab6);
		}
		else if (prefab is UnlockRequirementPrefab prefab7)
		{
			BindUnknownUnlockRequirement(binder, entity, prefab7);
		}
	}
```

- `private BindUnlockRequirementProperties(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.UnlockRequirementPrefab prefab) : System.Void`  

```csharp
private void BindUnlockRequirementProperties(IJsonWriter binder, Entity entity, UnlockRequirementPrefab prefab)
	{
		UnlockRequirementData componentData = base.EntityManager.GetComponentData<UnlockRequirementData>(entity);
		bool value = base.EntityManager.HasEnabledComponent<Locked>(entity);
		binder.PropertyName("entity");
		binder.Write(entity);
		binder.PropertyName("labelId");
		binder.Write((!string.IsNullOrEmpty(prefab.m_LabelID)) ? prefab.m_LabelID : null);
		binder.PropertyName("progress");
		binder.Write(componentData.m_Progress);
		binder.PropertyName("locked");
		binder.Write(value);
	}
```

- `private BindZoneBuiltRequirement(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.Prefabs.ZoneBuiltRequirementPrefab prefab) : System.Void`  

```csharp
private void BindZoneBuiltRequirement(IJsonWriter binder, Entity entity, ZoneBuiltRequirementPrefab prefab)
	{
		binder.TypeBegin("prefabs.ZoneBuiltRequirement");
		BindUnlockRequirementProperties(binder, entity, prefab);
		binder.PropertyName("icon");
		bool flag = m_PrefabSystem.HasComponent<UIObjectData>(prefab.m_RequiredZone);
		binder.Write(ImageSystem.GetIcon((PrefabBase)(flag ? (((object)prefab.m_RequiredZone) ?? ((object)prefab)) : prefab)) ?? m_ImageSystem.placeholderIcon);
		binder.PropertyName("requiredTheme");
		binder.Write(prefab.m_RequiredTheme?.name);
		binder.PropertyName("requiredZone");
		binder.Write(prefab.m_RequiredZone?.name);
		binder.PropertyName("requiredType");
		binder.Write((int)prefab.m_RequiredType);
		binder.PropertyName("minimumSquares");
		binder.Write(prefab.m_MinimumSquares);
		binder.PropertyName("minimumCount");
		binder.Write(prefab.m_MinimumCount);
		binder.PropertyName("minimumLevel");
		binder.Write(prefab.m_MinimumLevel);
		binder.TypeEnd();
	}
```

- `private static BuildDefaultConstructionCostBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder>`  

```csharp
private static List<IPrefabPropertyBinder> BuildDefaultConstructionCostBinders()
	{
		return new List<IPrefabPropertyBinder>
		{
			new ConstructionCostBinder(),
			new ComponentInt2PropertyBinder<PlaceableNetData>("Common.ASSET_CONSTRUCTION_COST", "moneyPerDistance", (PlaceableNetData data) => new int2(Convert.ToInt32(data.m_DefaultConstructionCost), Convert.ToInt32(data.m_DefaultConstructionCost) * 125)),
			new ComponentIntPropertyBinder<ServiceUpgradeData>("Properties.CONSTRUCTION_COST", "money", (ServiceUpgradeData data) => Convert.ToInt32(data.m_UpgradeCost))
		};
	}
```

- `private static BuildDefaultEffectBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder>`  

```csharp
private static List<IPrefabEffectBinder> BuildDefaultEffectBinders()
	{
		return new List<IPrefabEffectBinder>
		{
			new CityModifierBinder(),
			new LocalModifierBinder(),
			new LeisureProviderBinder()
		};
	}
```

- `private BuildDefaultPropertyBinders() : System.Collections.Generic.List<Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder>`  

```csharp
private List<IPrefabPropertyBinder> BuildDefaultPropertyBinders()
	{
		return new List<IPrefabPropertyBinder>
		{
			new RequiredResourceBinder(base.World.GetOrCreateSystemManaged<ResourceSystem>()),
			base.World.GetOrCreateSystemManaged<UpkeepPropertyBinderSystem>(),
			new ComponentIntPropertyBinder<AssetStampData>("Properties.UPKEEP", "moneyPerMonth", (AssetStampData data) => (int)data.m_UpKeepCost),
			new ComponentIntPropertyBinder<PlaceableNetData>("Properties.UPKEEP", "moneyPerDistancePerMonth", (PlaceableNetData data) => Convert.ToInt32(data.m_DefaultUpkeepCost) * 125),
			new PowerProductionBinder(),
			new ComponentIntPropertyBinder<BatteryData>("Properties.BATTERY_CAPACITY", "energy", (BatteryData data) => data.m_Capacity),
			new ComponentIntPropertyBinder<BatteryData>("Properties.BATTERY_POWER_OUTPUT", "power", (BatteryData data) => data.m_PowerOutput),
			new TransformerCapacityBinder(),
			new TransformerInputBinder(),
			new TransformerOutputBinder(),
			new ElectricityConnectionBinder(),
			new WaterConnectionBinder(),
			new ComponentIntPropertyBinder<SewageOutletData>("Properties.SEWAGE_CAPACITY", "volumePerMonth", (SewageOutletData data) => data.m_Capacity),
			new ComponentIntPropertyBinder<SewageOutletData>("Properties.SEWAGE_PURIFICATION_RATE", "percentage", (SewageOutletData data) => Mathf.RoundToInt(100f * data.m_Purification)),
			new ComponentIntPropertyBinder<WaterPumpingStationData>("Properties.WATER_CAPACITY", "volumePerMonth", (WaterPumpingStationData data) => data.m_Capacity),
			new ComponentIntPropertyBinder<WaterPumpingStationData>("Properties.WATER_PURIFICATION_RATE", "percentage", (WaterPumpingStationData data) => Mathf.RoundToInt(100f * data.m_Purification)),
			new ComponentIntPropertyBinder<HospitalData>("Properties.PATIENT_CAPACITY", "integer", (HospitalData data) => data.m_PatientCapacity),
			new ComponentIntPropertyBinder<HospitalData>("Properties.AMBULANCE_COUNT", "integer", (HospitalData data) => data.m_AmbulanceCapacity),
			new ComponentIntPropertyBinder<HospitalData>("Properties.MEDICAL_HELICOPTER_COUNT", "integer", (HospitalData data) => data.m_MedicalHelicopterCapacity),
			new ComponentIntPropertyBinder<DeathcareFacilityData>("Properties.DECEASED_PROCESSING_CAPACITY", "integerPerMonth", (DeathcareFacilityData data) => Mathf.CeilToInt(data.m_ProcessingRate)),
			new ComponentIntPropertyBinder<DeathcareFacilityData>("Properties.DECEASED_STORAGE", "integer", (DeathcareFacilityData data) => data.m_StorageCapacity),
			new ComponentIntPropertyBinder<DeathcareFacilityData>("Properties.HEARSE_COUNT", "integer", (DeathcareFacilityData data) => data.m_HearseCapacity),
			new ComponentIntPropertyBinder<GarbageFacilityData>("Properties.GARBAGE_PROCESSING_CAPACITY", "weightPerMonth", (GarbageFacilityData data) => data.m_ProcessingSpeed),
			new ComponentIntPropertyBinder<GarbageFacilityData>("Properties.GARBAGE_STORAGE", "weight", (GarbageFacilityData data) => data.m_GarbageCapacity),
			new ComponentIntPropertyBinder<StorageAreaData>("Properties.GARBAGE_STORAGE", "weightPerCell", (StorageAreaData data) => data.m_Capacity * 1000),
			new ComponentIntPropertyBinder<GarbageFacilityData>("Properties.GARBAGE_TRUCK_COUNT", "integer", (GarbageFacilityData data) => data.m_VehicleCapacity),
			new ComponentIntPropertyBinder<FireStationData>("Properties.FIRE_ENGINE_COUNT", "integer", (FireStationData data) => data.m_FireEngineCapacity),
			new ComponentIntPropertyBinder<FireStationData>("Properties.FIRE_HELICOPTER_COUNT", "integer", (FireStationData data) => data.m_FireHelicopterCapacity),
			new ComponentIntPropertyBinder<EmergencyShelterData>("Properties.SHELTER_CAPACITY", "integer", (EmergencyShelterData data) => data.m_ShelterCapacity),
			new ComponentIntPropertyBinder<EmergencyShelterData>("Properties.EVACUATION_BUS_COUNT", "integer", (EmergencyShelterData data) => data.m_VehicleCapacity),
			new JailCapacityBinder(),
			new ComponentIntPropertyBinder<PoliceStationData>("Properties.PATROL_CAR_COUNT", "integer", (PoliceStationData data) => data.m_PatrolCarCapacity),
			new ComponentIntPropertyBinder<PoliceStationData>("Properties.POLICE_HELICOPTER_COUNT", "integer", (PoliceStationData data) => data.m_PoliceHelicopterCapacity),
			new ComponentIntPropertyBinder<PrisonData>("Properties.PRISON_VAN_COUNT", "integer", (PrisonData data) => data.m_PrisonVanCapacity),
			new ComponentIntPropertyBinder<SchoolData>("Properties.STUDENT_CAPACITY", "integer", (SchoolData data) => data.m_StudentCapacity),
			new ComponentIntPropertyBinder<TransportDepotData>("Properties.TRANSPORT_VEHICLE_COUNT", "integer", (TransportDepotData data) => data.m_VehicleCapacity),
			new TransportStopBinder(),
			new ComponentIntPropertyBinder<MaintenanceDepotData>("Properties.MAINTENANCE_VEHICLES", "integer", (MaintenanceDepotData data) => data.m_VehicleCapacity),
			new ComponentIntPropertyBinder<PostFacilityData>("Properties.MAIL_SORTING_RATE", "integerPerMonth", (PostFacilityData data) => data.m_SortingRate),
			new ComponentIntPropertyBinder<PostFacilityData>("Properties.MAIL_STORAGE_CAPACITY", "integer", (PostFacilityData data) => data.m_MailCapacity),
			new ComponentIntPropertyBinder<MailBoxData>("Properties.MAIL_BOX_CAPACITY", "integer", (MailBoxData data) => data.m_MailCapacity),
			new ComponentIntPropertyBinder<PostFacilityData>("Properties.POST_VAN_COUNT", "integer", (PostFacilityData data) => data.m_PostVanCapacity),
			new ComponentIntPropertyBinder<PostFacilityData>("Properties.POST_TRUCK_COUNT", "integer", (PostFacilityData data) => data.m_PostTruckCapacity),
			new ComponentIntPropertyBinder<TelecomFacilityData>("Properties.NETWORK_RANGE", "length", (TelecomFacilityData data) => Mathf.CeilToInt(data.m_Range)),
			new ComponentIntPropertyBinder<TelecomFacilityData>("Properties.NETWORK_CAPACITY", "dataRate", (TelecomFacilityData data) => Mathf.CeilToInt(data.m_NetworkCapacity)),
			new ComponentIntPropertyBinder<AttractionData>("Properties.ATTRACTIVENESS", "integer", (AttractionData data) => data.m_Attractiveness),
			new UpkeepModifierBinder(),
			new StorageLimitBinder(),
			new PollutionBinder(m_PrefabSystem.GetSingletonPrefab<UIPollutionConfigurationPrefab>(m_PollutionConfigQuery)),
			new ComponentIntPropertyBinder<PollutionModifierData>("SelectedInfoPanel.POLLUTION_LEVELS_GROUND", "percentage", (PollutionModifierData data) => Mathf.RoundToInt(data.m_GroundPollutionMultiplier * 100f), omitZero: true, signed: true, null, "Media/Game/Icons/GroundPollution.svg"),
			new ComponentIntPropertyBinder<PollutionModifierData>("SelectedInfoPanel.POLLUTION_LEVELS_AIR", "percentage", (PollutionModifierData data) => Mathf.RoundToInt(data.m_AirPollutionMultiplier * 100f), omitZero: true, signed: true, null, "Media/Game/Icons/AirPollution.svg"),
			new ComponentIntPropertyBinder<PollutionModifierData>("SelectedInfoPanel.POLLUTION_LEVELS_NOISE", "percentage", (PollutionModifierData data) => Mathf.RoundToInt(data.m_NoisePollutionMultiplier * 100f), omitZero: true, signed: true, null, "Media/Game/Icons/NoisePollution.svg"),
			new ComponentIntPropertyBinder<ParkingFacilityData>("Properties.COMFORT", "integer", (ParkingFacilityData data) => (int)math.round(100f * data.m_ComfortFactor)),
			new ComponentIntPropertyBinder<TransportStopData>("Properties.COMFORT", "integer", (TransportStopData data) => (int)math.round(100f * data.m_ComfortFactor)),
			new ComponentIntPropertyBinder<TransportStationData>("Properties.COMFORT", "integer", (TransportStationData data) => (int)math.round(100f * data.m_ComfortFactor))
		};
	}
```

- `private FindLowestRequirements(Unity.Entities.Entity prefabEntity, Unity.Collections.NativeList<Unity.Entities.Entity> requirements, System.Int32 score = -1) : System.Int32`  

```csharp
private int FindLowestRequirements(Entity prefabEntity, NativeList<Entity> requirements, int score = -1)
	{
		NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(base.EntityManager, base.EntityManager.GetBuffer<UIGroupElement>(prefabEntity, isReadOnly: true), Allocator.TempJob);
		NativeParallelHashMap<Entity, UnlockFlags> devTreeNodes = new NativeParallelHashMap<Entity, UnlockFlags>(10, Allocator.TempJob);
		NativeParallelHashMap<Entity, UnlockFlags> unlockRequirements = new NativeParallelHashMap<Entity, UnlockFlags>(10, Allocator.TempJob);
		foreach (UIObjectInfo item in sortedObjects)
		{
			if (base.EntityManager.HasComponent<UIGroupElement>(item.entity))
			{
				int num = FindLowestRequirements(item.entity, requirements, score);
				if ((requirements.Length > 0 && score == -1) || num < score)
				{
					score = num;
				}
				continue;
			}
			GetRequirements(item.entity, out var milestone, devTreeNodes, unlockRequirements);
			int num2 = 0;
			if (milestone != Entity.Null)
			{
				num2 += base.EntityManager.GetComponentData<MilestoneData>(milestone).m_Index * 10000;
			}
			foreach (KeyValue<Entity, UnlockFlags> item2 in devTreeNodes)
			{
				DevTreeNodePrefab prefab = m_PrefabSystem.GetPrefab<DevTreeNodePrefab>(item2.Key);
				num2 += prefab.m_HorizontalPosition * 100;
			}
			num2 += unlockRequirements.Count() * 10;
			foreach (KeyValue<Entity, UnlockFlags> item3 in unlockRequirements)
			{
				if (base.EntityManager.HasComponent<UnlockRequirementData>(item3.Key))
				{
					UnlockRequirementPrefab prefab2 = m_PrefabSystem.GetPrefab<UnlockRequirementPrefab>(item3.Key);
					num2 = ((prefab2 is ZoneBuiltRequirementPrefab zoneBuiltRequirementPrefab) ? (num2 + (zoneBuiltRequirementPrefab.m_MinimumLevel * zoneBuiltRequirementPrefab.m_MinimumCount + zoneBuiltRequirementPrefab.m_MinimumSquares / 100)) : ((prefab2 is CitizenRequirementPrefab citizenRequirementPrefab) ? (num2 + (citizenRequirementPrefab.m_MinimumPopulation / 10 + citizenRequirementPrefab.m_MinimumHappiness * 100)) : ((!(prefab2 is ProcessingRequirementPrefab processingRequirementPrefab)) ? (num2 + 100) : (num2 + processingRequirementPrefab.m_MinimumProducedAmount / 10))));
				}
				else
				{
					num2 += 10;
				}
			}
			if ((item.entity != Entity.Null && !requirements.Contains(item.entity) && score == -1) || num2 <= score)
			{
				if (num2 < score)
				{
					requirements.Clear();
				}
				requirements.Add(item.entity);
				score = num2;
			}
		}
		sortedObjects.Dispose();
		devTreeNodes.Dispose();
		unlockRequirements.Dispose();
		return score;
	}
```

- `private GetRequirements(Unity.Entities.Entity prefabEntity, Unity.Entities.Entity& milestone, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

```csharp
private void GetRequirements(Entity prefabEntity, out Entity milestone, NativeParallelHashMap<Entity, UnlockFlags> devTreeNodes, NativeParallelHashMap<Entity, UnlockFlags> unlockRequirements)
	{
		NativeParallelHashMap<Entity, UnlockFlags> requiredPrefabs = new NativeParallelHashMap<Entity, UnlockFlags>(10, Allocator.TempJob);
		ProgressionUtils.CollectSubRequirements(base.EntityManager, prefabEntity, requiredPrefabs);
		milestone = Entity.Null;
		int num = -1;
		devTreeNodes.Clear();
		unlockRequirements.Clear();
		foreach (KeyValue<Entity, UnlockFlags> item in requiredPrefabs)
		{
			if (base.EntityManager.TryGetComponent<MilestoneData>(item.Key, out var component) && component.m_Index > num)
			{
				milestone = item.Key;
				num = component.m_Index;
			}
			if (base.EntityManager.HasComponent<DevTreeNodeData>(item.Key))
			{
				if (devTreeNodes.ContainsKey(item.Key))
				{
					devTreeNodes[item.Key] |= item.Value;
				}
				else
				{
					devTreeNodes.Add(item.Key, item.Value);
				}
			}
			if (base.EntityManager.HasComponent<UnlockRequirementData>(item.Key))
			{
				if (unlockRequirements.ContainsKey(item.Key))
				{
					unlockRequirements[item.Key] |= item.Value;
				}
				else
				{
					unlockRequirements.Add(item.Key, item.Value);
				}
			}
			if ((base.EntityManager.HasComponent<TutorialData>(item.Key) || base.EntityManager.HasComponent<TutorialPhaseData>(item.Key) || base.EntityManager.HasComponent<TutorialTriggerData>(item.Key) || base.EntityManager.HasComponent<TutorialListData>(item.Key)) && base.EntityManager.HasEnabledComponent<Locked>(item.Key))
			{
				if (unlockRequirements.ContainsKey(m_TutorialRequirementEntity))
				{
					unlockRequirements[m_TutorialRequirementEntity] |= item.Value;
				}
				else
				{
					unlockRequirements.Add(m_TutorialRequirementEntity, item.Value);
				}
			}
		}
		requiredPrefabs.Dispose();
	}
```

- `public GetTitleAndDescription(Unity.Entities.Entity prefabEntity, System.String& titleId, System.String& descriptionId) : System.Void`  

```csharp
public void GetTitleAndDescription(Entity prefabEntity, out string titleId, [CanBeNull] out string descriptionId)
	{
		if (m_PrefabSystem.TryGetPrefab<PrefabBase>(prefabEntity, out var prefab))
		{
			if (prefab is UIAssetMenuPrefab || prefab is ServicePrefab)
			{
				titleId = "Services.NAME[" + prefab.name + "]";
				descriptionId = "Services.DESCRIPTION[" + prefab.name + "]";
			}
			else if (prefab is UIAssetCategoryPrefab)
			{
				titleId = "SubServices.NAME[" + prefab.name + "]";
				descriptionId = "Assets.SUB_SERVICE_DESCRIPTION[" + prefab.name + "]";
			}
			else if (prefab.Has<Game.Prefabs.ServiceUpgrade>())
			{
				titleId = "Assets.UPGRADE_NAME[" + prefab.name + "]";
				descriptionId = "Assets.UPGRADE_DESCRIPTION[" + prefab.name + "]";
			}
			else
			{
				titleId = "Assets.NAME[" + prefab.name + "]";
				descriptionId = "Assets.DESCRIPTION[" + prefab.name + "]";
			}
		}
		else
		{
			titleId = m_PrefabSystem.GetObsoleteID(prefabEntity).GetName();
			descriptionId = "Assets.MISSING_PREFAB_DESCRIPTION";
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UniqueAssetTrackingSystem = base.World.GetOrCreateSystemManaged<UniqueAssetTrackingSystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_RequirementEntity = base.EntityManager.CreateEntity();
		base.EntityManager.AddBuffer<UnlockRequirement>(m_RequirementEntity);
		m_TutorialRequirementEntity = base.EntityManager.CreateEntity();
		m_ThemeQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<UIObjectData>(), ComponentType.ReadOnly<ThemeData>());
		m_ModifiedThemeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<ThemeData>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UnlockedPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_PollutionConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UIPollutionConfigurationData>());
		m_ManualUITagsConfigQuery = GetEntityQuery(ComponentType.ReadOnly<ManualUITagsConfigurationData>());
		AddBinding(m_ThemesBinding = new RawValueBinding("prefabs", "themes", BindThemes));
		AddBinding(m_PrefabDetailsBinding = new RawMapBinding<Entity>("prefabs", "prefabDetails", BindPrefabDetails));
		AddBinding(m_UITagsBinding = new GetterValueBinding<Dictionary<string, string>>("prefabs", "manualUITags", BindManualUITags, ValueWriters.Nullable(new DictionaryWriter<string, string>())));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (base.Enabled)
		{
			m_Initialized = true;
			constructionCostBinders = BuildDefaultConstructionCostBinders();
			propertyBinders = BuildDefaultPropertyBinders();
			effectBinders = BuildDefaultEffectBinders();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ModifiedThemeQuery.IsEmptyIgnoreFilter)
		{
			m_ThemesBinding.Update();
		}
		int componentOrderVersion = base.EntityManager.GetComponentOrderVersion<UnlockRequirementData>();
		int componentOrderVersion2 = base.EntityManager.GetComponentOrderVersion<ManualUITagsConfigurationData>();
		if (PrefabUtils.HasUnlockedPrefab<UIObjectData>(base.EntityManager, m_UnlockedPrefabQuery) || m_UnlockRequirementVersion != componentOrderVersion)
		{
			m_PrefabDetailsBinding.UpdateAll();
		}
		if (!m_ManualUITagsConfigQuery.IsEmptyIgnoreFilter && componentOrderVersion2 != m_UITagVersion)
		{
			m_UITagsBinding.Update();
		}
		m_UnlockRequirementVersion = componentOrderVersion;
		m_UITagVersion = componentOrderVersion2;
	}
```

- `private VerifyRequirements(Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> devTreeNodes, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> unlockRequirements) : System.Void`  

```csharp
private void VerifyRequirements(NativeParallelHashMap<Entity, UnlockFlags> devTreeNodes, NativeParallelHashMap<Entity, UnlockFlags> unlockRequirements)
	{
		Entity entity = Entity.Null;
		Entity entity2 = Entity.Null;
		int num = 0;
		foreach (KeyValue<Entity, UnlockFlags> item in devTreeNodes)
		{
			if ((item.Value & UnlockFlags.RequireAny) != 0)
			{
				entity = item.Key;
				num++;
			}
		}
		foreach (KeyValue<Entity, UnlockFlags> item2 in unlockRequirements)
		{
			if ((item2.Value & UnlockFlags.RequireAny) != 0)
			{
				entity2 = item2.Key;
				num++;
			}
		}
		if (num == 1)
		{
			if (entity != Entity.Null)
			{
				devTreeNodes[entity] = UnlockFlags.RequireAll;
			}
			if (entity2 != Entity.Null)
			{
				unlockRequirements[entity2] = UnlockFlags.RequireAll;
			}
		}
	}
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

