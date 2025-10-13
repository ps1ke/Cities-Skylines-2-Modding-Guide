# Game.UI.InGame.GameScreenUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class GameScreenUISystem : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GameScreenUISystem+GameScreen> m_ActiveScreenBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CanUseSaveSystem;
    private static const System.String kSavingGameNotificationTitle;
    private static const System.String kGroup;

    public Game.UI.InGame.GameScreenUISystem+GameScreen activeScreen { get; set; }
    public System.Boolean isMenuActive { get; }

    public GameScreenUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void SaveLoadInProgress(System.String name, System.Boolean start);
    public System.Void SetScreen(Game.UI.InGame.GameScreenUISystem+GameScreen screen);
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GameScreenUISystem+GameScreen> m_ActiveScreenBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GameScreenUISystem+GameScreen> m_ActiveScreenBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CanUseSaveSystem`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CanUseSaveSystem;
```

- `private static const System.String kSavingGameNotificationTitle`  

```csharp
private static const System.String kSavingGameNotificationTitle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.UI.InGame.GameScreenUISystem+GameScreen activeScreen { get; set }`  

```csharp
public Game.UI.InGame.GameScreenUISystem+GameScreen activeScreen { get; set; }
```

- `public System.Boolean isMenuActive { get }`  

```csharp
public System.Boolean isMenuActive { get; }
```


## Constructors

- `public GameScreenUISystem()`  

```csharp
[Preserve]
	public GameScreenUISystem()
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
		AddBinding(m_ActiveScreenBinding = new ValueBinding<GameScreen>("game", "activeScreen", GameScreen.Main, new EnumWriter<GameScreen>()));
		AddBinding(new TriggerBinding<GameScreen>("game", "setActiveScreen", SetScreen, new EnumReader<GameScreen>()));
		AddBinding(m_CanUseSaveSystem = new ValueBinding<bool>("game", "canUseSaveSystem", initialValue: true));
		GameManager.instance.onGameSaveLoad += SaveLoadInProgress;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		GameManager.instance.onGameSaveLoad -= SaveLoadInProgress;
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		SetScreen(GameScreen.Main);
	}
```

- `private SaveLoadInProgress(System.String name, System.Boolean start) : System.Void`  

```csharp
private void SaveLoadInProgress(string name, bool start)
	{
		if (start)
		{
			string identifier = "SavingGame" + name;
			LocalizedString? text = LocalizedString.Value(name);
			ProgressState? progressState = ProgressState.Indeterminate;
			NotificationSystem.Push(identifier, null, text, "SavingGame", null, null, progressState);
		}
		else
		{
			string identifier2 = "SavingGame" + name;
			LocalizedString? text = LocalizedString.Value(name);
			ProgressState? progressState = ProgressState.Complete;
			NotificationSystem.Pop(identifier2, 1f, null, text, "SavingGame", null, null, progressState);
		}
		m_CanUseSaveSystem.Update(!start);
	}
```

- `public SetScreen(Game.UI.InGame.GameScreenUISystem+GameScreen screen) : System.Void`  

```csharp
public void SetScreen(GameScreen screen)
	{
		InputManager.instance.hideCursor = screen == GameScreen.FreeCamera;
		InputManager instance = InputManager.instance;
		CursorLockMode cursorLockMode = (((uint)screen <= 1u) ? SharedSettings.instance.graphics.cursorMode.ToUnityCursorMode() : CursorLockMode.None);
		instance.cursorLockMode = cursorLockMode;
		m_ActiveScreenBinding.Update(screen);
	}
```


## Nested types

- `Game.UI.InGame.GameScreenUISystem+GameScreen`  

