# Game.Rendering.EffectRangeRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EffectRangeRenderSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ProviderQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Rendering.EffectRangeRenderSystem+TypeHandle __TypeHandle;

    public EffectRangeRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProviderQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Rendering.EffectRangeRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.EffectRangeRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EffectRangeRenderSystem()`  

```csharp
public EffectRangeRenderSystem();
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

- `Game.Rendering.EffectRangeRenderSystem+EffectRangeRenderJob`  
- `Game.Rendering.EffectRangeRenderSystem+TypeHandle`  

