# Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public ProgressDelegate(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State state) : System.Void`  

