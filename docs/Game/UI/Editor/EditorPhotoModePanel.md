# Game.UI.Editor.EditorPhotoModePanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class EditorPhotoModePanel : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem;

    public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }

    public EditorPhotoModePanel();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
}
```


## Fields

- `private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem`  

```csharp
private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem;
```


## Properties

- `public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get }`  

```csharp
public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }
```


## Constructors

- `public EditorPhotoModePanel()`  

```csharp
public EditorPhotoModePanel();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```


