# Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ProgressDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ProgressDelegate(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state);
}
```


## Constructors

- `public ProgressDelegate(System.Object object, System.IntPtr method)`  

```csharp
public ProgressDelegate(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state);
```


