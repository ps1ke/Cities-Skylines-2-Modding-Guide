# Colossal.UI.ViewListener

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.IViewListener`  
**Implements:** `System.IDisposable`, `Colossal.UI.IUnityViewListener`  

## Fields

- `private System.Action BindingsReleased`  
- `private System.Action<System.String> FinishLoad`  
- `private System.Action DOMBuilt`  
- `private System.Action<System.String, System.String> LoadFailed`  
- `private System.Func<System.String, System.Boolean> NavigateTo`  
- `private System.Action ReadyForBindings`  
- `private System.Action ScriptContextCreated`  
- `private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions> NodeKeyEvent`  
- `private System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeMouseEvent`  
- `private System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions> NodeTouched`  
- `private System.Action<cohtml.Net.Cursors, System.String> CursorChanged`  
- `private System.Action<cohtml.Net.ControlType> TextInputTypeChanged`  
- `private System.Action<System.Net.WebSockets.WebSocketState> <OnWebsocketStateChanged>k__BackingField`  
- `private System.Func<System.Int32> <OnWebsocketTimeoutSet>k__BackingField`  
- `private System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32> CaretRectChanged`  
- `private System.Action<System.Int32, System.Int32, System.Int32, System.Single> <OnAudioStreamCreate>k__BackingField`  
- `private System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> <OnAudioDataReceive>k__BackingField`  
- `private System.Action<System.Int32> <OnAudioStreamPlayed>k__BackingField`  
- `private System.Action<System.Int32> <OnAudioStreamPaused>k__BackingField`  
- `private System.Action<System.Int32, System.Single> <OnAudioStreamVolumeChange>k__BackingField`  
- `private System.Action<System.Int32> <OnAudioStreamEnds>k__BackingField`  
- `private System.Action<System.Int32> <OnAudioStreamClose>k__BackingField`  
- `private static Colossal.Logging.ILog log`  

## Properties

- `public System.Action<System.Net.WebSockets.WebSocketState> OnWebsocketStateChanged { get; set }`  
- `public System.Func<System.Int32> OnWebsocketTimeoutSet { get; set }`  
- `public System.Action<System.Int32, System.Int32, System.Int32, System.Single> OnAudioStreamCreate { get; set }`  
- `public System.Action<System.Int32, System.Int32, System.IntPtr, System.Int32> OnAudioDataReceive { get; set }`  
- `public System.Action<System.Int32> OnAudioStreamPlayed { get; set }`  
- `public System.Action<System.Int32> OnAudioStreamPaused { get; set }`  
- `public System.Action<System.Int32, System.Single> OnAudioStreamVolumeChange { get; set }`  
- `public System.Action<System.Int32> OnAudioStreamEnds { get; set }`  
- `public System.Action<System.Int32> OnAudioStreamClose { get; set }`  

## Constructors

- `public ViewListener()`  

## Methods

- `public virtual OnAudioDataReceived(System.Int32 id, System.Int32 samples, System.IntPtr pcm, System.Int32 channels) : System.Void`  
- `public virtual OnAudioStreamClosed(System.Int32 id) : System.Void`  
- `public virtual OnAudioStreamCreated(System.Int32 id, System.Int32 bitDepth, System.Int32 channels, System.Single samplingRate) : System.Void`  
- `public virtual OnAudioStreamEnded(System.Int32 id) : System.Void`  
- `public virtual OnAudioStreamPause(System.Int32 id) : System.Void`  
- `public virtual OnAudioStreamPlay(System.Int32 id) : System.Void`  
- `public virtual OnAudioStreamVolumeChanged(System.Int32 id, System.Single volume) : System.Void`  
- `public virtual OnBindingsReleased() : System.Void`  
- `public virtual OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height) : System.Void`  
- `public virtual OnClipboardTextGet(cohtml.Net.IViewListener+IClipboardData setDataObject) : System.Void`  
- `public virtual OnClipboardTextSet(System.String text, System.UInt32 lengthBytes) : System.Void`  
- `public virtual OnCreateWebSocket(cohtml.Net.ISocketListener listener, System.String url, System.IntPtr protocolsPtr, System.UInt32 protocolsCount) : cohtml.Net.IClientSideSocket`  
- `public virtual OnCursorChanged(cohtml.Net.Cursors cursor, System.String url, System.IntPtr xHotspot, System.IntPtr yHotspot) : System.Void`  
- `public virtual OnDOMBuilt() : System.Void`  
- `public virtual OnFinishLoad(System.String url) : System.Void`  
- `public virtual OnLoadFailed(System.String url, System.String error) : System.Void`  
- `public virtual OnNavigateTo(System.String url) : System.Boolean`  
- `public virtual OnNodeKeyEvent(cohtml.Net.INodeProxy node, cohtml.Net.IKeyEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  
- `public virtual OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  
- `public virtual OnNodeTouched(cohtml.Net.INodeProxy node, cohtml.Net.ITouchEventData arg1, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  
- `public virtual OnReadyForBindings() : System.Void`  
- `public virtual OnScriptContextCreated() : System.Void`  
- `public virtual OnTextInputTypeChanged(cohtml.Net.ControlType type) : System.Void`  

## Events

- `BindingsReleased` : `System.Action`  
- `FinishLoad` : `System.Action<System.String>`  
- `DOMBuilt` : `System.Action`  
- `LoadFailed` : `System.Action<System.String, System.String>`  
- `NavigateTo` : `System.Func<System.String, System.Boolean>`  
- `ReadyForBindings` : `System.Action`  
- `ScriptContextCreated` : `System.Action`  
- `NodeKeyEvent` : `System.Func<cohtml.Net.INodeProxy, cohtml.Net.IKeyEventData, System.IntPtr, cohtml.Net.Actions>`  
- `NodeMouseEvent` : `System.Func<cohtml.Net.INodeProxy, cohtml.Net.IMouseEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions>`  
- `NodeTouched` : `System.Func<cohtml.Net.INodeProxy, cohtml.Net.ITouchEventData, System.IntPtr, cohtml.Net.PhaseType, cohtml.Net.Actions>`  
- `CursorChanged` : `System.Action<cohtml.Net.Cursors, System.String>`  
- `TextInputTypeChanged` : `System.Action<cohtml.Net.ControlType>`  
- `CaretRectChanged` : `System.Action<System.Int32, System.Int32, System.UInt32, System.UInt32>`  

