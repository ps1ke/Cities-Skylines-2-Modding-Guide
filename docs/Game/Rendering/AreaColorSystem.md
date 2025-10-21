# Game.Rendering.AreaColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaColorSystem : Game.GameSystemBase
{
    private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Game.Rendering.AreaColorSystem+TypeHandle __TypeHandle;

    public AreaColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  

```csharp
private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Game.Rendering.AreaColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaColorSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaColorSystem()`  

```csharp
public AreaColorSystem();
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

- `Game.Rendering.AreaColorSystem+FillColorDataJob`  
- `Game.Rendering.AreaColorSystem+TypeHandle`  

