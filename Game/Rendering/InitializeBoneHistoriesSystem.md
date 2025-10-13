# Game.Rendering.InitializeBoneHistoriesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeBoneHistoriesSystem : Game.GameSystemBase
{
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle __TypeHandle;

    public InitializeBoneHistoriesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeBoneHistoriesSystem()`  

```csharp
public InitializeBoneHistoriesSystem();
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

- `Game.Rendering.InitializeBoneHistoriesSystem+InitializeBoneHistoriesJob`  
- `Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle`  

