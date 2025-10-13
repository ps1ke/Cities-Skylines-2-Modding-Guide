# Colossal.IO.AssetDatabase.AddAssetFile

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class AddAssetFile : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public AddAssetFile(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db, System.AsyncCallback callback, System.Object object);
    public virtual Colossal.IO.AssetDatabase.IAssetData EndInvoke(System.IAsyncResult result);
    public virtual Colossal.IO.AssetDatabase.IAssetData Invoke(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
}
```


## Constructors

- `public AddAssetFile(System.Object object, System.IntPtr method)`  

```csharp
public AddAssetFile(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public virtual Colossal.IO.AssetDatabase.IAssetData EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public virtual Colossal.IO.AssetDatabase.IAssetData Invoke(Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
```


