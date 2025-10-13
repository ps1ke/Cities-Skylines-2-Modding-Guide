# Game.UI.InGame.TutorialsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialsUISystem : Game.UI.UISystemBase
{
    protected Game.Prefabs.PrefabSystem m_PrefabSystem;
    protected Game.Tutorials.ITutorialSystem m_TutorialSystem;
    private Game.Tutorials.ITutorialSystem m_EditorTutorialSystem;
    protected Game.Tutorials.ITutorialUIActivationSystem m_ActivationSystem;
    protected Game.Tutorials.ITutorialUIDeactivationSystem m_DeactivationSystem;
    protected Game.Tutorials.ITutorialUITriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_TutorialConfigurationQuery;
    private Unity.Entities.EntityQuery m_TutorialCategoryQuery;
    protected Unity.Entities.EntityQuery m_UnlockQuery;
    protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialListBinding;
    protected Colossal.UI.Binding.RawValueBinding m_TutorialCategoriesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_TutorialsBinding;
    protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialBinding;
    protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialPhaseBinding;
    private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_TutorialPendingBinding;
    private System.Int32 m_TutorialActiveVersion;
    private System.Int32 m_PhaseActiveVersion;
    private System.Int32 m_TriggerActiveVersion;
    private System.Int32 m_TriggerCompletedVersion;
    private System.Int32 m_TutorialShownVersion;
    private System.Int32 m_PhaseShownVersion;
    private System.Int32 m_PhaseCompletedVersion;
    private System.Boolean m_WasEnabled;
    private Game.UI.InGame.TutorialsUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    public TutorialsUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean <OnCreate>b__25_0();
    private System.Boolean <OnCreate>b__25_1();
    private System.Boolean <OnCreate>b__25_2();
    private System.Boolean <OnCreate>b__25_3();
    private Unity.Entities.Entity <OnCreate>b__25_4();
    private Unity.Entities.Entity <OnCreate>b__25_5();
    private System.Void <OnCreate>b__25_6(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void <OnCreate>b__25_7(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void ActivateTutorial(Unity.Entities.Entity tutorial);
    private System.Void ActivateTutorialPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase);
    private System.Void ActivateTutorialTrigger(System.String trigger);
    private System.Boolean AlternativeCompleted(Unity.Entities.Entity tutorial);
    protected System.Void BindActiveTutorialList(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindCategories(Colossal.UI.Binding.IJsonWriter writer);
    protected System.Void BindTutorial(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity tutorialEntity);
    protected System.Void BindTutorialGroup(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    protected System.Void BindTutorialPhase(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity phaseEntity);
    private System.Void CompleteActiveTutorial();
    protected virtual System.Void CompleteActiveTutorialPhase();
    private System.Void CompleteIntro();
    private System.Void CompleteIntro(System.Boolean tutorialEnabled);
    private System.Void CompleteOutro();
    private System.Void DisactivateTutorialTrigger(System.String trigger);
    private System.Void ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation);
    private static System.String[] GetFilters(Game.Prefabs.TutorialPrefab prefab);
    private Unity.Collections.NativeList<Unity.Entities.Entity> GetListHintTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedCategories(Unity.Collections.Allocator allocator);
    private Unity.Collections.NativeList<Unity.Entities.Entity> GetVisibleListTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator);
    private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    private System.Void OnSetTutorialTagActive(System.String tag, System.Boolean active);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
protected Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `protected Game.Tutorials.ITutorialSystem m_TutorialSystem`  

```csharp
protected Game.Tutorials.ITutorialSystem m_TutorialSystem;
```

- `private Game.Tutorials.ITutorialSystem m_EditorTutorialSystem`  

```csharp
private Game.Tutorials.ITutorialSystem m_EditorTutorialSystem;
```

- `protected Game.Tutorials.ITutorialUIActivationSystem m_ActivationSystem`  

```csharp
protected Game.Tutorials.ITutorialUIActivationSystem m_ActivationSystem;
```

- `protected Game.Tutorials.ITutorialUIDeactivationSystem m_DeactivationSystem`  

```csharp
protected Game.Tutorials.ITutorialUIDeactivationSystem m_DeactivationSystem;
```

- `protected Game.Tutorials.ITutorialUITriggerSystem m_TriggerSystem`  

```csharp
protected Game.Tutorials.ITutorialUITriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_TutorialConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_TutorialCategoryQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialCategoryQuery;
```

- `protected Unity.Entities.EntityQuery m_UnlockQuery`  

```csharp
protected Unity.Entities.EntityQuery m_UnlockQuery;
```

- `protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialListBinding`  

```csharp
protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialListBinding;
```

- `protected Colossal.UI.Binding.RawValueBinding m_TutorialCategoriesBinding`  

```csharp
protected Colossal.UI.Binding.RawValueBinding m_TutorialCategoriesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_TutorialsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_TutorialsBinding;
```

- `protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialBinding`  

```csharp
protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialBinding;
```

- `protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialPhaseBinding`  

```csharp
protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialPhaseBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_TutorialPendingBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_TutorialPendingBinding;
```

- `private System.Int32 m_TutorialActiveVersion`  

```csharp
private System.Int32 m_TutorialActiveVersion;
```

- `private System.Int32 m_PhaseActiveVersion`  

```csharp
private System.Int32 m_PhaseActiveVersion;
```

- `private System.Int32 m_TriggerActiveVersion`  

```csharp
private System.Int32 m_TriggerActiveVersion;
```

- `private System.Int32 m_TriggerCompletedVersion`  

```csharp
private System.Int32 m_TriggerCompletedVersion;
```

- `private System.Int32 m_TutorialShownVersion`  

```csharp
private System.Int32 m_TutorialShownVersion;
```

- `private System.Int32 m_PhaseShownVersion`  

```csharp
private System.Int32 m_PhaseShownVersion;
```

- `private System.Int32 m_PhaseCompletedVersion`  

```csharp
private System.Int32 m_PhaseCompletedVersion;
```

- `private System.Boolean m_WasEnabled`  

```csharp
private System.Boolean m_WasEnabled;
```

- `private Game.UI.InGame.TutorialsUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TutorialsUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public TutorialsUISystem()`  

```csharp
[Preserve]
	public TutorialsUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private <OnCreate>b__25_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__25_0();
```

- `private <OnCreate>b__25_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__25_1();
```

- `private <OnCreate>b__25_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__25_2();
```

- `private <OnCreate>b__25_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__25_3();
```

- `private <OnCreate>b__25_4() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__25_4();
```

- `private <OnCreate>b__25_5() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__25_5();
```

- `private <OnCreate>b__25_6(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__25_6(Colossal.UI.Binding.IJsonWriter writer);
```

- `private <OnCreate>b__25_7(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void <OnCreate>b__25_7(Colossal.UI.Binding.IJsonWriter writer);
```

- `private ActivateTutorial(Unity.Entities.Entity tutorial) : System.Void`  

```csharp
private void ActivateTutorial(Entity tutorial)
	{
		m_TutorialSystem.SetTutorial(tutorial, Entity.Null);
	}
```

- `private ActivateTutorialPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  

```csharp
private void ActivateTutorialPhase(Entity tutorial, Entity phase)
	{
		m_TutorialSystem.SetTutorial(tutorial, phase);
	}
```

- `private ActivateTutorialTrigger(System.String trigger) : System.Void`  

```csharp
private void ActivateTutorialTrigger(string trigger)
	{
		m_TriggerSystem.ActivateTrigger(trigger);
	}
```

- `private AlternativeCompleted(Unity.Entities.Entity tutorial) : System.Boolean`  

```csharp
private bool AlternativeCompleted(Entity tutorial)
	{
		if (base.EntityManager.TryGetBuffer(tutorial, isReadOnly: true, out DynamicBuffer<Game.Tutorials.TutorialAlternative> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				if (base.EntityManager.HasComponent<TutorialCompleted>(buffer[i].m_Alternative))
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `protected BindActiveTutorialList(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected void BindActiveTutorialList(IJsonWriter writer)
	{
		Entity activeTutorialList = m_TutorialSystem.activeTutorialList;
		if (activeTutorialList != Entity.Null)
		{
			TutorialListPrefab prefab = m_PrefabSystem.GetPrefab<TutorialListPrefab>(activeTutorialList);
			NativeList<Entity> visibleListTutorials = GetVisibleListTutorials(activeTutorialList, Allocator.Temp);
			NativeList<Entity> listHintTutorials = GetListHintTutorials(activeTutorialList, Allocator.Temp);
			try
			{
				writer.TypeBegin(TypeNames.kTutorialList);
				writer.PropertyName("entity");
				writer.Write(activeTutorialList);
				writer.PropertyName("name");
				writer.Write(prefab.name);
				writer.PropertyName("tutorials");
				writer.ArrayBegin(visibleListTutorials.Length);
				foreach (Entity item in visibleListTutorials)
				{
					BindTutorial(writer, item);
				}
				writer.ArrayEnd();
				writer.PropertyName("hints");
				writer.ArrayBegin(listHintTutorials.Length);
				foreach (Entity item2 in listHintTutorials)
				{
					BindTutorial(writer, item2);
				}
				writer.ArrayEnd();
				writer.PropertyName("intro");
				writer.Write(m_TutorialSystem.showListReminder);
				writer.TypeEnd();
				return;
			}
			finally
			{
				visibleListTutorials.Dispose();
			}
		}
		writer.WriteNull();
	}
```

- `private BindCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindCategories(IJsonWriter writer)
	{
		NativeList<UIObjectInfo> sortedCategories = GetSortedCategories(Allocator.Temp);
		writer.ArrayBegin(sortedCategories.Length);
		for (int i = 0; i < sortedCategories.Length; i++)
		{
			UIObjectInfo uIObjectInfo = sortedCategories[i];
			UITutorialGroupPrefab prefab = m_PrefabSystem.GetPrefab<UITutorialGroupPrefab>(uIObjectInfo.entity);
			writer.TypeBegin(TypeNames.kAdvisorCategory);
			writer.PropertyName("entity");
			writer.Write(uIObjectInfo.entity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("shown");
			writer.Write(base.EntityManager.HasComponent<TutorialShown>(uIObjectInfo.entity));
			writer.PropertyName("force");
			writer.Write(base.EntityManager.HasComponent<ForceAdvisor>(uIObjectInfo.entity));
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(uIObjectInfo.entity));
			writer.PropertyName("children");
			BindTutorialGroup(writer, uIObjectInfo.entity);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		sortedCategories.Dispose();
	}
```

- `protected BindTutorial(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity tutorialEntity) : System.Void`  

```csharp
protected void BindTutorial(IJsonWriter writer, Entity tutorialEntity)
	{
		if (base.EntityManager.HasComponent<TutorialData>(tutorialEntity))
		{
			TutorialPrefab prefab = m_PrefabSystem.GetPrefab<TutorialPrefab>(tutorialEntity);
			writer.TypeBegin(TypeNames.kTutorial);
			writer.PropertyName("entity");
			writer.Write(tutorialEntity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("icon");
			writer.Write(ImageSystem.GetIcon(prefab));
			writer.PropertyName("locked");
			writer.Write(base.EntityManager.HasEnabledComponent<Locked>(tutorialEntity));
			writer.PropertyName("priority");
			writer.Write(prefab.m_Priority);
			writer.PropertyName("active");
			writer.Write(base.EntityManager.HasComponent<TutorialActive>(tutorialEntity));
			writer.PropertyName("completed");
			writer.Write(base.EntityManager.HasComponent<TutorialCompleted>(tutorialEntity) || AlternativeCompleted(tutorialEntity));
			writer.PropertyName("shown");
			writer.Write(base.EntityManager.HasComponent<TutorialShown>(tutorialEntity));
			writer.PropertyName("force");
			writer.Write(base.EntityManager.HasComponent<ForceAdvisor>(tutorialEntity));
			writer.PropertyName("mandatory");
			writer.Write(prefab.m_Mandatory);
			writer.PropertyName("advisorActivation");
			writer.Write(base.EntityManager.HasComponent<AdvisorActivation>(m_TutorialSystem.activeTutorial));
			DynamicBuffer<TutorialPhaseRef> buffer = base.EntityManager.GetBuffer<TutorialPhaseRef>(tutorialEntity, isReadOnly: true);
			writer.PropertyName("phases");
			int num = 0;
			for (int i = 0; i < buffer.Length; i++)
			{
				if (TutorialSystem.IsValidControlScheme(buffer[i].m_Phase, m_PrefabSystem))
				{
					num++;
				}
			}
			writer.ArrayBegin(num);
			for (int j = 0; j < buffer.Length; j++)
			{
				Entity phase = buffer[j].m_Phase;
				if (TutorialSystem.IsValidControlScheme(phase, m_PrefabSystem))
				{
					BindTutorialPhase(writer, phase);
				}
			}
			writer.ArrayEnd();
			writer.PropertyName("filters");
			writer.Write(GetFilters(prefab));
			writer.PropertyName("alternatives");
			if (base.EntityManager.TryGetBuffer(tutorialEntity, isReadOnly: true, out DynamicBuffer<Game.Tutorials.TutorialAlternative> buffer2))
			{
				writer.ArrayBegin(buffer2.Length);
				for (int k = 0; k < buffer2.Length; k++)
				{
					writer.Write(buffer2[k].m_Alternative);
				}
				writer.ArrayEnd();
			}
			else
			{
				writer.WriteNull();
			}
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `protected BindTutorialGroup(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected void BindTutorialGroup(IJsonWriter writer, Entity entity)
	{
		if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<UIGroupElement> buffer))
		{
			NativeList<UIObjectInfo> sortedObjects = UIObjectInfo.GetSortedObjects(base.EntityManager, buffer, Allocator.TempJob);
			writer.ArrayBegin(sortedObjects.Length);
			for (int i = 0; i < sortedObjects.Length; i++)
			{
				Entity entity2 = sortedObjects[i].entity;
				PrefabData prefabData = sortedObjects[i].prefabData;
				PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(prefabData);
				UIObject component = prefab.GetComponent<UIObject>();
				writer.TypeBegin(TypeNames.kAdvisorItem);
				writer.PropertyName("entity");
				writer.Write(entity2);
				writer.PropertyName("name");
				writer.Write(prefab.name);
				writer.PropertyName("icon");
				if (component.m_Icon == null)
				{
					writer.WriteNull();
				}
				else
				{
					writer.Write(component.m_Icon);
				}
				writer.PropertyName("type");
				writer.Write((!(prefab is TutorialPrefab)) ? 1 : 0);
				writer.PropertyName("shown");
				writer.Write(base.EntityManager.HasComponent<TutorialShown>(entity2));
				writer.PropertyName("force");
				writer.Write(base.EntityManager.HasComponent<ForceAdvisor>(entity2));
				writer.PropertyName("locked");
				writer.Write(base.EntityManager.HasEnabledComponent<Locked>(entity2));
				writer.PropertyName("children");
				BindTutorialGroup(writer, entity2);
				writer.TypeEnd();
			}
			writer.ArrayEnd();
			sortedObjects.Dispose();
		}
		else
		{
			writer.WriteEmptyArray();
		}
	}
```

- `protected BindTutorialPhase(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity phaseEntity) : System.Void`  

```csharp
protected void BindTutorialPhase(IJsonWriter writer, Entity phaseEntity)
	{
		if (base.EntityManager.TryGetComponent<TutorialPhaseData>(phaseEntity, out var component))
		{
			TutorialPhasePrefab prefab = m_PrefabSystem.GetPrefab<TutorialPhasePrefab>(phaseEntity);
			TutorialBalloonPrefab tutorialBalloonPrefab = prefab as TutorialBalloonPrefab;
			writer.TypeBegin(TypeNames.kTutorialPhase);
			writer.PropertyName("entity");
			writer.Write(phaseEntity);
			writer.PropertyName("name");
			writer.Write(prefab.name);
			writer.PropertyName("type");
			writer.Write((int)component.m_Type);
			writer.PropertyName("active");
			writer.Write(base.EntityManager.HasComponent<TutorialPhaseActive>(phaseEntity));
			writer.PropertyName("shown");
			writer.Write(base.EntityManager.HasComponent<TutorialPhaseShown>(phaseEntity));
			writer.PropertyName("force");
			writer.Write(base.EntityManager.HasComponent<ForceAdvisor>(phaseEntity));
			writer.PropertyName("completed");
			writer.Write(base.EntityManager.HasComponent<TutorialPhaseCompleted>(phaseEntity));
			writer.PropertyName("forcesCompletion");
			writer.Write(base.EntityManager.HasComponent<Game.Tutorials.ForceTutorialCompletion>(phaseEntity));
			writer.PropertyName("isBranch");
			writer.Write(base.EntityManager.HasComponent<TutorialPhaseBranch>(phaseEntity));
			writer.PropertyName("image");
			writer.Write((!string.IsNullOrWhiteSpace(prefab.m_Image)) ? prefab.m_Image : null);
			writer.PropertyName("overrideImagePS");
			writer.Write((!string.IsNullOrWhiteSpace(prefab.m_OverrideImagePS)) ? prefab.m_OverrideImagePS : null);
			writer.PropertyName("overrideImageXbox");
			writer.Write((!string.IsNullOrWhiteSpace(prefab.m_OverrideImageXBox)) ? prefab.m_OverrideImageXBox : null);
			writer.PropertyName("icon");
			writer.Write((!string.IsNullOrWhiteSpace(prefab.m_Icon)) ? prefab.m_Icon : null);
			writer.PropertyName("titleVisible");
			writer.Write(prefab.m_TitleVisible);
			writer.PropertyName("descriptionVisible");
			writer.Write(prefab.m_DescriptionVisible);
			writer.PropertyName("balloonTargets");
			if (tutorialBalloonPrefab == null)
			{
				writer.WriteEmptyArray();
			}
			else
			{
				writer.Write((IList<TutorialBalloonPrefab.BalloonUITarget>)tutorialBalloonPrefab.m_UITargets);
			}
			writer.PropertyName("controlScheme");
			writer.Write((int)prefab.m_ControlScheme);
			writer.PropertyName("trigger");
			if (base.EntityManager.TryGetComponent<TutorialTrigger>(phaseEntity, out var component2))
			{
				TutorialTriggerPrefabBase prefab2 = m_PrefabSystem.GetPrefab<TutorialTriggerPrefabBase>(component2.m_Trigger);
				writer.TypeBegin(TypeNames.kTutorialTrigger);
				writer.PropertyName("entity");
				writer.Write(component2.m_Trigger);
				writer.PropertyName("name");
				writer.Write(prefab2.name);
				Dictionary<int, List<string>> blinkTags = prefab2.GetBlinkTags();
				List<int> list = blinkTags.Keys.ToList();
				list.Sort();
				writer.PropertyName("blinkTags");
				writer.ArrayBegin(list.Count);
				foreach (int item in list)
				{
					List<string> value = blinkTags[item];
					writer.Write((IList<string>)value);
				}
				writer.ArrayEnd();
				writer.PropertyName("displayUI");
				writer.Write(prefab2.m_DisplayUI);
				writer.PropertyName("active");
				writer.Write(base.EntityManager.HasComponent<TriggerActive>(component2.m_Trigger));
				writer.PropertyName("completed");
				writer.Write(base.EntityManager.HasComponent<TriggerCompleted>(component2.m_Trigger));
				writer.PropertyName("preCompleted");
				writer.Write(base.EntityManager.HasComponent<TriggerPreCompleted>(component2.m_Trigger));
				writer.PropertyName("phaseBranching");
				writer.Write(prefab2.phaseBranching);
				writer.TypeEnd();
			}
			else
			{
				writer.WriteNull();
			}
			writer.TypeEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `private CompleteActiveTutorial() : System.Void`  

```csharp
private void CompleteActiveTutorial()
	{
		m_TutorialSystem.CompleteTutorial(m_TutorialSystem.activeTutorial);
	}
```

- `protected virtual CompleteActiveTutorialPhase() : System.Void`  

```csharp
protected virtual void CompleteActiveTutorialPhase()
	{
		if (GameManager.instance.gameMode.IsGame())
		{
			m_TutorialSystem.CompleteCurrentTutorialPhase();
		}
	}
```

- `private CompleteIntro() : System.Void`  

```csharp
private void CompleteIntro(bool tutorialEnabled)
	{
		m_TutorialSystem.mode = TutorialMode.Default;
		m_TutorialSystem.tutorialEnabled = tutorialEnabled;
	}
```

- `private CompleteIntro(System.Boolean tutorialEnabled) : System.Void`  

```csharp
private void CompleteIntro(bool tutorialEnabled)
	{
		m_TutorialSystem.mode = TutorialMode.Default;
		m_TutorialSystem.tutorialEnabled = tutorialEnabled;
	}
```

- `private CompleteOutro() : System.Void`  

```csharp
private void CompleteOutro()
	{
		m_TutorialSystem.mode = TutorialMode.Default;
	}
```

- `private DisactivateTutorialTrigger(System.String trigger) : System.Void`  

```csharp
private void DisactivateTutorialTrigger(string trigger)
	{
		m_TriggerSystem.DisactivateTrigger(trigger);
	}
```

- `private ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  

```csharp
private void ForceTutorial(Entity tutorial, Entity phase, bool advisorActivation)
	{
		m_TutorialSystem.ForceTutorial(tutorial, phase, advisorActivation);
	}
```

- `private static GetFilters(Game.Prefabs.TutorialPrefab prefab) : System.String[]`  

```csharp
private static string[] GetFilters(TutorialPrefab prefab)
	{
		TutorialControlSchemeActivation component = prefab.GetComponent<TutorialControlSchemeActivation>();
		if (!(component != null))
		{
			return null;
		}
		return new string[1] { component.m_ControlScheme.ToString() };
	}
```

- `private GetListHintTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private NativeList<Entity> GetListHintTutorials(Entity listEntity, Allocator allocator)
	{
		DynamicBuffer<TutorialRef> buffer = base.EntityManager.GetBuffer<TutorialRef>(listEntity, isReadOnly: true);
		ComponentLookup<TutorialActivationData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tutorials_TutorialActivationData_RW_ComponentLookup, ref base.CheckedStateRef);
		NativeList<Entity> result = new NativeList<Entity>(buffer.Length, allocator);
		foreach (TutorialRef item in buffer)
		{
			TutorialRef current = item;
			if (componentLookup.HasComponent(current.m_Tutorial))
			{
				result.Add(in current.m_Tutorial);
			}
		}
		return result;
	}
```

- `private GetSortedCategories(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private NativeList<UIObjectInfo> GetSortedCategories(Allocator allocator)
	{
		NativeArray<Entity> nativeArray = m_TutorialCategoryQuery.ToEntityArray(Allocator.TempJob);
		NativeArray<UIObjectData> nativeArray2 = m_TutorialCategoryQuery.ToComponentDataArray<UIObjectData>(Allocator.TempJob);
		NativeList<UIObjectInfo> nativeList = new NativeList<UIObjectInfo>(allocator);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (nativeArray2[i].m_Group == Entity.Null)
			{
				nativeList.Add(new UIObjectInfo(nativeArray[i], nativeArray2[i].m_Priority));
			}
		}
		nativeList.Sort();
		nativeArray.Dispose();
		nativeArray2.Dispose();
		return nativeList;
	}
```

- `private GetVisibleListTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private NativeList<Entity> GetVisibleListTutorials(Entity listEntity, Allocator allocator)
	{
		DynamicBuffer<TutorialRef> buffer = base.EntityManager.GetBuffer<TutorialRef>(listEntity, isReadOnly: true);
		ComponentLookup<TutorialActivationData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tutorials_TutorialActivationData_RW_ComponentLookup, ref base.CheckedStateRef);
		NativeList<Entity> result = new NativeList<Entity>(buffer.Length, allocator);
		foreach (TutorialRef item in buffer)
		{
			TutorialRef current = item;
			if (!componentLookup.HasComponent(current.m_Tutorial))
			{
				result.Add(in current.m_Tutorial);
			}
		}
		return result;
	}
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
private void OnControlSchemeChanged(InputManager.ControlScheme controlScheme)
	{
		m_TutorialsBinding.UpdateAll();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		base.Enabled = false;
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_TutorialSystem = base.World.GetOrCreateSystemManaged<TutorialSystem>();
		m_ActivationSystem = base.World.GetOrCreateSystemManaged<TutorialUIActivationSystem>();
		m_DeactivationSystem = base.World.GetOrCreateSystemManaged<TutorialUIDeactivationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TutorialUITriggerSystem>();
		m_TutorialCategoryQuery = GetEntityQuery(ComponentType.ReadOnly<UITutorialGroupData>(), ComponentType.Exclude<UIEditorTutorialGroupData>(), ComponentType.ReadOnly<UIObjectData>());
		m_UnlockQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		AddBinding(m_ActiveTutorialListBinding = new RawValueBinding("tutorials", "activeList", BindActiveTutorialList));
		AddBinding(new TriggerBinding<Entity>("tutorials", "activateTutorial", ActivateTutorial));
		AddBinding(new TriggerBinding<Entity, Entity>("tutorials", "activateTutorialPhase", ActivateTutorialPhase));
		AddBinding(new TriggerBinding<Entity, Entity, bool>("tutorials", "forceTutorial", ForceTutorial));
		AddBinding(new TriggerBinding("tutorials", "completeActiveTutorialPhase", CompleteActiveTutorialPhase));
		AddBinding(new TriggerBinding("tutorials", "completeActiveTutorial", CompleteActiveTutorial));
		AddBinding(new TriggerBinding<string, bool>("tutorials", "setTutorialTagActive", OnSetTutorialTagActive));
		AddBinding(new TriggerBinding<string>("tutorials", "activateTutorialTrigger", ActivateTutorialTrigger));
		AddBinding(new TriggerBinding<string>("tutorials", "disactivateTutorialTrigger", DisactivateTutorialTrigger));
		if (!(GetType() == typeof(EditorTutorialsUISystem)))
		{
			AddBinding(new TriggerBinding("tutorials", "completeListIntro", CompleteIntro));
			AddBinding(new TriggerBinding("tutorials", "completeListOutro", CompleteOutro));
			AddBinding(new TriggerBinding<bool>("tutorials", "completeIntro", CompleteIntro));
			AddUpdateBinding(new GetterValueBinding<bool>("tutorials", "tutorialsEnabled", () => m_TutorialSystem.tutorialEnabled));
			AddUpdateBinding(new GetterValueBinding<bool>("tutorials", "introActive", () => m_TutorialSystem.mode == TutorialMode.Intro));
			AddUpdateBinding(new GetterValueBinding<bool>("tutorials", "listIntroActive", () => m_TutorialSystem.mode == TutorialMode.ListIntro));
			AddUpdateBinding(new GetterValueBinding<bool>("tutorials", "listOutroActive", () => m_TutorialSystem.mode == TutorialMode.ListOutro));
			AddUpdateBinding(new GetterValueBinding<Entity>("tutorials", "next", () => m_TutorialSystem.nextListTutorial));
			AddBinding(m_TutorialCategoriesBinding = new RawValueBinding("tutorials", "categories", BindCategories));
			AddBinding(m_TutorialsBinding = new RawMapBinding<Entity>("tutorials", "tutorials", BindTutorial));
			AddBinding(m_TutorialPendingBinding = new GetterValueBinding<Entity>("tutorials", "pending", () => m_TutorialSystem.tutorialPending));
			AddBinding(m_ActiveTutorialBinding = new RawValueBinding("tutorials", "activeTutorial", delegate(IJsonWriter writer)
			{
				BindTutorial(writer, m_TutorialSystem.activeTutorial);
			}));
			AddBinding(m_ActiveTutorialPhaseBinding = new RawValueBinding("tutorials", "activeTutorialPhase", delegate(IJsonWriter writer)
			{
				BindTutorialPhase(writer, m_TutorialSystem.activeTutorialPhase);
			}));
			m_WasEnabled = m_TutorialSystem.tutorialEnabled;
			InputManager.instance.EventControlSchemeChanged += OnControlSchemeChanged;
		}
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected override void OnGameLoadingComplete(Purpose purpose, GameMode gameMode)
	{
		base.OnGameLoadingComplete(purpose, gameMode);
		base.Enabled = gameMode.IsGameOrEditor();
	}
```

- `private OnSetTutorialTagActive(System.String tag, System.Boolean active) : System.Void`  

```csharp
private void OnSetTutorialTagActive(string tag, bool active)
	{
		m_ActivationSystem.SetTag(tag, active);
		if (!active)
		{
			m_DeactivationSystem.DeactivateTag(tag);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		int componentOrderVersion = base.EntityManager.GetComponentOrderVersion<TutorialActive>();
		int componentOrderVersion2 = base.EntityManager.GetComponentOrderVersion<TutorialPhaseActive>();
		int componentOrderVersion3 = base.EntityManager.GetComponentOrderVersion<TutorialPhaseCompleted>();
		int componentOrderVersion4 = base.EntityManager.GetComponentOrderVersion<TutorialPhaseShown>();
		int componentOrderVersion5 = base.EntityManager.GetComponentOrderVersion<TriggerActive>();
		int componentOrderVersion6 = base.EntityManager.GetComponentOrderVersion<TriggerCompleted>();
		int componentOrderVersion7 = base.EntityManager.GetComponentOrderVersion<TutorialShown>();
		bool flag = componentOrderVersion != m_TutorialActiveVersion;
		bool flag2 = componentOrderVersion2 != m_PhaseActiveVersion;
		bool flag3 = componentOrderVersion5 != m_TriggerActiveVersion;
		bool flag4 = componentOrderVersion6 != m_TriggerCompletedVersion;
		bool flag5 = componentOrderVersion7 != m_TutorialShownVersion;
		bool flag6 = componentOrderVersion4 != m_PhaseShownVersion;
		bool flag7 = componentOrderVersion3 != m_PhaseCompletedVersion;
		if (flag)
		{
			m_ActiveTutorialListBinding.Update();
		}
		if (m_TutorialsBinding != null && (flag || flag2 || flag3 || flag4 || flag7))
		{
			m_ActiveTutorialBinding.Update();
			m_ActiveTutorialPhaseBinding.Update();
			m_TutorialsBinding.Update(m_TutorialSystem.activeTutorial);
		}
		if (PrefabUtils.HasUnlockedPrefabAny<TutorialData, TutorialPhaseData, TutorialTriggerData, TutorialListData>(base.EntityManager, m_UnlockQuery) || m_WasEnabled != m_TutorialSystem.tutorialEnabled || flag5 || flag6)
		{
			m_TutorialCategoriesBinding.Update();
			if (m_TutorialsBinding != null)
			{
				m_TutorialsBinding.UpdateAll();
			}
		}
		if (m_TutorialPendingBinding != null)
		{
			m_TutorialPendingBinding.Update();
		}
		m_TutorialActiveVersion = componentOrderVersion;
		m_PhaseActiveVersion = componentOrderVersion2;
		m_TriggerActiveVersion = componentOrderVersion5;
		m_TriggerCompletedVersion = componentOrderVersion6;
		m_TutorialShownVersion = componentOrderVersion7;
		m_PhaseShownVersion = componentOrderVersion4;
		m_PhaseCompletedVersion = componentOrderVersion3;
		if (m_TutorialSystem != null)
		{
			m_WasEnabled = m_TutorialSystem.tutorialEnabled;
		}
	}
```


## Nested types

- `Game.UI.InGame.TutorialsUISystem+BindingNames`  
- `Game.UI.InGame.TutorialsUISystem+AdvisorItemType`  
- `Game.UI.InGame.TutorialsUISystem+TypeHandle`  

