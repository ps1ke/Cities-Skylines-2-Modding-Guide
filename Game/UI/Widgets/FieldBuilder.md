# Game.UI.Widgets.FieldBuilder

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class FieldBuilder : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public FieldBuilder(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Reflection.IValueAccessor accessor, System.AsyncCallback callback, System.Object object);
    public virtual Game.UI.Widgets.IWidget EndInvoke(System.IAsyncResult result);
    public virtual Game.UI.Widgets.IWidget Invoke(Game.Reflection.IValueAccessor accessor);
}
```


## Constructors

- `public FieldBuilder(System.Object object, System.IntPtr method)`  

```csharp
public FieldBuilder(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Reflection.IValueAccessor accessor, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Reflection.IValueAccessor accessor, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : Game.UI.Widgets.IWidget`  

```csharp
public virtual Game.UI.Widgets.IWidget EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Reflection.IValueAccessor accessor) : Game.UI.Widgets.IWidget`  

```csharp
public virtual Game.UI.Widgets.IWidget Invoke(Game.Reflection.IValueAccessor accessor);
```


