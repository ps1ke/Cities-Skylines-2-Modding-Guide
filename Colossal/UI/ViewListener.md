# Colossal.UI.ViewListener

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.IViewListener`  
**Implements:** `System.IDisposable`, `Colossal.UI.IUnityViewListener`  

## Code

```csharp
public class ViewListener : cohtml.Net.IViewListener, System.IDisposable, Colossal.UI.IUnityViewListener
{
    private System.Action BindingsReleased;
    private System.Action<System.String> FinishLoad;
    private System.Action DOMBuilt;
    private System.Action<System.String, System.String> LoadFailed;
    private System.Func<System.String, System.Boolean> NavigateTo;
    private System.Action ReadyForBindings;
    private System.Action ScriptContextCreated;
    private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions> NodeKeyEvent;
    private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeMouseEvent;
    private System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeTouched;
    private System.Action<cohtml.Net.Cursors, System.String> CursorChanged;
    private System.Action<cohtml.Net.ControlType> TextInputTypeChanged;
    private System.Action<System.Net.WebSockets.WebSocketState> <OnWebsocketStateChanged>k__BackingField;
    private System.Func<System.Int32> <OnWebsocketTimeoutSet>k__BackingField;
    private System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32> CaretRectChanged;
    private System.Action<System.Int32, System.Int32, System.Int32, System.Single> <OnAudioStreamCreate>k__BackingField;
    private System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> <OnAudioDataReceive>k__BackingField;
    private System.Action<System.Int32> <OnAudioStreamPlayed>k__BackingField;
    private System.Action<System.Int32> <OnAudioStreamPaused>k__BackingField;
    private System.Action<System.Int32, System.Single> <OnAudioStreamVolumeChange>k__BackingField;
    private System.Action<System.Int32> <OnAudioStreamEnds>k__BackingField;
    private System.Action<System.Int32> <OnAudioStreamClose>k__BackingField;
    private static Colossal.Logging.ILog log;

    public System.Action<System.Net.WebSockets.WebSocketState> OnWebsocketStateChanged { get; set; }
    public System.Func<System.Int32> OnWebsocketTimeoutSet { get; set; }
    public System.Action<System.Int32, System.Int32, System.Int32, System.Single> OnAudioStreamCreate { get; set; }
    public System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> OnAudioDataReceive { get; set; }
    public System.Action<System.Int32> OnAudioStreamPlayed { get; set; }
    public System.Action<System.Int32> OnAudioStreamPaused { get; set; }
    public System.Action<System.Int32, System.Single> OnAudioStreamVolumeChange { get; set; }
    public System.Action<System.Int32> OnAudioStreamEnds { get; set; }
    public System.Action<System.Int32> OnAudioStreamClose { get; set; }

    public ViewListener();

    public virtual System.Void OnAudioDataReceived(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels);
    public virtual System.Void OnAudioStreamClosed(System.Int32 id);
    public virtual System.Void OnAudioStreamCreated(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate);
    public virtual System.Void OnAudioStreamEnded(System.Int32 id);
    public virtual System.Void OnAudioStreamPause(System.Int32 id);
    public virtual System.Void OnAudioStreamPlay(System.Int32 id);
    public virtual System.Void OnAudioStreamVolumeChanged(System.Int32 id, System.Single volume);
    public virtual System.Void OnBindingsReleased();
    public virtual System.Void OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height);
    public virtual System.Void OnClipboardTextGet(cohtml.Net.IViewListener+IClipboardData setDataObject);
    public virtual System.Void OnClipboardTextSet(System.String text, System.UInt32 lengthBytes);
    public virtual cohtml.Net.IClientSideSocket OnCreateWebSocket(cohtml.Net.ISocketListener listener, System.String url, System.IntPtr protocolsPtr, System.UInt32 protocolsCount);
    public virtual System.Void OnCursorChanged(cohtml.Net.Cursors cursor, System.String url, System.IntPtr xHotspot, System.IntPtr yHotspot);
    public virtual System.Void OnDOMBuilt();
    public virtual System.Void OnFinishLoad(System.String url);
    public virtual System.Void OnLoadFailed(System.String url, System.String error);
    public virtual System.Boolean OnNavigateTo(System.String url);
    public virtual cohtml.Net.Actions OnNodeKeyEvent(cohtml.Net.INodeProxy node, cohtml.Net.IKeyEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
    public virtual cohtml.Net.Actions OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
    public virtual cohtml.Net.Actions OnNodeTouched(cohtml.Net.INodeProxy node, cohtml.Net.ITouchEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
    public virtual System.Void OnReadyForBindings();
    public virtual System.Void OnScriptContextCreated();
    public virtual System.Void OnTextInputTypeChanged(cohtml.Net.ControlType type);
}
```


## Fields

- `private System.Action BindingsReleased`  

```csharp
private System.Action BindingsReleased;
```

- `private System.Action<System.String> FinishLoad`  

```csharp
private System.Action<System.String> FinishLoad;
```

- `private System.Action DOMBuilt`  

```csharp
private System.Action DOMBuilt;
```

- `private System.Action<System.String, System.String> LoadFailed`  

```csharp
private System.Action<System.String, System.String> LoadFailed;
```

- `private System.Func<System.String, System.Boolean> NavigateTo`  

```csharp
private System.Func<System.String, System.Boolean> NavigateTo;
```

- `private System.Action ReadyForBindings`  

```csharp
private System.Action ReadyForBindings;
```

- `private System.Action ScriptContextCreated`  

```csharp
private System.Action ScriptContextCreated;
```

- `private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions> NodeKeyEvent`  

```csharp
private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions> NodeKeyEvent;
```

- `private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeMouseEvent`  

```csharp
private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeMouseEvent;
```

- `private System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeTouched`  

```csharp
private System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeTouched;
```

- `private System.Action<cohtml.Net.Cursors, System.String> CursorChanged`  

```csharp
private System.Action<cohtml.Net.Cursors, System.String> CursorChanged;
```

- `private System.Action<cohtml.Net.ControlType> TextInputTypeChanged`  

```csharp
private System.Action<cohtml.Net.ControlType> TextInputTypeChanged;
```

- `private System.Action<System.Net.WebSockets.WebSocketState> <OnWebsocketStateChanged>k__BackingField`  

```csharp
private System.Action<System.Net.WebSockets.WebSocketState> <OnWebsocketStateChanged>k__BackingField;
```

- `private System.Func<System.Int32> <OnWebsocketTimeoutSet>k__BackingField`  

```csharp
private System.Func<System.Int32> <OnWebsocketTimeoutSet>k__BackingField;
```

- `private System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32> CaretRectChanged`  

```csharp
private System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32> CaretRectChanged;
```

- `private System.Action<System.Int32, System.Int32, System.Int32, System.Single> <OnAudioStreamCreate>k__BackingField`  

```csharp
private System.Action<System.Int32, System.Int32, System.Int32, System.Single> <OnAudioStreamCreate>k__BackingField;
```

- `private System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> <OnAudioDataReceive>k__BackingField`  

```csharp
private System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> <OnAudioDataReceive>k__BackingField;
```

- `private System.Action<System.Int32> <OnAudioStreamPlayed>k__BackingField`  

```csharp
private System.Action<System.Int32> <OnAudioStreamPlayed>k__BackingField;
```

- `private System.Action<System.Int32> <OnAudioStreamPaused>k__BackingField`  

```csharp
private System.Action<System.Int32> <OnAudioStreamPaused>k__BackingField;
```

- `private System.Action<System.Int32, System.Single> <OnAudioStreamVolumeChange>k__BackingField`  

```csharp
private System.Action<System.Int32, System.Single> <OnAudioStreamVolumeChange>k__BackingField;
```

- `private System.Action<System.Int32> <OnAudioStreamEnds>k__BackingField`  

```csharp
private System.Action<System.Int32> <OnAudioStreamEnds>k__BackingField;
```

- `private System.Action<System.Int32> <OnAudioStreamClose>k__BackingField`  

```csharp
private System.Action<System.Int32> <OnAudioStreamClose>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Properties

- `public System.Action<System.Net.WebSockets.WebSocketState> OnWebsocketStateChanged { get; set }`  

```csharp
public System.Action<System.Net.WebSockets.WebSocketState> OnWebsocketStateChanged { get; set; }
```

- `public System.Func<System.Int32> OnWebsocketTimeoutSet { get; set }`  

```csharp
public System.Func<System.Int32> OnWebsocketTimeoutSet { get; set; }
```

- `public System.Action<System.Int32, System.Int32, System.Int32, System.Single> OnAudioStreamCreate { get; set }`  

```csharp
public System.Action<System.Int32, System.Int32, System.Int32, System.Single> OnAudioStreamCreate { get; set; }
```

- `public System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> OnAudioDataReceive { get; set }`  

```csharp
public System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> OnAudioDataReceive { get; set; }
```

- `public System.Action<System.Int32> OnAudioStreamPlayed { get; set }`  

```csharp
public System.Action<System.Int32> OnAudioStreamPlayed { get; set; }
```

- `public System.Action<System.Int32> OnAudioStreamPaused { get; set }`  

```csharp
public System.Action<System.Int32> OnAudioStreamPaused { get; set; }
```

- `public System.Action<System.Int32, System.Single> OnAudioStreamVolumeChange { get; set }`  

```csharp
public System.Action<System.Int32, System.Single> OnAudioStreamVolumeChange { get; set; }
```

- `public System.Action<System.Int32> OnAudioStreamEnds { get; set }`  

```csharp
public System.Action<System.Int32> OnAudioStreamEnds { get; set; }
```

- `public System.Action<System.Int32> OnAudioStreamClose { get; set }`  

```csharp
public System.Action<System.Int32> OnAudioStreamClose { get; set; }
```


## Constructors

- `public ViewListener()`  

```csharp
public ViewListener();
```


## Methods

- `public virtual OnAudioDataReceived(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels) : System.Void`  

```csharp
public virtual System.Void OnAudioDataReceived(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels);
```

- `public virtual OnAudioStreamClosed(System.Int32 id) : System.Void`  

```csharp
public virtual System.Void OnAudioStreamClosed(System.Int32 id);
```

- `public virtual OnAudioStreamCreated(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate) : System.Void`  

```csharp
public virtual System.Void OnAudioStreamCreated(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate);
```

- `public virtual OnAudioStreamEnded(System.Int32 id) : System.Void`  

```csharp
public virtual System.Void OnAudioStreamEnded(System.Int32 id);
```

- `public virtual OnAudioStreamPause(System.Int32 id) : System.Void`  

```csharp
public virtual System.Void OnAudioStreamPause(System.Int32 id);
```

- `public virtual OnAudioStreamPlay(System.Int32 id) : System.Void`  

```csharp
public virtual System.Void OnAudioStreamPlay(System.Int32 id);
```

- `public virtual OnAudioStreamVolumeChanged(System.Int32 id, System.Single volume) : System.Void`  

```csharp
public virtual System.Void OnAudioStreamVolumeChanged(System.Int32 id, System.Single volume);
```

- `public virtual OnBindingsReleased() : System.Void`  

```csharp
public virtual System.Void OnBindingsReleased();
```

- `public virtual OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height) : System.Void`  

```csharp
public virtual System.Void OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height);
```

- `public virtual OnClipboardTextGet(cohtml.Net.IViewListener+IClipboardData setDataObject) : System.Void`  

```csharp
public virtual System.Void OnClipboardTextGet(cohtml.Net.IViewListener+IClipboardData setDataObject);
```

- `public virtual OnClipboardTextSet(System.String text, System.UInt32 lengthBytes) : System.Void`  

```csharp
public virtual System.Void OnClipboardTextSet(System.String text, System.UInt32 lengthBytes);
```

- `public virtual OnCreateWebSocket(cohtml.Net.ISocketListener listener, System.String url, System.IntPtr protocolsPtr, System.UInt32 protocolsCount) : cohtml.Net.IClientSideSocket`  

```csharp
public virtual cohtml.Net.IClientSideSocket OnCreateWebSocket(cohtml.Net.ISocketListener listener, System.String url, System.IntPtr protocolsPtr, System.UInt32 protocolsCount);
```

- `public virtual OnCursorChanged(cohtml.Net.Cursors cursor, System.String url, System.IntPtr xHotspot, System.IntPtr yHotspot) : System.Void`  

```csharp
public virtual System.Void OnCursorChanged(cohtml.Net.Cursors cursor, System.String url, System.IntPtr xHotspot, System.IntPtr yHotspot);
```

- `public virtual OnDOMBuilt() : System.Void`  

```csharp
public virtual System.Void OnDOMBuilt();
```

- `public virtual OnFinishLoad(System.String url) : System.Void`  

```csharp
public virtual System.Void OnFinishLoad(System.String url);
```

- `public virtual OnLoadFailed(System.String url, System.String error) : System.Void`  

```csharp
public virtual System.Void OnLoadFailed(System.String url, System.String error);
```

- `public virtual OnNavigateTo(System.String url) : System.Boolean`  

```csharp
public virtual System.Boolean OnNavigateTo(System.String url);
```

- `public virtual OnNodeKeyEvent(cohtml.Net.INodeProxy node, cohtml.Net.IKeyEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  

```csharp
public virtual cohtml.Net.Actions OnNodeKeyEvent(cohtml.Net.INodeProxy node, cohtml.Net.IKeyEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
```

- `public virtual OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  

```csharp
public virtual cohtml.Net.Actions OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
```

- `public virtual OnNodeTouched(cohtml.Net.INodeProxy node, cohtml.Net.ITouchEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  

```csharp
public virtual cohtml.Net.Actions OnNodeTouched(cohtml.Net.INodeProxy node, cohtml.Net.ITouchEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
```

- `public virtual OnReadyForBindings() : System.Void`  

```csharp
public virtual System.Void OnReadyForBindings();
```

- `public virtual OnScriptContextCreated() : System.Void`  

```csharp
public virtual System.Void OnScriptContextCreated();
```

- `public virtual OnTextInputTypeChanged(cohtml.Net.ControlType type) : System.Void`  

```csharp
public virtual System.Void OnTextInputTypeChanged(cohtml.Net.ControlType type);
```


## Events

- `BindingsReleased` : `System.Action`  

```csharp
public event System.Action BindingsReleased;
```

- `FinishLoad` : `System.Action<System.String>`  

```csharp
public event System.Action<System.String> FinishLoad;
```

- `DOMBuilt` : `System.Action`  

```csharp
public event System.Action DOMBuilt;
```

- `LoadFailed` : `System.Action<System.String, System.String>`  

```csharp
public event System.Action<System.String, System.String> LoadFailed;
```

- `NavigateTo` : `System.Func<System.String, System.Boolean>`  

```csharp
public event System.Func<System.String, System.Boolean> NavigateTo;
```

- `ReadyForBindings` : `System.Action`  

```csharp
public event System.Action ReadyForBindings;
```

- `ScriptContextCreated` : `System.Action`  

```csharp
public event System.Action ScriptContextCreated;
```

- `NodeKeyEvent` : `System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions>`  

```csharp
public event System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions> NodeKeyEvent;
```

- `NodeMouseEvent` : `System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions>`  

```csharp
public event System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeMouseEvent;
```

- `NodeTouched` : `System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions>`  

```csharp
public event System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeTouched;
```

- `CursorChanged` : `System.Action<cohtml.Net.Cursors, System.String>`  

```csharp
public event System.Action<cohtml.Net.Cursors, System.String> CursorChanged;
```

- `TextInputTypeChanged` : `System.Action<cohtml.Net.ControlType>`  

```csharp
public event System.Action<cohtml.Net.ControlType> TextInputTypeChanged;
```

- `CaretRectChanged` : `System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32>`  

```csharp
public event System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32> CaretRectChanged;
```


