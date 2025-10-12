# Game.Tutorials.TutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tutorials.ITutorialSystem`, `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  
- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  
- `private Unity.Entities.EntityQuery m_TutorialConfigurationQuery`  
- `protected Unity.Entities.EntityQuery m_TutorialQuery`  
- `private Unity.Entities.EntityQuery m_TutorialListQuery`  
- `private Unity.Entities.EntityQuery m_TutorialPhaseQuery`  
- `private Unity.Entities.EntityQuery m_ActiveTutorialListQuery`  
- `protected Unity.Entities.EntityQuery m_ActiveTutorialQuery`  
- `private Unity.Entities.EntityQuery m_ActiveTutorialPhaseQuery`  
- `protected Unity.Entities.EntityQuery m_PendingTutorialListQuery`  
- `protected Unity.Entities.EntityQuery m_PendingTutorialQuery`  
- `protected Unity.Entities.EntityQuery m_PendingPriorityTutorialQuery`  
- `protected Unity.Entities.EntityQuery m_LockedTutorialQuery`  
- `private Unity.Entities.EntityQuery m_LockedTutorialPhaseQuery`  
- `private Unity.Entities.EntityQuery m_LockedTutorialTriggerQuery`  
- `private Unity.Entities.EntityQuery m_LockedTutorialListQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_ForceAdvisorQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private System.Single m_AccumulatedDelay`  
- `protected Game.Tutorials.TutorialMode m_Mode`  
- `protected Game.Settings.Setting m_Setting`  
- `private Game.Tutorials.TutorialSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Single kBalloonCompletionDelay`  
- `private static readonly System.Single kCompletionDelay`  
- `private static readonly System.Single kActivationDelay`  
- `private static readonly System.String kWelcomeIntroKey`  
- `protected static readonly System.String kListIntroKey`  
- `private static readonly System.String kListOutroKey`  

## Properties

- `protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get }`  
- `public Game.Tutorials.TutorialMode mode { get; set }`  
- `public Unity.Entities.Entity activeTutorial { get }`  
- `public Unity.Entities.Entity activeTutorialPhase { get }`  
- `public System.Boolean tutorialEnabled { get; set }`  
- `public Unity.Entities.Entity activeTutorialList { get }`  
- `public Unity.Entities.Entity tutorialPending { get }`  
- `public Unity.Entities.Entity nextListTutorial { get }`  
- `public System.Boolean showListReminder { get }`  

## Constructors

- `public TutorialSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private ActivateNextTutorial(System.Boolean delay = False) : System.Void`  
- `private ActivateNextTutorialList() : System.Void`  
- `private CheckCurrentPhaseCompleted(Unity.Entities.Entity& nextPhase) : System.Boolean`  
- `private CheckCurrentTutorialListCompleted() : System.Boolean`  
- `private CheckListIntro() : System.Void`  
- `private CleanupTutorial(Unity.Entities.Entity tutorial, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  
- `private CleanupTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  
- `private CleanupTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  
- `private ClearComponents() : System.Void`  
- `private ClearLock(Unity.Entities.Entity entity) : System.Void`  
- `private ClearLocks(Unity.Entities.EntityQuery query) : System.Void`  
- `private ClearTutorialLocks() : System.Void`  
- `private CompleteCurrentTutorialList() : System.Void`  
- `public CompleteCurrentTutorialPhase() : System.Void`  
- `public CompleteCurrentTutorialPhase(Unity.Entities.Entity nextPhase) : System.Void`  
- `public CompleteTutorial(Unity.Entities.Entity tutorial) : System.Void`  
- `private FindNextTutorial() : Unity.Entities.Entity`  
- `private FindNextTutorial(Unity.Entities.EntityQuery query) : Unity.Entities.Entity`  
- `private FindNextTutorialList(Unity.Entities.EntityQuery query) : Unity.Entities.Entity`  
- `private ForceAdvisor(Unity.Entities.Entity entity) : System.Void`  
- `private ForceAdvisorVisibility() : System.Void`  
- `public ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  
- `private static GetCompletionDelay(Game.Tutorials.TutorialPhaseData phase) : System.Single`  
- `private GetFirstTutorialPhase(Unity.Entities.Entity tutorial) : Unity.Entities.Entity`  
- `private GetNextPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity currentPhase, Unity.Entities.Entity nextPhase) : Unity.Entities.Entity`  
- `private IsCompleted(Unity.Entities.Entity tutorial, Unity.Entities.BufferLookup<Game.Tutorials.TutorialAlternative> alternativeData, Unity.Entities.ComponentLookup<Game.Tutorials.TutorialCompleted> completionData) : System.Boolean`  
- `public static IsValidControlScheme(Unity.Entities.Entity phase, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  
- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager) : System.Void`  
- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.EntityManager entityManager, Unity.Entities.EntityCommandBuffer commandBuffer) : System.Void`  
- `public static ManualUnlock(Unity.Entities.Entity entity, Unity.Entities.EntityArchetype unlockEventArchetype, Unity.Entities.BufferLookup`1[[Game.Prefabs.ForceUIGroupUnlockData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& forcedUnlocksFromEntity, Unity.Entities.BufferLookup`1[[Game.Prefabs.UnlockRequirement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unlockRequirementsFromEntity, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 sortKey) : System.Void`  
- `private NonListTutorialPending() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  
- `public virtual OnResetTutorials() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private ReadSettings() : System.Void`  
- `private ResetState() : System.Void`  
- `public SetAllTutorialsShown() : System.Void`  
- `private SetTutorial(Unity.Entities.Entity tutorial, System.Boolean passed = False) : System.Void`  
- `public SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean passed) : System.Void`  
- `public SetTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  
- `private SetTutorialList(Unity.Entities.Entity tutorialList, System.Boolean passed = False, System.Boolean updateSettings = True) : System.Void`  
- `private SetTutorialPhase(Unity.Entities.Entity tutorialPhase, System.Boolean passed) : System.Void`  
- `private SetTutorialShown(Unity.Entities.Entity entity, System.Boolean updateSettings = True) : System.Void`  
- `private ShouldReplaceActiveTutorial() : System.Boolean`  
- `private ShouldReplaceActiveTutorialList() : System.Boolean`  
- `public SkipActiveList() : System.Void`  
- `private UpdateActiveTutorial() : System.Void`  
- `private UpdateActiveTutorialList() : System.Void`  
- `private UpdateSettings(Unity.Entities.Entity tutorial, System.Boolean passed = False) : System.Void`  
- `private UpdateSettings(System.String name, System.Boolean passed) : System.Void`  

## Nested types

- `Game.Tutorials.TutorialSystem+TypeHandle`  

