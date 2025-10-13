# Colossal.Win32.UnityDragAndDropHook+DroppedFilesEvent

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class DroppedFilesEvent : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public DroppedFilesEvent(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint);
}
```


## Constructors

- `public DroppedFilesEvent(System.Object object, System.IntPtr method)`  

```csharp
public DroppedFilesEvent(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Collections.Generic.List<System.String> aPathNames, Colossal.Win32.POINT aDropPoint);
```


