# Game.Audio.Radio.Radio+OnClipChanged

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnClipChanged : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnClipChanged(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset);
}
```


## Constructors

- `public OnClipChanged(System.Object object, System.IntPtr method)`  

```csharp
public OnClipChanged(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset);
```


