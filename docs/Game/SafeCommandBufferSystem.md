# Game.SafeCommandBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Unity.Entities.EntityCommandBufferSystem`  

## Code

```csharp
public class SafeCommandBufferSystem : Unity.Entities.EntityCommandBufferSystem
{
    private System.Boolean m_IsAllowed;

    public SafeCommandBufferSystem();

    public System.Void AllowUsage();
    public Unity.Entities.EntityCommandBuffer CreateCommandBuffer();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean m_IsAllowed`  

```csharp
private System.Boolean m_IsAllowed;
```


## Constructors

- `public SafeCommandBufferSystem()`  

```csharp
public SafeCommandBufferSystem();
```


## Methods

- `public AllowUsage() : System.Void`  

```csharp
public System.Void AllowUsage();
```

- `public CreateCommandBuffer() : Unity.Entities.EntityCommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer CreateCommandBuffer();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


