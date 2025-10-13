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
public GameScreenUISystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private SaveLoadInProgress(System.String name, System.Boolean start) : System.Void`  

```csharp
private System.Void SaveLoadInProgress(System.String name, System.Boolean start);
```

- `public SetScreen(Game.UI.InGame.GameScreenUISystem+GameScreen screen) : System.Void`  

```csharp
public System.Void SetScreen(Game.UI.InGame.GameScreenUISystem+GameScreen screen);
```


## Nested types

- `Game.UI.InGame.GameScreenUISystem+GameScreen`  

