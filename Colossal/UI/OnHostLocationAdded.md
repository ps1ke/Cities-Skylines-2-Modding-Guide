# Colossal.UI.UISystem+OnHostLocationAdded

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnHostLocationAdded : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnHostLocationAdded(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch);
}
```


## Constructors

- `public OnHostLocationAdded(System.Object object, System.IntPtr method)`  

```csharp
public OnHostLocationAdded(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String uri, System.Collections.Generic.HashSet<System.String> paths, System.Boolean shouldWatch);
```


