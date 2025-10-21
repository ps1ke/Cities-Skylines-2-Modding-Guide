# Game.Settings.OnSettingsAppliedHandler

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnSettingsAppliedHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnSettingsAppliedHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Settings.Setting setting, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.Settings.Setting setting);
}
```


## Constructors

- `public OnSettingsAppliedHandler(System.Object object, System.IntPtr method)`  

```csharp
public OnSettingsAppliedHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Settings.Setting setting, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Settings.Setting setting, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Settings.Setting setting) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.Settings.Setting setting);
```


