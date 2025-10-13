# Game.Audio.Radio.Radio+OnDemandClips

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnDemandClips : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnDemandClips(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Audio.Radio.Radio+RuntimeSegment segment, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.Audio.Radio.Radio+RuntimeSegment segment);
}
```


## Constructors

- `public OnDemandClips(System.Object object, System.IntPtr method)`  

```csharp
public OnDemandClips(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Audio.Radio.Radio+RuntimeSegment segment, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Audio.Radio.Radio+RuntimeSegment segment, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.Audio.Radio.Radio+RuntimeSegment segment);
```


