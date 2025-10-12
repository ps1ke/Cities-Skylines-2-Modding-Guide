# Game.SceneFlow.FullScreenOverlay

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Fields

- `protected System.Action m_CompletedEvent`  
- `protected System.Boolean m_Done`  
- `protected static const System.String kEngagementAnyKeyAction`  
- `protected static const System.String kEngagementContinueAction`  
- `protected static const System.String kEngagementCancelAction`  

## Properties

- `protected Game.SceneFlow.OverlayScreen overlayScreen { protected get }`  
- `protected System.String actionA { protected get }`  
- `protected System.String actionB { protected get }`  
- `protected System.String continueDisplayProperty { protected get }`  
- `protected System.String cancelDisplayProperty { protected get }`  
- `protected System.Int32 continueDisplayPriority { protected get }`  
- `protected System.Int32 cancelDisplayPriority { protected get }`  

## Constructors

- `protected FullScreenOverlay()`  

## Methods

- `public abstract Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `protected virtual HandleScreenChange(Game.SceneFlow.OverlayScreen screen) : System.Boolean`  

