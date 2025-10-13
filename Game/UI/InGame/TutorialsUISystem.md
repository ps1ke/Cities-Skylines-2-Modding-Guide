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
public TutorialsUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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
private System.Void ActivateTutorial(Unity.Entities.Entity tutorial);
```

- `private ActivateTutorialPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase) : System.Void`  

```csharp
private System.Void ActivateTutorialPhase(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase);
```

- `private ActivateTutorialTrigger(System.String trigger) : System.Void`  

```csharp
private System.Void ActivateTutorialTrigger(System.String trigger);
```

- `private AlternativeCompleted(Unity.Entities.Entity tutorial) : System.Boolean`  

```csharp
private System.Boolean AlternativeCompleted(Unity.Entities.Entity tutorial);
```

- `protected BindActiveTutorialList(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected System.Void BindActiveTutorialList(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindCategories(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindCategories(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected BindTutorial(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity tutorialEntity) : System.Void`  

```csharp
protected System.Void BindTutorial(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity tutorialEntity);
```

- `protected BindTutorialGroup(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected System.Void BindTutorialGroup(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `protected BindTutorialPhase(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity phaseEntity) : System.Void`  

```csharp
protected System.Void BindTutorialPhase(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity phaseEntity);
```

- `private CompleteActiveTutorial() : System.Void`  

```csharp
private System.Void CompleteActiveTutorial();
```

- `protected virtual CompleteActiveTutorialPhase() : System.Void`  

```csharp
protected virtual System.Void CompleteActiveTutorialPhase();
```

- `private CompleteIntro() : System.Void`  

```csharp
private System.Void CompleteIntro();
```

- `private CompleteIntro(System.Boolean tutorialEnabled) : System.Void`  

```csharp
private System.Void CompleteIntro(System.Boolean tutorialEnabled);
```

- `private CompleteOutro() : System.Void`  

```csharp
private System.Void CompleteOutro();
```

- `private DisactivateTutorialTrigger(System.String trigger) : System.Void`  

```csharp
private System.Void DisactivateTutorialTrigger(System.String trigger);
```

- `private ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation) : System.Void`  

```csharp
private System.Void ForceTutorial(Unity.Entities.Entity tutorial, Unity.Entities.Entity phase, System.Boolean advisorActivation);
```

- `private static GetFilters(Game.Prefabs.TutorialPrefab prefab) : System.String[]`  

```csharp
private static System.String[] GetFilters(Game.Prefabs.TutorialPrefab prefab);
```

- `private GetListHintTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> GetListHintTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator);
```

- `private GetSortedCategories(Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedCategories(Unity.Collections.Allocator allocator);
```

- `private GetVisibleListTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator) : Unity.Collections.NativeList<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> GetVisibleListTutorials(Unity.Entities.Entity listEntity, Unity.Collections.Allocator allocator);
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
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

- `private OnSetTutorialTagActive(System.String tag, System.Boolean active) : System.Void`  

```csharp
private System.Void OnSetTutorialTagActive(System.String tag, System.Boolean active);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.UI.InGame.TutorialsUISystem+BindingNames`  
- `Game.UI.InGame.TutorialsUISystem+AdvisorItemType`  
- `Game.UI.InGame.TutorialsUISystem+TypeHandle`  

