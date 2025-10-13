# Game.Rendering.BatchInstanceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatchInstanceSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.BatchInstanceSystem+Groups m_Groups;
    private Game.Rendering.BatchInstanceSystem+TypeHandle __TypeHandle;

    public BatchInstanceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.BatchInstanceSystem+Groups m_Groups`  

```csharp
private Game.Rendering.BatchInstanceSystem+Groups m_Groups;
```

- `private Game.Rendering.BatchInstanceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BatchInstanceSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BatchInstanceSystem()`  

```csharp
public BatchInstanceSystem();
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

- `Game.Rendering.BatchInstanceSystem+Groups`  
- `Game.Rendering.BatchInstanceSystem+BatchInstanceJob`  
- `Game.Rendering.BatchInstanceSystem+GroupActionData`  
- `Game.Rendering.BatchInstanceSystem+VelocityData`  
- `Game.Rendering.BatchInstanceSystem+FadeData`  
- `Game.Rendering.BatchInstanceSystem+DequeueFadesJob`  
- `Game.Rendering.BatchInstanceSystem+GroupActionJob`  
- `Game.Rendering.BatchInstanceSystem+TypeHandle`  

