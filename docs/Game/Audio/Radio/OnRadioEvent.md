# Game.Audio.Radio.Radio+OnRadioEvent

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnRadioEvent : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnRadioEvent(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Audio.Radio.Radio radio, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.Audio.Radio.Radio radio);
}
```


## Constructors

- `public OnRadioEvent(System.Object object, System.IntPtr method)`  

```csharp
public OnRadioEvent(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Audio.Radio.Radio radio, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Audio.Radio.Radio radio, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.Audio.Radio.Radio radio);
```


