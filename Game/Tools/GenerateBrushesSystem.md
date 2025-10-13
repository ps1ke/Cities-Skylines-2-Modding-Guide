# Game.Tools.GenerateBrushesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateBrushesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Game.Tools.GenerateBrushesSystem+TypeHandle __TypeHandle;

    public GenerateBrushesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Game.Tools.GenerateBrushesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateBrushesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateBrushesSystem()`  

```csharp
public GenerateBrushesSystem();
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

- `Game.Tools.GenerateBrushesSystem+GenerateBrushesJob`  
- `Game.Tools.GenerateBrushesSystem+TypeHandle`  

