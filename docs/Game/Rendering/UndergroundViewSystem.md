# Game.Rendering.UndergroundViewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UndergroundViewSystem : Game.GameSystemBase
{
    private System.Boolean <undergroundOn>k__BackingField;
    private System.Boolean <tunnelsOn>k__BackingField;
    private System.Boolean <pipelinesOn>k__BackingField;
    private System.Boolean <subPipelinesOn>k__BackingField;
    private System.Boolean <waterwaysOn>k__BackingField;
    private System.Boolean <contourLinesOn>k__BackingField;
    private System.Boolean <markersOn>k__BackingField;
    private Game.Net.UtilityTypes <utilityTypes>k__BackingField;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private System.Boolean m_LastWasWaterways;
    private System.Boolean m_LastWasMarkers;
    private System.Boolean m_Loaded;
    private Game.Net.UtilityTypes m_LastUtilityTypes;
    private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle;

    public System.Boolean undergroundOn { get; private set; }
    public System.Boolean tunnelsOn { get; private set; }
    public System.Boolean pipelinesOn { get; private set; }
    public System.Boolean subPipelinesOn { get; private set; }
    public System.Boolean waterwaysOn { get; private set; }
    public System.Boolean contourLinesOn { get; private set; }
    public System.Boolean markersOn { get; private set; }
    public Game.Net.UtilityTypes utilityTypes { get; private set; }

    public UndergroundViewSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <undergroundOn>k__BackingField`  

```csharp
private System.Boolean <undergroundOn>k__BackingField;
```

- `private System.Boolean <tunnelsOn>k__BackingField`  

```csharp
private System.Boolean <tunnelsOn>k__BackingField;
```

- `private System.Boolean <pipelinesOn>k__BackingField`  

```csharp
private System.Boolean <pipelinesOn>k__BackingField;
```

- `private System.Boolean <subPipelinesOn>k__BackingField`  

```csharp
private System.Boolean <subPipelinesOn>k__BackingField;
```

- `private System.Boolean <waterwaysOn>k__BackingField`  

```csharp
private System.Boolean <waterwaysOn>k__BackingField;
```

- `private System.Boolean <contourLinesOn>k__BackingField`  

```csharp
private System.Boolean <contourLinesOn>k__BackingField;
```

- `private System.Boolean <markersOn>k__BackingField`  

```csharp
private System.Boolean <markersOn>k__BackingField;
```

- `private Game.Net.UtilityTypes <utilityTypes>k__BackingField`  

```csharp
private Game.Net.UtilityTypes <utilityTypes>k__BackingField;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem`  

```csharp
private Game.Rendering.UtilityLodUpdateSystem m_UtilityLodUpdateSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private System.Boolean m_LastWasWaterways`  

```csharp
private System.Boolean m_LastWasWaterways;
```

- `private System.Boolean m_LastWasMarkers`  

```csharp
private System.Boolean m_LastWasMarkers;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.UtilityTypes m_LastUtilityTypes`  

```csharp
private Game.Net.UtilityTypes m_LastUtilityTypes;
```

- `private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.UndergroundViewSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean undergroundOn { get; private set }`  

```csharp
public System.Boolean undergroundOn { get; private set; }
```

- `public System.Boolean tunnelsOn { get; private set }`  

```csharp
public System.Boolean tunnelsOn { get; private set; }
```

- `public System.Boolean pipelinesOn { get; private set }`  

```csharp
public System.Boolean pipelinesOn { get; private set; }
```

- `public System.Boolean subPipelinesOn { get; private set }`  

```csharp
public System.Boolean subPipelinesOn { get; private set; }
```

- `public System.Boolean waterwaysOn { get; private set }`  

```csharp
public System.Boolean waterwaysOn { get; private set; }
```

- `public System.Boolean contourLinesOn { get; private set }`  

```csharp
public System.Boolean contourLinesOn { get; private set; }
```

- `public System.Boolean markersOn { get; private set }`  

```csharp
public System.Boolean markersOn { get; private set; }
```

- `public Game.Net.UtilityTypes utilityTypes { get; private set }`  

```csharp
public Game.Net.UtilityTypes utilityTypes { get; private set; }
```


## Constructors

- `public UndergroundViewSystem()`  

```csharp
public UndergroundViewSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Rendering.UndergroundViewSystem+TypeHandle`  

