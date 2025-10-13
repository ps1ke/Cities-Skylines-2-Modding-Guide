# Game.SceneFlow.ControllerPairingScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class ControllerPairingScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String continueDisplayProperty { protected get; }
    protected System.String cancelDisplayProperty { protected get; }
    protected System.Int32 cancelDisplayPriority { protected get; }

    public ControllerPairingScreen();

    public virtual System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
}
```


## Properties

- `protected Game.SceneFlow.OverlayScreen overlayScreen { protected get }`  

```csharp
protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
```

- `protected System.String continueDisplayProperty { protected get }`  

```csharp
protected System.String continueDisplayProperty { protected get; }
```

- `protected System.String cancelDisplayProperty { protected get }`  

```csharp
protected System.String cancelDisplayProperty { protected get; }
```

- `protected System.Int32 cancelDisplayPriority { protected get }`  

```csharp
protected System.Int32 cancelDisplayPriority { protected get; }
```


## Constructors

- `public ControllerPairingScreen()`  

```csharp
public ControllerPairingScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
```


## Nested types

- `Game.SceneFlow.ControllerPairingScreen+<>c__DisplayClass8_0`  
- `Game.SceneFlow.ControllerPairingScreen+<Execute>d__8`  

