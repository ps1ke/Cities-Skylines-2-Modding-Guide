# Colossal.Mono.Cecil.AssemblyResolveEventHandler

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class AssemblyResolveEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public AssemblyResolveEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Object sender, Colossal.Mono.Cecil.AssemblyNameReference reference, System.AsyncCallback callback, System.Object object);
    public virtual Colossal.Mono.Cecil.AssemblyDefinition EndInvoke(System.IAsyncResult result);
    public virtual Colossal.Mono.Cecil.AssemblyDefinition Invoke(System.Object sender, Colossal.Mono.Cecil.AssemblyNameReference reference);
}
```


## Constructors

- `public AssemblyResolveEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public AssemblyResolveEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Object sender, Colossal.Mono.Cecil.AssemblyNameReference reference, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Object sender, Colossal.Mono.Cecil.AssemblyNameReference reference, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyDefinition EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Object sender, Colossal.Mono.Cecil.AssemblyNameReference reference) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyDefinition Invoke(System.Object sender, Colossal.Mono.Cecil.AssemblyNameReference reference);
```


