# Game.Rendering.EditorGizmoSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorGizmoSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RenderQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.EditorGizmoSystem+TypeHandle __TypeHandle;

    public EditorGizmoSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RenderQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.EditorGizmoSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.EditorGizmoSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EditorGizmoSystem()`  

```csharp
public EditorGizmoSystem();
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

- `Game.Rendering.EditorGizmoSystem+EditorGizmoJob`  
- `Game.Rendering.EditorGizmoSystem+TypeHandle`  

