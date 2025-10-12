# Game.UI.InGame.TutorialsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `protected Game.Tutorials.ITutorialSystem m_TutorialSystem`  
- `private Game.Tutorials.ITutorialSystem m_EditorTutorialSystem`  
- `protected Game.Tutorials.ITutorialUIActivationSystem m_ActivationSystem`  
- `protected Game.Tutorials.ITutorialUIDeactivationSystem m_DeactivationSystem`  
- `protected Game.Tutorials.ITutorialUITriggerSystem m_TriggerSystem`  
- `private Unity.Entities.EntityQuery m_TutorialConfigurationQuery`  
- `private Unity.Entities.EntityQuery m_TutorialCategoryQuery`  
- `protected Unity.Entities.EntityQuery m_UnlockQuery`  
- `protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialListBinding`  
- `protected Colossal.UI.Binding.RawValueBinding m_TutorialCategoriesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_TutorialsBinding`  
- `protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialBinding`  
- `protected Colossal.UI.Binding.RawValueBinding m_ActiveTutorialPhaseBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Unity.Entities.Entity> m_TutorialPendingBinding`  
- `private System.Int32 m_TutorialActiveVersion`  
- `private System.Int32 m_PhaseActiveVersion`  
- `private System.Int32 m_TriggerActiveVersion`  
- `private System.Int32 m_TriggerCompletedVersion`  
- `private System.Int32 m_TutorialShownVersion`  
- `private System.Int32 m_PhaseShownVersion`  
- `private System.Int32 m_PhaseCompletedVersion`  
- `private System.Boolean m_WasEnabled`  
- `private Game.UI.InGame.TutorialsUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Constructors

- `public TutorialsUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <OnCreate>b__25_0() : System.Boolean`  
- `private <OnCreate>b__25_1() : System.Boolean`  
- `private <OnCreate>b__25_2() : System.Boolean`  
- `private <OnCreate>b__25_3() : System.Boolean`  
- `private <OnCreate>b__25_4() : Unity.Entities.Entity`  
- `private <OnCreate>b__25_5() : Unity.Entities.Entity`  
- `private <OnCreate>b__25_6(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private <OnCreate>b__25_7(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private ActivateTutorial(Unity.Entities.Entity tutorial) : System.Void`  
- `private ActivateTutorialPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  
- `private ActivateTutorialTrigger(System.String trigger) : System.Void`  
- `private AlternativeCompleted(Unity.Entities.Entity tutorial) : System.Boolean`  
- `protected BindActiveTutorialList(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected BindTutorial(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity tutorialEntity) : System.Void`  
- `protected BindTutorialGroup(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `protected BindTutorialPhase(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity phaseEntity) : System.Void`  
- `private CompleteActiveTutorial() : System.Void`  
- `protected virtual CompleteActiveTutorialPhase() : System.Void`  
- `private CompleteIntro() : System.Void`  
- `private CompleteIntro(System.Boolean tutorialEnabled) : System.Void`  
- `private CompleteOutro() : System.Void`  
- `private DisactivateTutorialTrigger(System.String trigger) : System.Void`  
- `private ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  
- `private static GetFilters(Game.Prefabs.TutorialPrefab prefab) : System.String[]`  
- `private GetListHintTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private GetSortedCategories(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `private GetVisibleListTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  
- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  
- `private OnSetTutorialTagActive(System.String tag, System.Boolean active) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.TutorialsUISystem+BindingNames`  
- `Game.UI.InGame.TutorialsUISystem+AdvisorItemType`  
- `Game.UI.InGame.TutorialsUISystem+TypeHandle`  

