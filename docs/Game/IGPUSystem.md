# Game.IGPUSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IGPUSystem
{
    public System.Boolean Enabled { get; }
    public System.Boolean IsAsync { get; set; }

    public abstract System.Void OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd);
}
```


## Properties

- `public System.Boolean Enabled { get }`  

```csharp
public System.Boolean Enabled { get; }
```

- `public System.Boolean IsAsync { get; set }`  

```csharp
public System.Boolean IsAsync { get; set; }
```


## Methods

- `public abstract OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
public abstract System.Void OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd);
```


