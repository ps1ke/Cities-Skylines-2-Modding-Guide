# Game.UI.Editor.EditorScreenUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class EditorScreenUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.ValueBinding<Game.UI.Editor.EditorScreenUISystem+EditorScreen> m_ActiveScreenBinding;
    private static const System.String kGroup;

    public Game.UI.Editor.EditorScreenUISystem+EditorScreen activeScreen { get; set; }

    public EditorScreenUISystem();

    protected virtual System.Void OnCreate();
    public System.Void SetScreen(Game.UI.Editor.EditorScreenUISystem+EditorScreen screen);
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<Game.UI.Editor.EditorScreenUISystem+EditorScreen> m_ActiveScreenBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.Editor.EditorScreenUISystem+EditorScreen> m_ActiveScreenBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.UI.Editor.EditorScreenUISystem+EditorScreen activeScreen { get; set }`  

```csharp
public Game.UI.Editor.EditorScreenUISystem+EditorScreen activeScreen { get; set; }
```


## Constructors

- `public EditorScreenUISystem()`  

```csharp
[Preserve]
	public EditorScreenUISystem()
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
		AddBinding(m_ActiveScreenBinding = new ValueBinding<EditorScreen>("editor", "activeScreen", EditorScreen.Main, new EnumWriter<EditorScreen>()));
		AddBinding(new TriggerBinding<EditorScreen>("editor", "setActiveScreen", SetScreen, new EnumReader<EditorScreen>()));
	}
```

- `public SetScreen(Game.UI.Editor.EditorScreenUISystem+EditorScreen screen) : System.Void`  

```csharp
public void SetScreen(EditorScreen screen)
	{
		m_ActiveScreenBinding.Update(screen);
	}
```


## Nested types

- `Game.UI.Editor.EditorScreenUISystem+EditorScreen`  

