# Game.Tutorials.TutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tutorials.ITutorialSystem`, `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialSystem : Game.GameSystemBase, Game.Tutorials.ITutorialSystem, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
    private Unity.Entities.EntityQuery m_TutorialConfigurationQuery;
    protected Unity.Entities.EntityQuery m_TutorialQuery;
    private Unity.Entities.EntityQuery m_TutorialListQuery;
    private Unity.Entities.EntityQuery m_TutorialPhaseQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialListQuery;
    protected Unity.Entities.EntityQuery m_ActiveTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialPhaseQuery;
    protected Unity.Entities.EntityQuery m_PendingTutorialListQuery;
    protected Unity.Entities.EntityQuery m_PendingTutorialQuery;
    protected Unity.Entities.EntityQuery m_PendingPriorityTutorialQuery;
    protected Unity.Entities.EntityQuery m_LockedTutorialQuery;
    private Unity.Entities.EntityQuery m_LockedTutorialPhaseQuery;
    private Unity.Entities.EntityQuery m_LockedTutorialTriggerQuery;
    private Unity.Entities.EntityQuery m_LockedTutorialListQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_ForceAdvisorQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private System.Single m_AccumulatedDelay;
    protected Game.Tutorials.TutorialMode m_Mode;
    protected Game.Settings.Setting m_Setting;
    private Game.Tutorials.TutorialSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kBalloonCompletionDelay;
    private static readonly System.Single kCompletionDelay;
    private static readonly System.Single kActivationDelay;
    private static readonly System.String kWelcomeIntroKey;
    protected static readonly System.String kListIntroKey;
    private static readonly System.String kListOutroKey;

    protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get; }
    public Game.Tutorials.TutorialMode mode { get; set; }
    public Unity.Entities.Entity activeTutorial { get; }
    public Unity.Entities.Entity activeTutorialPhase { get; }
    public System.Boolean tutorialEnabled { get; set; }
    public Unity.Entities.Entity activeTutorialList { get; }
    public Unity.Entities.Entity tutorialPending { get; }
    public Unity.Entities.Entity nextListTutorial { get; }
    public System.Boolean showListReminder { get; }

    public TutorialSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ActivateNextTutorial(System.Boolean delay);
    private System.Void ActivateNextTutorialList();
    private System.Boolean CheckCurrentPhaseCompleted(Unity.Entities.Entity& nextPhase);
    private System.Boolean CheckCurrentTutorialListCompleted();
    private System.Void CheckListIntro();
    private System.Void CleanupTutorial(Unity.Entities.Entity tutorial, System.Boolean passed, System.Boolean updateSettings);
    private System.Void CleanupTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed, System.Boolean updateSettings);
    private System.Void CleanupTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed, System.Boolean updateSettings);
    private System.Void ClearComponents();
    private System.Void ClearLock(Unity.Entities.Entity entity);
    private System.Void ClearLocks(Unity.Entities.EntityQuery query);
    private System.Void ClearTutorialLocks();
    private System.Void CompleteCurrentTutorialList();
    public System.Void CompleteCurrentTutorialPhase();
    public System.Void CompleteCurrentTutorialPhase(Unity.Entities.Entity nextPhase);
    public System.Void CompleteTutorial(Unity.Entities.Entity tutorial);
    private Unity.Entities.Entity FindNextTutorial();
    private Unity.Entities.Entity FindNextTutorial(Unity.Entities.EntityQuery query);
    private Unity.Entities.Entity FindNextTutorialList(Unity.Entities.EntityQuery query);
    private System.Void ForceAdvisor(Unity.Entities.Entity entity);
    private System.Void ForceAdvisorVisibility();
    public System.Void ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation);
    private static System.Single GetCompletionDelay(Game.Tutorials.TutorialPhaseData phase);
    private Unity.Entities.Entity GetFirstTutorialPhase(Unity.Entities.Entity tutorial);
    private Unity.Entities.Entity GetNextPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity currentPhase, Unity.Entities.Entity nextPhase);
    private System.Boolean IsCompleted(Unity.Entities.Entity tutorial, Unity.Entities.BufferLookup<Game.Tutorials.TutorialAlternative> alternativeData, Unity.Entities.ComponentLookup<Game.Tutorials.TutorialCompleted> completionData);
    public static System.Boolean IsValidControlScheme(Unity.Entities.Entity phase, Game.Prefabs.PrefabSystem prefabSystem);
    public static System.Void ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager);
    public static System.Void ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer);
    public static System.Void ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.BufferLookup`1[[Game.Prefabs.ForceUIGroupUnlockData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& forcedUnlocksFromEntity, Unity.Entities.BufferLookup`1[[Game.Prefabs.UnlockRequirement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unlockRequirementsFromEntity, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey);
    private System.Boolean NonListTutorialPending();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    public virtual System.Void OnResetTutorials();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void ReadSettings();
    private System.Void ResetState();
    public System.Void SetAllTutorialsShown();
    private System.Void SetTutorial(Unity.Entities.Entity tutorial, System.Boolean passed);
    public System.Void SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean passed);
    public System.Void SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase);
    private System.Void SetTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed, System.Boolean updateSettings);
    private System.Void SetTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed);
    private System.Void SetTutorialShown(Unity.Entities.Entity entity, System.Boolean updateSettings);
    private System.Boolean ShouldReplaceActiveTutorial();
    private System.Boolean ShouldReplaceActiveTutorialList();
    public System.Void SkipActiveList();
    private System.Void UpdateActiveTutorial();
    private System.Void UpdateActiveTutorialList();
    private System.Void UpdateSettings(Unity.Entities.Entity tutorial, System.Boolean passed);
    private System.Void UpdateSettings(System.String name, System.Boolean passed);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  

```csharp
private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
```

- `private Unity.Entities.EntityQuery m_TutorialConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialConfigurationQuery;
```

- `protected Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
protected Unity.Entities.EntityQuery m_TutorialQuery;
```

- `private Unity.Entities.EntityQuery m_TutorialListQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialListQuery;
```

- `private Unity.Entities.EntityQuery m_TutorialPhaseQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialPhaseQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialListQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialListQuery;
```

- `protected Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialPhaseQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialPhaseQuery;
```

- `protected Unity.Entities.EntityQuery m_PendingTutorialListQuery`  

```csharp
protected Unity.Entities.EntityQuery m_PendingTutorialListQuery;
```

- `protected Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
protected Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `protected Unity.Entities.EntityQuery m_PendingPriorityTutorialQuery`  

```csharp
protected Unity.Entities.EntityQuery m_PendingPriorityTutorialQuery;
```

- `protected Unity.Entities.EntityQuery m_LockedTutorialQuery`  

```csharp
protected Unity.Entities.EntityQuery m_LockedTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_LockedTutorialPhaseQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedTutorialPhaseQuery;
```

- `private Unity.Entities.EntityQuery m_LockedTutorialTriggerQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedTutorialTriggerQuery;
```

- `private Unity.Entities.EntityQuery m_LockedTutorialListQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedTutorialListQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_ForceAdvisorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ForceAdvisorQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private System.Single m_AccumulatedDelay`  

```csharp
private System.Single m_AccumulatedDelay;
```

- `protected Game.Tutorials.TutorialMode m_Mode`  

```csharp
protected Game.Tutorials.TutorialMode m_Mode;
```

- `protected Game.Settings.Setting m_Setting`  

```csharp
protected Game.Settings.Setting m_Setting;
```

- `private Game.Tutorials.TutorialSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tutorials.TutorialSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kBalloonCompletionDelay`  

```csharp
private static readonly System.Single kBalloonCompletionDelay;
```

- `private static readonly System.Single kCompletionDelay`  

```csharp
private static readonly System.Single kCompletionDelay;
```

- `private static readonly System.Single kActivationDelay`  

```csharp
private static readonly System.Single kActivationDelay;
```

- `private static readonly System.String kWelcomeIntroKey`  

```csharp
private static readonly System.String kWelcomeIntroKey;
```

- `protected static readonly System.String kListIntroKey`  

```csharp
protected static readonly System.String kListIntroKey;
```

- `private static readonly System.String kListOutroKey`  

```csharp
private static readonly System.String kListOutroKey;
```


## Properties

- `protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get }`  

```csharp
protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get; }
```

- `public Game.Tutorials.TutorialMode mode { get; set }`  

```csharp
public Game.Tutorials.TutorialMode mode { get; set; }
```

- `public Unity.Entities.Entity activeTutorial { get }`  

```csharp
public Unity.Entities.Entity activeTutorial { get; }
```

- `public Unity.Entities.Entity activeTutorialPhase { get }`  

```csharp
public Unity.Entities.Entity activeTutorialPhase { get; }
```

- `public System.Boolean tutorialEnabled { get; set }`  

```csharp
public System.Boolean tutorialEnabled { get; set; }
```

- `public Unity.Entities.Entity activeTutorialList { get }`  

```csharp
public Unity.Entities.Entity activeTutorialList { get; }
```

- `public Unity.Entities.Entity tutorialPending { get }`  

```csharp
public Unity.Entities.Entity tutorialPending { get; }
```

- `public Unity.Entities.Entity nextListTutorial { get }`  

```csharp
public Unity.Entities.Entity nextListTutorial { get; }
```

- `public System.Boolean showListReminder { get }`  

```csharp
public System.Boolean showListReminder { get; }
```


## Constructors

- `public TutorialSystem()`  

```csharp
[Preserve]
	public TutorialSystem()
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

- `private ActivateNextTutorial(System.Boolean delay = False) : System.Void`  

```csharp
private void ActivateNextTutorial(bool delay = false)
	{
		if (delay)
		{
			m_AccumulatedDelay += UnityEngine.Time.deltaTime;
			if (m_AccumulatedDelay < kActivationDelay)
			{
				return;
			}
			m_AccumulatedDelay = 0f;
		}
		Entity tutorial = FindNextTutorial();
		SetTutorial(tutorial);
	}
```

- `private ActivateNextTutorialList() : System.Void`  

```csharp
private void ActivateNextTutorialList()
	{
		Entity tutorialList = FindNextTutorialList(m_PendingTutorialListQuery);
		SetTutorialList(tutorialList);
	}
```

- `private CheckCurrentPhaseCompleted(Unity.Entities.Entity& nextPhase) : System.Boolean`  

```csharp
private bool CheckCurrentPhaseCompleted(out Entity nextPhase)
	{
		nextPhase = Entity.Null;
		if (base.EntityManager.TryGetComponent<TutorialPhaseData>(activeTutorialPhase, out var component) && base.EntityManager.TryGetComponent<TutorialTrigger>(activeTutorialPhase, out var component2))
		{
			if (!base.EntityManager.HasComponent<TriggerCompleted>(component2.m_Trigger))
			{
				return false;
			}
			if (m_AccumulatedDelay < GetCompletionDelay(component))
			{
				m_AccumulatedDelay += UnityEngine.Time.deltaTime;
				return false;
			}
			m_AccumulatedDelay = 0f;
			if (base.EntityManager.TryGetComponent<TutorialNextPhase>(activeTutorialPhase, out var component3))
			{
				nextPhase = component3.m_NextPhase;
			}
			if (base.EntityManager.TryGetComponent<TutorialNextPhase>(component2.m_Trigger, out component3))
			{
				nextPhase = component3.m_NextPhase;
			}
			return true;
		}
		return false;
	}
```

- `private CheckCurrentTutorialListCompleted() : System.Boolean`  

```csharp
private bool CheckCurrentTutorialListCompleted()
	{
		if (base.EntityManager.HasComponent<TutorialRef>(activeTutorialList))
		{
			ComponentLookup<TutorialCompleted> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tutorials_TutorialCompleted_RO_ComponentLookup, ref base.CheckedStateRef);
			BufferLookup<TutorialAlternative> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tutorials_TutorialAlternative_RO_BufferLookup, ref base.CheckedStateRef);
			DynamicBuffer<TutorialRef> buffer = base.EntityManager.GetBuffer<TutorialRef>(activeTutorialList, isReadOnly: true);
			for (int i = 0; i < buffer.Length; i++)
			{
				if (!IsCompleted(buffer[i].m_Tutorial, bufferLookup, componentLookup))
				{
					return false;
				}
			}
		}
		return true;
	}
```

- `private CheckListIntro() : System.Void`  

```csharp
private void CheckListIntro()
	{
		TutorialsConfigurationData singleton = m_TutorialConfigurationQuery.GetSingleton<TutorialsConfigurationData>();
		if (activeTutorialList == singleton.m_TutorialsIntroList && !ShownTutorials.ContainsKey(kListIntroKey) && activeTutorial == Entity.Null && !NonListTutorialPending())
		{
			mode = TutorialMode.ListIntro;
			UpdateSettings(kListIntroKey, passed: true);
		}
	}
```

- `private CleanupTutorial(Unity.Entities.Entity tutorial, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private void CleanupTutorial(Entity tutorial, bool passed = false, bool updateSettings = true)
	{
		if (!(tutorial != Entity.Null))
		{
			return;
		}
		base.EntityManager.RemoveComponent<AdvisorActivation>(tutorial);
		base.EntityManager.RemoveComponent<TutorialActive>(tutorial);
		base.EntityManager.RemoveComponent<ForceActivation>(tutorial);
		NativeArray<TutorialPhaseRef> nativeArray = base.EntityManager.GetBuffer<TutorialPhaseRef>(tutorial, isReadOnly: true).ToNativeArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity phase = nativeArray[i].m_Phase;
			CleanupTutorialPhase(phase, passed, updateSettings);
		}
		nativeArray.Dispose();
		if (!passed)
		{
			return;
		}
		SetTutorialShown(tutorial);
		base.EntityManager.AddComponent<TutorialCompleted>(tutorial);
		if (updateSettings)
		{
			UpdateSettings(tutorial, passed: true);
			if (base.EntityManager.HasComponent<TutorialFireTelemetry>(tutorial))
			{
				Telemetry.TutorialEvent(tutorial);
			}
		}
		ManualUnlock(tutorial, m_UnlockEventArchetype, base.EntityManager);
	}
```

- `private CleanupTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private void CleanupTutorialList(Entity tutorialList, bool passed = false, bool updateSettings = true)
	{
		if (!(tutorialList != Entity.Null))
		{
			return;
		}
		base.EntityManager.RemoveComponent<TutorialActivated>(tutorialList);
		base.EntityManager.RemoveComponent<TutorialActive>(tutorialList);
		if (!passed)
		{
			return;
		}
		SetTutorialShown(tutorialList);
		base.EntityManager.AddComponent<TutorialCompleted>(tutorialList);
		ManualUnlock(tutorialList, m_UnlockEventArchetype, base.EntityManager);
		if (base.EntityManager.HasComponent<TutorialRef>(tutorialList))
		{
			NativeArray<TutorialRef> nativeArray = base.EntityManager.GetBuffer<TutorialRef>(tutorialList, isReadOnly: true).ToNativeArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				CleanupTutorial(nativeArray[i].m_Tutorial, passed, updateSettings);
			}
			nativeArray.Dispose();
		}
		if (updateSettings)
		{
			UpdateSettings(tutorialList, passed: true);
		}
	}
```

- `private CleanupTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private void CleanupTutorialPhase(Entity tutorialPhase, bool passed = false, bool updateSettings = true)
	{
		if (!(tutorialPhase != Entity.Null))
		{
			return;
		}
		base.EntityManager.RemoveComponent<TutorialPhaseActive>(tutorialPhase);
		if (passed)
		{
			SetTutorialShown(tutorialPhase);
			base.EntityManager.AddComponent<TutorialPhaseCompleted>(tutorialPhase);
			ManualUnlock(tutorialPhase, m_UnlockEventArchetype, base.EntityManager);
			if (updateSettings)
			{
				UpdateSettings(tutorialPhase, passed: true);
			}
		}
		if (base.EntityManager.TryGetComponent<TutorialTrigger>(tutorialPhase, out var component))
		{
			base.EntityManager.RemoveComponent<TriggerActive>(component.m_Trigger);
			base.EntityManager.RemoveComponent<TriggerCompleted>(component.m_Trigger);
			base.EntityManager.RemoveComponent<TriggerPreCompleted>(component.m_Trigger);
			base.EntityManager.RemoveComponent<TutorialNextPhase>(component.m_Trigger);
			if (passed)
			{
				ManualUnlock(component.m_Trigger, m_UnlockEventArchetype, base.EntityManager);
			}
		}
	}
```

- `private ClearComponents() : System.Void`  

```csharp
private void ClearComponents()
	{
		base.EntityManager.RemoveComponent<TutorialActive>(m_TutorialListQuery);
		base.EntityManager.RemoveComponent<TutorialCompleted>(m_TutorialListQuery);
		base.EntityManager.RemoveComponent<TutorialShown>(m_TutorialListQuery);
		base.EntityManager.RemoveComponent<AdvisorActivation>(m_TutorialQuery);
		base.EntityManager.RemoveComponent<TutorialActive>(m_TutorialQuery);
		base.EntityManager.RemoveComponent<TutorialCompleted>(m_TutorialQuery);
		base.EntityManager.RemoveComponent<TutorialShown>(m_TutorialQuery);
		base.EntityManager.RemoveComponent<ForceActivation>(m_TutorialQuery);
		base.EntityManager.RemoveComponent<TutorialActivated>(m_TutorialQuery);
		base.EntityManager.RemoveComponent<TutorialPhaseActive>(m_TutorialPhaseQuery);
		base.EntityManager.RemoveComponent<TutorialPhaseCompleted>(m_TutorialPhaseQuery);
		base.EntityManager.RemoveComponent<TutorialPhaseShown>(m_TutorialPhaseQuery);
	}
```

- `private ClearLock(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void ClearLock(Entity entity)
	{
		NativeArray<UnlockRequirement> nativeArray = base.EntityManager.GetBuffer<UnlockRequirement>(entity, isReadOnly: true).ToNativeArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			UnlockRequirement unlockRequirement = nativeArray[i];
			if (unlockRequirement.m_Prefab == entity && (unlockRequirement.m_Flags & UnlockFlags.RequireAll) != 0)
			{
				ManualUnlock(entity, m_UnlockEventArchetype, base.EntityManager);
				nativeArray.Dispose();
				return;
			}
		}
		nativeArray.Dispose();
	}
```

- `private ClearLocks(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private void ClearLocks(EntityQuery query)
	{
		if (!query.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = query.ToEntityArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ClearLock(nativeArray[i]);
			}
			nativeArray.Dispose();
		}
	}
```

- `private ClearTutorialLocks() : System.Void`  

```csharp
private void ClearTutorialLocks()
	{
		ClearLocks(m_LockedTutorialQuery);
		ClearLocks(m_LockedTutorialPhaseQuery);
		ClearLocks(m_LockedTutorialTriggerQuery);
		ClearLocks(m_LockedTutorialListQuery);
		if (m_CityConfigurationSystem.unlockMapTiles)
		{
			TutorialsConfigurationData singleton = m_TutorialConfigurationQuery.GetSingleton<TutorialsConfigurationData>();
			if (base.EntityManager.HasEnabledComponent<Locked>(singleton.m_MapTilesFeature))
			{
				Entity entity = base.EntityManager.CreateEntity(m_UnlockEventArchetype);
				base.EntityManager.SetComponentData(entity, new Unlock(singleton.m_MapTilesFeature));
			}
			m_MapTilePurchaseSystem.UnlockMapTiles();
		}
	}
```

- `private CompleteCurrentTutorialList() : System.Void`  

```csharp
private void CompleteCurrentTutorialList()
	{
		Entity entity = activeTutorialList;
		if (m_CityConfigurationSystem.unlockMapTiles)
		{
			TutorialsConfigurationData singleton = m_TutorialConfigurationQuery.GetSingleton<TutorialsConfigurationData>();
			if (activeTutorialList == singleton.m_TutorialsIntroList)
			{
				if (base.EntityManager.HasEnabledComponent<Locked>(singleton.m_MapTilesFeature))
				{
					Entity entity2 = base.EntityManager.CreateEntity(m_UnlockEventArchetype);
					base.EntityManager.SetComponentData(entity2, new Unlock(singleton.m_MapTilesFeature));
				}
				m_MapTilePurchaseSystem.UnlockMapTiles();
			}
		}
		if (entity != Entity.Null)
		{
			SetTutorialList(Entity.Null, passed: true);
		}
	}
```

- `public CompleteCurrentTutorialPhase() : System.Void`  

```csharp
public void CompleteCurrentTutorialPhase(Entity nextPhase)
	{
		Entity entity = activeTutorial;
		if (entity != Entity.Null)
		{
			Entity entity2 = GetNextPhase(entity, activeTutorialPhase, nextPhase);
			if (base.EntityManager.HasComponent<ForceTutorialCompletion>(activeTutorialPhase))
			{
				entity2 = Entity.Null;
			}
			if (entity2 != Entity.Null)
			{
				SetTutorialPhase(entity2, passed: true);
			}
			else
			{
				CompleteTutorial(entity);
			}
		}
	}
```

- `public CompleteCurrentTutorialPhase(Unity.Entities.Entity nextPhase) : System.Void`  

```csharp
public void CompleteCurrentTutorialPhase(Entity nextPhase)
	{
		Entity entity = activeTutorial;
		if (entity != Entity.Null)
		{
			Entity entity2 = GetNextPhase(entity, activeTutorialPhase, nextPhase);
			if (base.EntityManager.HasComponent<ForceTutorialCompletion>(activeTutorialPhase))
			{
				entity2 = Entity.Null;
			}
			if (entity2 != Entity.Null)
			{
				SetTutorialPhase(entity2, passed: true);
			}
			else
			{
				CompleteTutorial(entity);
			}
		}
	}
```

- `public CompleteTutorial(Unity.Entities.Entity tutorial) : System.Void`  

```csharp
public void CompleteTutorial(Entity tutorial)
	{
		if (!m_SoundQuery.IsEmptyIgnoreFilter)
		{
			m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TutorialCompletedSound);
		}
		CleanupTutorial(tutorial, passed: true);
	}
```

- `private FindNextTutorial() : Unity.Entities.Entity`  

```csharp
private Entity FindNextTutorial(EntityQuery query)
	{
		if (!query.IsEmptyIgnoreFilter)
		{
			NativeArray<TutorialData> nativeArray = query.ToComponentDataArray<TutorialData>(Allocator.TempJob);
			NativeArray<Entity> nativeArray2 = query.ToEntityArray(Allocator.TempJob);
			int index = 0;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (nativeArray[i].m_Priority < nativeArray[index].m_Priority)
				{
					index = i;
				}
			}
			Entity result = nativeArray2[index];
			nativeArray.Dispose();
			nativeArray2.Dispose();
			return result;
		}
		return Entity.Null;
	}
```

- `private FindNextTutorial(Unity.Entities.EntityQuery query) : Unity.Entities.Entity`  

```csharp
private Entity FindNextTutorial(EntityQuery query)
	{
		if (!query.IsEmptyIgnoreFilter)
		{
			NativeArray<TutorialData> nativeArray = query.ToComponentDataArray<TutorialData>(Allocator.TempJob);
			NativeArray<Entity> nativeArray2 = query.ToEntityArray(Allocator.TempJob);
			int index = 0;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (nativeArray[i].m_Priority < nativeArray[index].m_Priority)
				{
					index = i;
				}
			}
			Entity result = nativeArray2[index];
			nativeArray.Dispose();
			nativeArray2.Dispose();
			return result;
		}
		return Entity.Null;
	}
```

- `private FindNextTutorialList(Unity.Entities.EntityQuery query) : Unity.Entities.Entity`  

```csharp
private Entity FindNextTutorialList(EntityQuery query)
	{
		if (!query.IsEmptyIgnoreFilter)
		{
			NativeArray<TutorialListData> nativeArray = query.ToComponentDataArray<TutorialListData>(Allocator.TempJob);
			NativeArray<Entity> nativeArray2 = query.ToEntityArray(Allocator.TempJob);
			int index = 0;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (nativeArray[i].m_Priority < nativeArray[index].m_Priority)
				{
					index = i;
				}
			}
			Entity result = nativeArray2[index];
			nativeArray.Dispose();
			nativeArray2.Dispose();
			return result;
		}
		return Entity.Null;
	}
```

- `private ForceAdvisor(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void ForceAdvisor(Entity entity)
	{
		if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<TutorialPhaseRef> buffer))
		{
			NativeArray<TutorialPhaseRef> nativeArray = buffer.ToNativeArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity phase = nativeArray[i].m_Phase;
				ForceAdvisor(phase);
			}
			nativeArray.Dispose();
		}
		if (base.EntityManager.TryGetComponent<UIObjectData>(entity, out var component) && component.m_Group != Entity.Null)
		{
			ForceAdvisor(component.m_Group);
		}
		if (!base.EntityManager.HasComponent<ForceAdvisor>(entity))
		{
			base.EntityManager.AddComponent<ForceAdvisor>(entity);
		}
	}
```

- `private ForceAdvisorVisibility() : System.Void`  

```csharp
private void ForceAdvisorVisibility()
	{
		NativeArray<Entity> nativeArray = m_ForceAdvisorQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ForceAdvisor(nativeArray[i]);
		}
		nativeArray.Dispose();
	}
```

- `public ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  

```csharp
public void ForceTutorial(Entity tutorial, Entity phase, bool advisorActivation)
	{
		if (tutorial != Entity.Null)
		{
			base.EntityManager.AddComponent<ForceActivation>(tutorial);
			if (advisorActivation)
			{
				base.EntityManager.AddComponent<AdvisorActivation>(tutorial);
			}
		}
		SetTutorial(tutorial, phase, passed: false);
	}
```

- `private static GetCompletionDelay(Game.Tutorials.TutorialPhaseData phase) : System.Single`  

```csharp
private static float GetCompletionDelay(TutorialPhaseData phase)
	{
		if (phase.m_OverrideCompletionDelay >= 0f)
		{
			return phase.m_OverrideCompletionDelay;
		}
		if (phase.m_Type == TutorialPhaseType.Balloon)
		{
			return kBalloonCompletionDelay;
		}
		return kCompletionDelay;
	}
```

- `private GetFirstTutorialPhase(Unity.Entities.Entity tutorial) : Unity.Entities.Entity`  

```csharp
private Entity GetFirstTutorialPhase(Entity tutorial)
	{
		DynamicBuffer<TutorialPhaseRef> buffer = base.EntityManager.GetBuffer<TutorialPhaseRef>(tutorial, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity phase = buffer[i].m_Phase;
			if (IsValidControlScheme(phase, m_PrefabSystem))
			{
				return phase;
			}
		}
		return Entity.Null;
	}
```

- `private GetNextPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity currentPhase, Unity.Entities.Entity nextPhase) : Unity.Entities.Entity`  

```csharp
private Entity GetNextPhase(Entity tutorial, Entity currentPhase, Entity nextPhase)
	{
		NativeArray<TutorialPhaseRef> nativeArray = base.EntityManager.GetBuffer<TutorialPhaseRef>(tutorial, isReadOnly: true).ToNativeArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity phase = nativeArray[i].m_Phase;
			if (nextPhase == Entity.Null)
			{
				if (!(phase == currentPhase))
				{
					continue;
				}
				for (int j = i; j < nativeArray.Length - 1; j++)
				{
					nextPhase = nativeArray[j + 1].m_Phase;
					if (IsValidControlScheme(nextPhase, m_PrefabSystem))
					{
						nativeArray.Dispose();
						return nextPhase;
					}
				}
			}
			else if (phase == nextPhase)
			{
				nativeArray.Dispose();
				if (!IsValidControlScheme(nextPhase, m_PrefabSystem))
				{
					return Entity.Null;
				}
				return nextPhase;
			}
		}
		nativeArray.Dispose();
		return Entity.Null;
	}
```

- `private IsCompleted(Unity.Entities.Entity tutorial, Unity.Entities.BufferLookup<Game.Tutorials.TutorialAlternative> alternativeData, Unity.Entities.ComponentLookup<Game.Tutorials.TutorialCompleted> completionData) : System.Boolean`  

```csharp
private bool IsCompleted(Entity tutorial, BufferLookup<TutorialAlternative> alternativeData, ComponentLookup<TutorialCompleted> completionData)
	{
		if (completionData.HasComponent(tutorial))
		{
			return true;
		}
		if (alternativeData.TryGetBuffer(tutorial, out var bufferData))
		{
			for (int i = 0; i < bufferData.Length; i++)
			{
				if (completionData.HasComponent(bufferData[i].m_Alternative))
				{
					return true;
				}
			}
		}
		return false;
	}
```

- `public static IsValidControlScheme(Unity.Entities.Entity phase, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public static bool IsValidControlScheme(Entity phase, PrefabSystem prefabSystem)
	{
		TutorialPhasePrefab prefab = prefabSystem.GetPrefab<TutorialPhasePrefab>(phase);
		if (((object)prefab == null || (prefab.m_ControlScheme & TutorialPhasePrefab.ControlScheme.All) != TutorialPhasePrefab.ControlScheme.All) && (InputManager.instance.activeControlScheme != InputManager.ControlScheme.KeyboardAndMouse || (object)prefab == null || (prefab.m_ControlScheme & TutorialPhasePrefab.ControlScheme.KeyboardAndMouse) != TutorialPhasePrefab.ControlScheme.KeyboardAndMouse))
		{
			if (InputManager.instance.activeControlScheme == InputManager.ControlScheme.Gamepad)
			{
				if ((object)prefab == null)
				{
					return false;
				}
				return (prefab.m_ControlScheme & TutorialPhasePrefab.ControlScheme.Gamepad) == TutorialPhasePrefab.ControlScheme.Gamepad;
			}
			return false;
		}
		return true;
	}
```

- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager) : System.Void`  

```csharp
public static void ManualUnlock(Entity entity, EntityArchetype unlockEventArchetype, ref BufferLookup<ForceUIGroupUnlockData> forcedUnlocksFromEntity, ref BufferLookup<UnlockRequirement> unlockRequirementsFromEntity, EntityCommandBuffer.ParallelWriter commandBuffer, int sortKey)
	{
		if (!unlockRequirementsFromEntity.TryGetBuffer(entity, out var bufferData) || bufferData.Length <= 0 || !(bufferData[0].m_Prefab == entity) || (bufferData[0].m_Flags & UnlockFlags.RequireAll) == 0)
		{
			return;
		}
		Entity e = commandBuffer.CreateEntity(sortKey, unlockEventArchetype);
		commandBuffer.SetComponent(sortKey, e, new Unlock(entity));
		if (forcedUnlocksFromEntity.TryGetBuffer(entity, out var bufferData2))
		{
			for (int i = 0; i < bufferData2.Length; i++)
			{
				Entity e2 = commandBuffer.CreateEntity(sortKey, unlockEventArchetype);
				commandBuffer.SetComponent(sortKey, e2, new Unlock(bufferData2[i].m_Entity));
			}
		}
	}
```

- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static void ManualUnlock(Entity entity, EntityArchetype unlockEventArchetype, ref BufferLookup<ForceUIGroupUnlockData> forcedUnlocksFromEntity, ref BufferLookup<UnlockRequirement> unlockRequirementsFromEntity, EntityCommandBuffer.ParallelWriter commandBuffer, int sortKey)
	{
		if (!unlockRequirementsFromEntity.TryGetBuffer(entity, out var bufferData) || bufferData.Length <= 0 || !(bufferData[0].m_Prefab == entity) || (bufferData[0].m_Flags & UnlockFlags.RequireAll) == 0)
		{
			return;
		}
		Entity e = commandBuffer.CreateEntity(sortKey, unlockEventArchetype);
		commandBuffer.SetComponent(sortKey, e, new Unlock(entity));
		if (forcedUnlocksFromEntity.TryGetBuffer(entity, out var bufferData2))
		{
			for (int i = 0; i < bufferData2.Length; i++)
			{
				Entity e2 = commandBuffer.CreateEntity(sortKey, unlockEventArchetype);
				commandBuffer.SetComponent(sortKey, e2, new Unlock(bufferData2[i].m_Entity));
			}
		}
	}
```

- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.BufferLookup`1[[Game.Prefabs.ForceUIGroupUnlockData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& forcedUnlocksFromEntity, Unity.Entities.BufferLookup`1[[Game.Prefabs.UnlockRequirement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unlockRequirementsFromEntity, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey) : System.Void`  

```csharp
public static void ManualUnlock(Entity entity, EntityArchetype unlockEventArchetype, ref BufferLookup<ForceUIGroupUnlockData> forcedUnlocksFromEntity, ref BufferLookup<UnlockRequirement> unlockRequirementsFromEntity, EntityCommandBuffer.ParallelWriter commandBuffer, int sortKey)
	{
		if (!unlockRequirementsFromEntity.TryGetBuffer(entity, out var bufferData) || bufferData.Length <= 0 || !(bufferData[0].m_Prefab == entity) || (bufferData[0].m_Flags & UnlockFlags.RequireAll) == 0)
		{
			return;
		}
		Entity e = commandBuffer.CreateEntity(sortKey, unlockEventArchetype);
		commandBuffer.SetComponent(sortKey, e, new Unlock(entity));
		if (forcedUnlocksFromEntity.TryGetBuffer(entity, out var bufferData2))
		{
			for (int i = 0; i < bufferData2.Length; i++)
			{
				Entity e2 = commandBuffer.CreateEntity(sortKey, unlockEventArchetype);
				commandBuffer.SetComponent(sortKey, e2, new Unlock(bufferData2[i].m_Entity));
			}
		}
	}
```

- `private NonListTutorialPending() : System.Boolean`  

```csharp
private bool NonListTutorialPending()
	{
		Entity entity = FindNextTutorial();
		if (entity != Entity.Null)
		{
			DynamicBuffer<TutorialRef> buffer = base.EntityManager.GetBuffer<TutorialRef>(activeTutorialList, isReadOnly: true);
			for (int i = 0; i < buffer.Length; i++)
			{
				if (buffer[i].m_Tutorial == entity)
				{
					return false;
				}
			}
			return true;
		}
		return false;
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
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_MapTilePurchaseSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		m_GameScreenUISystem = base.World.GetOrCreateSystemManaged<GameScreenUISystem>();
		m_TutorialConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialsConfigurationData>());
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.Exclude<EditorTutorial>());
		m_TutorialPhaseQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialPhaseData>(), ComponentType.Exclude<EditorTutorial>());
		m_TutorialListQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialListData>());
		m_ActiveTutorialListQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialListData>(), ComponentType.ReadOnly<TutorialRef>(), ComponentType.ReadOnly<TutorialActive>());
		m_ActiveTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialActive>());
		m_ActiveTutorialPhaseQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialPhaseData>(), ComponentType.ReadOnly<TutorialPhaseActive>());
		m_PendingTutorialListQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialListData>(), ComponentType.ReadOnly<TutorialRef>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>());
		m_PendingTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialPhaseRef>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<EditorTutorial>());
		m_PendingPriorityTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialPhaseRef>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<ReplaceActiveData>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<EditorTutorial>());
		m_LockedTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<Locked>(), ComponentType.Exclude<EditorTutorial>());
		m_LockedTutorialPhaseQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialPhaseData>(), ComponentType.ReadOnly<Locked>());
		m_LockedTutorialTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialTriggerData>(), ComponentType.ReadOnly<Locked>());
		m_LockedTutorialListQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialListData>(), ComponentType.ReadOnly<Locked>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_ForceAdvisorQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<AdvisorActivationData>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Unlock>());
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
		if (gameMode == GameMode.Game && tutorialEnabled && !ShownTutorials.ContainsKey(kWelcomeIntroKey))
		{
			m_Mode = TutorialMode.Intro;
		}
		ReadSettings();
		if (m_CityConfigurationSystem.unlockMapTiles && (!tutorialEnabled || (ShownTutorials.TryGetValue(kListIntroKey, out var value) && value)))
		{
			TutorialsConfigurationData singleton = m_TutorialConfigurationQuery.GetSingleton<TutorialsConfigurationData>();
			if (base.EntityManager.HasEnabledComponent<Locked>(singleton.m_MapTilesFeature))
			{
				Entity entity = base.EntityManager.CreateEntity(m_UnlockEventArchetype);
				base.EntityManager.SetComponentData(entity, new Unlock(singleton.m_MapTilesFeature));
			}
			m_MapTilePurchaseSystem.UnlockMapTiles();
		}
		ForceAdvisorVisibility();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode gameMode)
	{
		base.OnGamePreload(purpose, gameMode);
		ResetState();
		base.Enabled = gameMode.IsGame();
	}
```

- `public virtual OnResetTutorials() : System.Void`  

```csharp
public virtual void OnResetTutorials()
	{
		if (GameManager.instance.gameMode.IsGameOrEditor())
		{
			ResetState();
			ClearComponents();
			m_Mode = TutorialMode.Intro;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (mode == TutorialMode.Default)
		{
			if (tutorialEnabled)
			{
				UpdateActiveTutorialList();
			}
			if (tutorialEnabled || base.EntityManager.HasComponent<AdvisorActivation>(activeTutorial))
			{
				UpdateActiveTutorial();
				return;
			}
			ClearTutorialLocks();
			SetTutorial(Entity.Null);
			SetTutorialList(Entity.Null);
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		ClearComponents();
	}
```

- `private ReadSettings() : System.Void`  

```csharp
private void ReadSettings()
	{
		NativeArray<Entity> nativeArray = m_TutorialListQuery.ToEntityArray(Allocator.TempJob);
		foreach (Entity item in nativeArray)
		{
			if (m_PrefabSystem.TryGetPrefab<PrefabBase>(item, out var prefab) && ShownTutorials.TryGetValue(prefab.name, out var value))
			{
				if (value)
				{
					CleanupTutorialList(item, passed: true, updateSettings: false);
				}
				else
				{
					SetTutorialShown(item, updateSettings: false);
				}
			}
		}
		nativeArray.Dispose();
		NativeArray<Entity> nativeArray2 = m_TutorialQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray2.Length; i++)
		{
			Entity entity = nativeArray2[i];
			if (!m_PrefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefab2) || !ShownTutorials.TryGetValue(prefab2.name, out var value2))
			{
				continue;
			}
			if (value2)
			{
				CleanupTutorial(entity, passed: true, updateSettings: false);
				continue;
			}
			SetTutorialShown(entity, updateSettings: false);
			NativeArray<TutorialPhaseRef> nativeArray3 = base.EntityManager.GetBuffer<TutorialPhaseRef>(entity, isReadOnly: true).ToNativeArray(Allocator.TempJob);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				Entity phase = nativeArray3[j].m_Phase;
				if (m_PrefabSystem.TryGetPrefab<PrefabBase>(phase, out var prefab3) && ShownTutorials.ContainsKey(prefab3.name))
				{
					SetTutorialShown(phase, updateSettings: false);
				}
			}
			nativeArray3.Dispose();
		}
		nativeArray2.Dispose();
	}
```

- `private ResetState() : System.Void`  

```csharp
private void ResetState()
	{
		m_Mode = TutorialMode.Default;
		m_AccumulatedDelay = 0f;
		SetTutorial(Entity.Null);
		SetTutorialList(Entity.Null);
	}
```

- `public SetAllTutorialsShown() : System.Void`  

```csharp
public void SetAllTutorialsShown()
	{
		if (!m_TutorialQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_TutorialQuery.ToEntityArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				SetTutorialShown(nativeArray[i]);
			}
			nativeArray.Dispose();
		}
		if (!m_TutorialPhaseQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray2 = m_TutorialPhaseQuery.ToEntityArray(Allocator.TempJob);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				SetTutorialShown(nativeArray2[j]);
			}
			nativeArray2.Dispose();
		}
	}
```

- `private SetTutorial(Unity.Entities.Entity tutorial, System.Boolean passed = False) : System.Void`  

```csharp
public void SetTutorial(Entity tutorial, Entity phase)
	{
		SetTutorial(tutorial, phase, passed: false);
	}
```

- `public SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean passed) : System.Void`  

```csharp
public void SetTutorial(Entity tutorial, Entity phase)
	{
		SetTutorial(tutorial, phase, passed: false);
	}
```

- `public SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  

```csharp
public void SetTutorial(Entity tutorial, Entity phase)
	{
		SetTutorial(tutorial, phase, passed: false);
	}
```

- `private SetTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private void SetTutorialList(Entity tutorialList, bool passed = false, bool updateSettings = true)
	{
		Entity entity = activeTutorialList;
		if (!(tutorialList != entity))
		{
			return;
		}
		if (entity != Entity.Null)
		{
			CleanupTutorialList(entity, passed, updateSettings);
			if (passed)
			{
				TutorialsConfigurationData singleton = m_TutorialConfigurationQuery.GetSingleton<TutorialsConfigurationData>();
				if (updateSettings && entity == singleton.m_TutorialsIntroList && !ShownTutorials.ContainsKey(kListOutroKey))
				{
					mode = TutorialMode.ListOutro;
					UpdateSettings(kListOutroKey, passed: true);
				}
			}
		}
		if (tutorialList != Entity.Null)
		{
			SetTutorialShown(tutorialList, updateSettings);
			base.EntityManager.AddComponent<TutorialActive>(tutorialList);
		}
	}
```

- `private SetTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed) : System.Void`  

```csharp
private void SetTutorialPhase(Entity tutorialPhase, bool passed)
	{
		Entity entity = activeTutorialPhase;
		if (!(tutorialPhase != entity))
		{
			return;
		}
		if (entity != Entity.Null)
		{
			CleanupTutorialPhase(entity, passed);
		}
		if (tutorialPhase != Entity.Null)
		{
			base.EntityManager.AddComponent<TutorialPhaseActive>(tutorialPhase);
			ManualUnlock(tutorialPhase, m_UnlockEventArchetype, base.EntityManager);
			SetTutorialShown(tutorialPhase);
			if (!m_SoundQuery.IsEmptyIgnoreFilter && !m_GameScreenUISystem.isMenuActive && !GameManager.instance.isGameLoading)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TutorialStartedSound);
			}
			if (base.EntityManager.TryGetComponent<TutorialTrigger>(tutorialPhase, out var component))
			{
				base.EntityManager.AddComponent<TriggerActive>(component.m_Trigger);
			}
		}
	}
```

- `private SetTutorialShown(Unity.Entities.Entity entity, System.Boolean updateSettings = True) : System.Void`  

```csharp
private void SetTutorialShown(Entity entity, bool updateSettings = true)
	{
		if (base.EntityManager.HasComponent<TutorialPhaseData>(entity))
		{
			base.EntityManager.AddComponent<TutorialPhaseShown>(entity);
			if (updateSettings)
			{
				UpdateSettings(entity);
			}
		}
		else
		{
			base.EntityManager.AddComponent<TutorialShown>(entity);
			if (updateSettings)
			{
				UpdateSettings(entity);
			}
		}
		if (base.EntityManager.TryGetComponent<UIObjectData>(entity, out var component) && component.m_Group != Entity.Null)
		{
			SetTutorialShown(component.m_Group, updateSettings: false);
		}
	}
```

- `private ShouldReplaceActiveTutorial() : System.Boolean`  

```csharp
private bool ShouldReplaceActiveTutorial()
	{
		Entity entity = activeTutorial;
		if (entity != Entity.Null)
		{
			if (base.EntityManager.HasComponent<ForceActivation>(entity))
			{
				return false;
			}
			if (!base.EntityManager.HasComponent<TutorialActivated>(entity))
			{
				return true;
			}
			if (!base.EntityManager.HasComponent<ReplaceActiveData>(entity))
			{
				return !m_PendingPriorityTutorialQuery.IsEmptyIgnoreFilter;
			}
			return false;
		}
		return false;
	}
```

- `private ShouldReplaceActiveTutorialList() : System.Boolean`  

```csharp
private bool ShouldReplaceActiveTutorialList()
	{
		Entity entity = activeTutorialList;
		if (entity != Entity.Null)
		{
			return !base.EntityManager.HasComponent<TutorialActivated>(entity);
		}
		return false;
	}
```

- `public SkipActiveList() : System.Void`  

```csharp
public void SkipActiveList()
	{
		CompleteCurrentTutorialList();
	}
```

- `private UpdateActiveTutorial() : System.Void`  

```csharp
private void UpdateActiveTutorial()
	{
		if (activeTutorial != Entity.Null)
		{
			if (CheckCurrentPhaseCompleted(out var nextPhase))
			{
				CompleteCurrentTutorialPhase(nextPhase);
			}
			if (ShouldReplaceActiveTutorial())
			{
				ActivateNextTutorial();
			}
		}
		if (activeTutorial == Entity.Null)
		{
			ActivateNextTutorial(delay: true);
		}
	}
```

- `private UpdateActiveTutorialList() : System.Void`  

```csharp
private void UpdateActiveTutorialList()
	{
		if (activeTutorialList != Entity.Null)
		{
			CheckListIntro();
			if (CheckCurrentTutorialListCompleted())
			{
				CompleteCurrentTutorialList();
			}
			if (ShouldReplaceActiveTutorialList())
			{
				ActivateNextTutorialList();
			}
		}
		else
		{
			ActivateNextTutorialList();
		}
	}
```

- `private UpdateSettings(Unity.Entities.Entity tutorial, System.Boolean passed = False) : System.Void`  

```csharp
private void UpdateSettings(string name, bool passed)
	{
		Setting setting = m_Setting;
		if (ShownTutorials.TryAdd(name, passed))
		{
			setting.ApplyAndSave();
		}
		else if (passed)
		{
			ShownTutorials[name] = true;
			setting.ApplyAndSave();
		}
	}
```

- `private UpdateSettings(System.String name, System.Boolean passed) : System.Void`  

```csharp
private void UpdateSettings(string name, bool passed)
	{
		Setting setting = m_Setting;
		if (ShownTutorials.TryAdd(name, passed))
		{
			setting.ApplyAndSave();
		}
		else if (passed)
		{
			ShownTutorials[name] = true;
			setting.ApplyAndSave();
		}
	}
```


## Nested types

- `Game.Tutorials.TutorialSystem+TypeHandle`  

