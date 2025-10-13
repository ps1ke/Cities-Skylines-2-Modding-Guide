# Game.Tutorials.EditorTutorialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialSystem`  
**Implements:** `Game.Tutorials.ITutorialSystem`, `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class EditorTutorialSystem : Game.Tutorials.TutorialSystem, Game.Tutorials.ITutorialSystem, Game.Serialization.IPreDeserialize
{
    protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get; }
    public System.Boolean tutorialEnabled { get; set; }

    public EditorTutorialSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode);
    public virtual System.Void OnResetTutorials();
}
```


## Properties

- `protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get }`  

```csharp
protected System.Collections.Generic.Dictionary<System.String, System.Boolean> ShownTutorials { protected get; }
```

- `public System.Boolean tutorialEnabled { get; set }`  

```csharp
public System.Boolean tutorialEnabled { get; set; }
```


## Constructors

- `public EditorTutorialSystem()`  

```csharp
[Preserve]
	public EditorTutorialSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_Setting = SharedSettings.instance.editor;
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<EditorTutorial>());
		m_ActiveTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialActive>(), ComponentType.ReadOnly<EditorTutorial>());
		m_PendingTutorialListQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialListData>(), ComponentType.ReadOnly<TutorialRef>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.ReadOnly<EditorTutorial>());
		m_PendingTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialPhaseRef>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.ReadOnly<EditorTutorial>());
		m_PendingPriorityTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialPhaseRef>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<ReplaceActiveData>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.ReadOnly<EditorTutorial>());
		m_LockedTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<Locked>(), ComponentType.ReadOnly<EditorTutorial>());
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected override void OnGameLoadingComplete(Purpose purpose, GameMode gameMode)
	{
		base.OnGameLoadingComplete(purpose, gameMode);
		if (gameMode == GameMode.Editor && tutorialEnabled && !ShownTutorials.ContainsKey(TutorialSystem.kListIntroKey))
		{
			m_Mode = TutorialMode.ListIntro;
		}
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode gameMode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode gameMode)
	{
		base.OnGamePreload(purpose, gameMode);
		base.Enabled = gameMode.IsEditor();
	}
```

- `public virtual OnResetTutorials() : System.Void`  

```csharp
public override void OnResetTutorials()
	{
		ShownTutorials.Clear();
		base.OnResetTutorials();
		if (GameManager.instance.gameMode.IsEditor())
		{
			m_Mode = TutorialMode.ListIntro;
		}
	}
```


