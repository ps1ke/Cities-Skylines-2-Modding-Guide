# Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public DroppedFilesEvent(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint) : System.Void`  

