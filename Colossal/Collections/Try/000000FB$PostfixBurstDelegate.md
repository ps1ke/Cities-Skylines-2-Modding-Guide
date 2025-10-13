# Colossal.Collections.UnsafeLinearAllocator+Colossal.Collections.Try_000000FB$PostfixBurstDelegate

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class Try_000000FB$PostfixBurstDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public Try_000000FB$PostfixBurstDelegate(System.Object , System.IntPtr );

    public virtual System.IAsyncResult BeginInvoke(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block, System.AsyncCallback , System.Object );
    public virtual System.Int32 EndInvoke(System.IAsyncResult );
    public virtual System.Int32 Invoke(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block);
}
```


## Constructors

- `public Try_000000FB$PostfixBurstDelegate(System.Object , System.IntPtr )`  

```csharp
public Try_000000FB$PostfixBurstDelegate(System.Object , System.IntPtr );
```


## Methods

- `public virtual BeginInvoke(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block, System.AsyncCallback , System.Object ) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block, System.AsyncCallback , System.Object );
```

- `public virtual EndInvoke(System.IAsyncResult ) : System.Int32`  

```csharp
public virtual System.Int32 EndInvoke(System.IAsyncResult );
```

- `public virtual Invoke(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block) : System.Int32`  

```csharp
public virtual System.Int32 Invoke(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block);
```


