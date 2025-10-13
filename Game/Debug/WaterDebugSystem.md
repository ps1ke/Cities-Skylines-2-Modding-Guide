# Game.Debug.WaterDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Unity.Entities.EntityQuery m_WaterSourceGroup;
    private Game.Debug.BaseDebugSystem+Option m_ShowCulling;
    private Game.Debug.BaseDebugSystem+Option m_showSurface;
    private Game.Debug.WaterDebugSystem+TypeHandle __TypeHandle;

    public WaterDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Unity.Entities.EntityQuery m_WaterSourceGroup`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceGroup;
```

- `private Game.Debug.BaseDebugSystem+Option m_ShowCulling`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ShowCulling;
```

- `private Game.Debug.BaseDebugSystem+Option m_showSurface`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_showSurface;
```

- `private Game.Debug.WaterDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.WaterDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterDebugSystem()`  

```csharp
public WaterDebugSystem();
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

- `Game.Debug.WaterDebugSystem+WaterGizmoJob`  
- `Game.Debug.WaterDebugSystem+TypeHandle`  

