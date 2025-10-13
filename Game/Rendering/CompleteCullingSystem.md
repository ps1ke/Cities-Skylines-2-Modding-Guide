# Game.Rendering.CompleteCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompleteCullingSystem : Game.GameSystemBase
{
    private Game.Rendering.PreCullingSystem m_CullingSystem;
    private Game.Rendering.CompleteCullingSystem+TypeHandle __TypeHandle;

    public CompleteCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.PreCullingSystem m_CullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_CullingSystem;
```

- `private Game.Rendering.CompleteCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.CompleteCullingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompleteCullingSystem()`  

```csharp
public CompleteCullingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Rendering.CompleteCullingSystem+CullingCleanupJob`  
- `Game.Rendering.CompleteCullingSystem+TypeHandle`  

