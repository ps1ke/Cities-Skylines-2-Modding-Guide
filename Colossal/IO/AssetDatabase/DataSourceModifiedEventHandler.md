# Colossal.IO.AssetDatabase.DataSourceModifiedEventHandler

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class DataSourceModifiedEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public DataSourceModifiedEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.DataSourceModification modification, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.DataSourceModification modification);
}
```


## Constructors

- `public DataSourceModifiedEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public DataSourceModifiedEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.DataSourceModification modification, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.DataSourceModification modification, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.DataSourceModification modification) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.DataSourceModification modification);
```


