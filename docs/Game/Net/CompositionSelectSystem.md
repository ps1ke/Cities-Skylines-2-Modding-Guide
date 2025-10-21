# Game.Net.CompositionSelectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompositionSelectSystem : Game.GameSystemBase
{
    private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private System.Boolean m_Loaded;
    private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle;

    public CompositionSelectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem`  

```csharp
private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompositionSelectSystem()`  

```csharp
public CompositionSelectSystem();
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

- `Game.Net.CompositionSelectSystem+CompositionCreateInfo`  
- `Game.Net.CompositionSelectSystem+SelectCompositionJob`  
- `Game.Net.CompositionSelectSystem+CreatedCompositionKey`  
- `Game.Net.CompositionSelectSystem+CreateCompositionJob`  
- `Game.Net.CompositionSelectSystem+TypeHandle`  

