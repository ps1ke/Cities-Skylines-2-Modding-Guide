# Game.SceneFlow.FullScreenOverlay

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public abstract class FullScreenOverlay : Game.SceneFlow.IScreenState
{
    protected System.Action m_CompletedEvent;
    protected System.Boolean m_Done;
    protected static const System.String kEngagementAnyKeyAction;
    protected static const System.String kEngagementContinueAction;
    protected static const System.String kEngagementCancelAction;

    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String actionA { protected get; }
    protected System.String actionB { protected get; }
    protected System.String continueDisplayProperty { protected get; }
    protected System.String cancelDisplayProperty { protected get; }
    protected System.Int32 continueDisplayPriority { protected get; }
    protected System.Int32 cancelDisplayPriority { protected get; }

    protected FullScreenOverlay();

    public abstract System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
    protected virtual System.Boolean HandleScreenChange(Game.SceneFlow.OverlayScreen screen);
}
```


## Fields

- `protected System.Action m_CompletedEvent`  

```csharp
protected System.Action m_CompletedEvent;
```

- `protected System.Boolean m_Done`  

```csharp
protected System.Boolean m_Done;
```

- `protected static const System.String kEngagementAnyKeyAction`  

```csharp
protected static const System.String kEngagementAnyKeyAction;
```

- `protected static const System.String kEngagementContinueAction`  

```csharp
protected static const System.String kEngagementContinueAction;
```

- `protected static const System.String kEngagementCancelAction`  

```csharp
protected static const System.String kEngagementCancelAction;
```


## Properties

- `protected Game.SceneFlow.OverlayScreen overlayScreen { protected get }`  

```csharp
protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
```

- `protected System.String actionA { protected get }`  

```csharp
protected System.String actionA { protected get; }
```

- `protected System.String actionB { protected get }`  

```csharp
protected System.String actionB { protected get; }
```

- `protected System.String continueDisplayProperty { protected get }`  

```csharp
protected System.String continueDisplayProperty { protected get; }
```

- `protected System.String cancelDisplayProperty { protected get }`  

```csharp
protected System.String cancelDisplayProperty { protected get; }
```

- `protected System.Int32 continueDisplayPriority { protected get }`  

```csharp
protected System.Int32 continueDisplayPriority { protected get; }
```

- `protected System.Int32 cancelDisplayPriority { protected get }`  

```csharp
protected System.Int32 cancelDisplayPriority { protected get; }
```


## Constructors

- `protected FullScreenOverlay()`  

```csharp
protected FullScreenOverlay();
```


## Methods

- `public abstract Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
```

- `protected virtual HandleScreenChange(Game.SceneFlow.OverlayScreen screen) : System.Boolean`  

```csharp
protected virtual System.Boolean HandleScreenChange(Game.SceneFlow.OverlayScreen screen);
```


