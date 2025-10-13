# Game.UI.Widgets.ValueChangedCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ValueChangedCallback : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ValueChangedCallback(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.UI.Widgets.IWidget widget, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.UI.Widgets.IWidget widget);
}
```


## Constructors

- `public ValueChangedCallback(System.Object object, System.IntPtr method)`  

```csharp
public ValueChangedCallback(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.UI.Widgets.IWidget widget, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.UI.Widgets.IWidget widget, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.UI.Widgets.IWidget widget);
```


