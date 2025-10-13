# Game.Simulation.XPBuiltSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class XPBuiltSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuiltGroup;
    private Unity.Entities.EntityQuery m_ElectricityGroup;
    private Game.Simulation.XPSystem m_XPSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kElectricityGridXPBonus;

    public XPBuiltSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuiltGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuiltGroup;
```

- `private Unity.Entities.EntityQuery m_ElectricityGroup`  

```csharp
private Unity.Entities.EntityQuery m_ElectricityGroup;
```

- `private Game.Simulation.XPSystem m_XPSystem`  

```csharp
private Game.Simulation.XPSystem m_XPSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kElectricityGridXPBonus`  

```csharp
private static readonly System.Int32 kElectricityGridXPBonus;
```


## Constructors

- `public XPBuiltSystem()`  

```csharp
public XPBuiltSystem();
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

- `Game.Simulation.XPBuiltSystem+XPBuiltJob`  
- `Game.Simulation.XPBuiltSystem+XPElectricityJob`  
- `Game.Simulation.XPBuiltSystem+TypeHandle`  

