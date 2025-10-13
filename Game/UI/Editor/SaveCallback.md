# Game.UI.Editor.SaveAssetPanel+SaveCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class SaveCallback : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public SaveCallback(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
}
```


## Constructors

- `public SaveCallback(System.Object object, System.IntPtr method)`  

```csharp
public SaveCallback(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid);
```


