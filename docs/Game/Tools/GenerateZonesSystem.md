# Game.Tools.GenerateZonesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateZonesSystem : Game.GameSystemBase
{
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Game.Tools.GenerateZonesSystem+TypeHandle __TypeHandle;

    public GenerateZonesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Game.Tools.GenerateZonesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateZonesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateZonesSystem()`  

```csharp
public GenerateZonesSystem();
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

- `Game.Tools.GenerateZonesSystem+CellData`  
- `Game.Tools.GenerateZonesSystem+BaseCell`  
- `Game.Tools.GenerateZonesSystem+FillBlocksListJob`  
- `Game.Tools.GenerateZonesSystem+CreateBlocksJob`  
- `Game.Tools.GenerateZonesSystem+TypeHandle`  

