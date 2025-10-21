# Game.Tools.GenerateWaterSourcesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateWaterSourcesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
    private Game.Tools.GenerateWaterSourcesSystem+TypeHandle __TypeHandle;

    public GenerateWaterSourcesSystem();

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

- `private Unity.Entities.EntityArchetype m_WaterSourceArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
```

- `private Game.Tools.GenerateWaterSourcesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateWaterSourcesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateWaterSourcesSystem()`  

```csharp
public GenerateWaterSourcesSystem();
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

- `Game.Tools.GenerateWaterSourcesSystem+GenerateBrushesJob`  
- `Game.Tools.GenerateWaterSourcesSystem+TypeHandle`  

