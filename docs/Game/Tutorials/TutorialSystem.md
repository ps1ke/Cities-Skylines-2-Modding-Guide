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
public TutorialSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private ActivateNextTutorial(System.Boolean delay = False) : System.Void`  

```csharp
private System.Void ActivateNextTutorial(System.Boolean delay);
```

- `private ActivateNextTutorialList() : System.Void`  

```csharp
private System.Void ActivateNextTutorialList();
```

- `private CheckCurrentPhaseCompleted(Unity.Entities.Entity& nextPhase) : System.Boolean`  

```csharp
private System.Boolean CheckCurrentPhaseCompleted(Unity.Entities.Entity& nextPhase);
```

- `private CheckCurrentTutorialListCompleted() : System.Boolean`  

```csharp
private System.Boolean CheckCurrentTutorialListCompleted();
```

- `private CheckListIntro() : System.Void`  

```csharp
private System.Void CheckListIntro();
```

- `private CleanupTutorial(Unity.Entities.Entity tutorial, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private System.Void CleanupTutorial(Unity.Entities.Entity tutorial, System.Boolean passed, System.Boolean updateSettings);
```

- `private CleanupTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private System.Void CleanupTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed, System.Boolean updateSettings);
```

- `private CleanupTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private System.Void CleanupTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed, System.Boolean updateSettings);
```

- `private ClearComponents() : System.Void`  

```csharp
private System.Void ClearComponents();
```

- `private ClearLock(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void ClearLock(Unity.Entities.Entity entity);
```

- `private ClearLocks(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private System.Void ClearLocks(Unity.Entities.EntityQuery query);
```

- `private ClearTutorialLocks() : System.Void`  

```csharp
private System.Void ClearTutorialLocks();
```

- `private CompleteCurrentTutorialList() : System.Void`  

```csharp
private System.Void CompleteCurrentTutorialList();
```

- `public CompleteCurrentTutorialPhase() : System.Void`  

```csharp
public System.Void CompleteCurrentTutorialPhase();
```

- `public CompleteCurrentTutorialPhase(Unity.Entities.Entity nextPhase) : System.Void`  

```csharp
public System.Void CompleteCurrentTutorialPhase(Unity.Entities.Entity nextPhase);
```

- `public CompleteTutorial(Unity.Entities.Entity tutorial) : System.Void`  

```csharp
public System.Void CompleteTutorial(Unity.Entities.Entity tutorial);
```

- `private FindNextTutorial() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity FindNextTutorial();
```

- `private FindNextTutorial(Unity.Entities.EntityQuery query) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity FindNextTutorial(Unity.Entities.EntityQuery query);
```

- `private FindNextTutorialList(Unity.Entities.EntityQuery query) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity FindNextTutorialList(Unity.Entities.EntityQuery query);
```

- `private ForceAdvisor(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void ForceAdvisor(Unity.Entities.Entity entity);
```

- `private ForceAdvisorVisibility() : System.Void`  

```csharp
private System.Void ForceAdvisorVisibility();
```

- `public ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  

```csharp
public System.Void ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation);
```

- `private static GetCompletionDelay(Game.Tutorials.TutorialPhaseData phase) : System.Single`  

```csharp
private static System.Single GetCompletionDelay(Game.Tutorials.TutorialPhaseData phase);
```

- `private GetFirstTutorialPhase(Unity.Entities.Entity tutorial) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetFirstTutorialPhase(Unity.Entities.Entity tutorial);
```

- `private GetNextPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity currentPhase, Unity.Entities.Entity nextPhase) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetNextPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity currentPhase, Unity.Entities.Entity nextPhase);
```

- `private IsCompleted(Unity.Entities.Entity tutorial, Unity.Entities.BufferLookup<Game.Tutorials.TutorialAlternative> alternativeData, Unity.Entities.ComponentLookup<Game.Tutorials.TutorialCompleted> completionData) : System.Boolean`  

```csharp
private System.Boolean IsCompleted(Unity.Entities.Entity tutorial, Unity.Entities.BufferLookup<Game.Tutorials.TutorialAlternative> alternativeData, Unity.Entities.ComponentLookup<Game.Tutorials.TutorialCompleted> completionData);
```

- `public static IsValidControlScheme(Unity.Entities.Entity phase, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public static System.Boolean IsValidControlScheme(Unity.Entities.Entity phase, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager) : System.Void`  

```csharp
public static System.Void ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager);
```

- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  

```csharp
public static System.Void ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer);
```

- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.BufferLookup`1[[Game.Prefabs.ForceUIGroupUnlockData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& forcedUnlocksFromEntity, Unity.Entities.BufferLookup`1[[Game.Prefabs.UnlockRequirement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unlockRequirementsFromEntity, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey) : System.Void`  

```csharp
public static System.Void ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.BufferLookup`1[[Game.Prefabs.ForceUIGroupUnlockData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& forcedUnlocksFromEntity, Unity.Entities.BufferLookup`1[[Game.Prefabs.UnlockRequirement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unlockRequirementsFromEntity, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey);
```

- `private NonListTutorialPending() : System.Boolean`  

```csharp
private System.Boolean NonListTutorialPending();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
```

- `public virtual OnResetTutorials() : System.Void`  

```csharp
public virtual System.Void OnResetTutorials();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private ReadSettings() : System.Void`  

```csharp
private System.Void ReadSettings();
```

- `private ResetState() : System.Void`  

```csharp
private System.Void ResetState();
```

- `public SetAllTutorialsShown() : System.Void`  

```csharp
public System.Void SetAllTutorialsShown();
```

- `private SetTutorial(Unity.Entities.Entity tutorial, System.Boolean passed = False) : System.Void`  

```csharp
private System.Void SetTutorial(Unity.Entities.Entity tutorial, System.Boolean passed);
```

- `public SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean passed) : System.Void`  

```csharp
public System.Void SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean passed);
```

- `public SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  

```csharp
public System.Void SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase);
```

- `private SetTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  

```csharp
private System.Void SetTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed, System.Boolean updateSettings);
```

- `private SetTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed) : System.Void`  

```csharp
private System.Void SetTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed);
```

- `private SetTutorialShown(Unity.Entities.Entity entity, System.Boolean updateSettings = True) : System.Void`  

```csharp
private System.Void SetTutorialShown(Unity.Entities.Entity entity, System.Boolean updateSettings);
```

- `private ShouldReplaceActiveTutorial() : System.Boolean`  

```csharp
private System.Boolean ShouldReplaceActiveTutorial();
```

- `private ShouldReplaceActiveTutorialList() : System.Boolean`  

```csharp
private System.Boolean ShouldReplaceActiveTutorialList();
```

- `public SkipActiveList() : System.Void`  

```csharp
public System.Void SkipActiveList();
```

- `private UpdateActiveTutorial() : System.Void`  

```csharp
private System.Void UpdateActiveTutorial();
```

- `private UpdateActiveTutorialList() : System.Void`  

```csharp
private System.Void UpdateActiveTutorialList();
```

- `private UpdateSettings(Unity.Entities.Entity tutorial, System.Boolean passed = False) : System.Void`  

```csharp
private System.Void UpdateSettings(Unity.Entities.Entity tutorial, System.Boolean passed);
```

- `private UpdateSettings(System.String name, System.Boolean passed) : System.Void`  

```csharp
private System.Void UpdateSettings(System.String name, System.Boolean passed);
```


## Nested types

- `Game.Tutorials.TutorialSystem+TypeHandle`  

