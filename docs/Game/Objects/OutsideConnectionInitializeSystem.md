# Game.Objects.OutsideConnectionInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OutsideConnectionInitializeSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_ExistingQuery;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle;
    private static const System.Single kNearbyMaxDistanceSqr;

    public OutsideConnectionInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Prefabs.OutsideConnectionTransferType GetTransferType(Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionData);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private static System.Boolean TryGetNearestConnectionRandomIndex(Unity.Collections.NativeList<Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo> connections, Game.Prefabs.OutsideConnectionTransferType transferType, Unity.Mathematics.float3 position, Game.Common.RandomLocalizationIndex& randomIndex);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ExistingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExistingQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single kNearbyMaxDistanceSqr`  

```csharp
private static const System.Single kNearbyMaxDistanceSqr;
```


## Constructors

- `public OutsideConnectionInitializeSystem()`  

```csharp
public OutsideConnectionInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static GetTransferType(Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionData) : Game.Prefabs.OutsideConnectionTransferType`  

```csharp
private static Game.Prefabs.OutsideConnectionTransferType GetTransferType(Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionData);
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private static TryGetNearestConnectionRandomIndex(Unity.Collections.NativeList<Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo> connections, Game.Prefabs.OutsideConnectionTransferType transferType, Unity.Mathematics.float3 position, Game.Common.RandomLocalizationIndex& randomIndex) : System.Boolean`  

```csharp
private static System.Boolean TryGetNearestConnectionRandomIndex(Unity.Collections.NativeList<Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo> connections, Game.Prefabs.OutsideConnectionTransferType transferType, Unity.Mathematics.float3 position, Game.Common.RandomLocalizationIndex& randomIndex);
```


## Nested types

- `Game.Objects.OutsideConnectionInitializeSystem+CollectOutsideConnectionsJob`  
- `Game.Objects.OutsideConnectionInitializeSystem+InitializeLocalizationJob`  
- `Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo`  
- `Game.Objects.OutsideConnectionInitializeSystem+TypeHandle`  

