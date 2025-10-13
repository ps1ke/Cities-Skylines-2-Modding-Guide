# Colossal.UI.UIManager+UnityPluginListener

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.IUnityPluginListener`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UnityPluginListener : cohtml.Net.IUnityPluginListener, System.IDisposable
{
    public System.Action<System.IntPtr> PreloadedTextureReleased;

    public UnityPluginListener();

    public virtual System.Void Dispose();
    public virtual System.Void OnPreloadedTextureReleased(System.IntPtr texturePtr);
    public virtual System.Void OnUserImageDropped(System.IntPtr texturePtr);
    public virtual System.Void OnWorkAvailable(cohtml.Net.WorkType type);
}
```


## Fields

- `public System.Action<System.IntPtr> PreloadedTextureReleased`  

```csharp
public System.Action<System.IntPtr> PreloadedTextureReleased;
```


## Constructors

- `public UnityPluginListener()`  

```csharp
public UnityPluginListener();
```


## Methods

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public virtual OnPreloadedTextureReleased(System.IntPtr texturePtr) : System.Void`  

```csharp
public virtual System.Void OnPreloadedTextureReleased(System.IntPtr texturePtr);
```

- `public virtual OnUserImageDropped(System.IntPtr texturePtr) : System.Void`  

```csharp
public virtual System.Void OnUserImageDropped(System.IntPtr texturePtr);
```

- `public virtual OnWorkAvailable(cohtml.Net.WorkType type) : System.Void`  

```csharp
public virtual System.Void OnWorkAvailable(cohtml.Net.WorkType type);
```


