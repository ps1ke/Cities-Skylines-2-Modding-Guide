# Game.Rendering.MarkerIconSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MarkerIconSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.Entity m_SelectedMarker;
    private Unity.Entities.Entity m_FollowedMarker;
    private Unity.Entities.Entity m_SelectedLocation;
    private Unity.Entities.Entity m_FollowedLocation;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Unity.Entities.EntityQuery m_IconQuery;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle;

    public MarkerIconSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AdjustLocations(Unity.Mathematics.float3 selectedLocation, Unity.Mathematics.float3 followedLocation, Unity.Mathematics.float3 cameraPos, Unity.Mathematics.float3 cameraUp);
    private Unity.Entities.Entity CreateMarker(Unity.Entities.Entity target, Unity.Mathematics.float3 position, Game.Rendering.MarkerIconSystem+MarkerType markerType, System.Boolean skipAnimation);
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void RemoveMarker(Unity.Entities.Entity& marker, System.Boolean skipAnimation);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateMarker(Unity.Entities.Entity& marker, Unity.Entities.Entity target, Game.Rendering.MarkerIconSystem+MarkerType markerType, Unity.Mathematics.float3 position, System.Boolean skipAnimation);
}
```


## Fields

- `private Unity.Entities.Entity m_SelectedMarker`  

```csharp
private Unity.Entities.Entity m_SelectedMarker;
```

- `private Unity.Entities.Entity m_FollowedMarker`  

```csharp
private Unity.Entities.Entity m_FollowedMarker;
```

- `private Unity.Entities.Entity m_SelectedLocation`  

```csharp
private Unity.Entities.Entity m_SelectedLocation;
```

- `private Unity.Entities.Entity m_FollowedLocation`  

```csharp
private Unity.Entities.Entity m_FollowedLocation;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MarkerIconSystem()`  

```csharp
public MarkerIconSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AdjustLocations(Unity.Mathematics.float3 selectedLocation, Unity.Mathematics.float3 followedLocation, Unity.Mathematics.float3 cameraPos, Unity.Mathematics.float3 cameraUp) : System.Void`  

```csharp
private System.Void AdjustLocations(Unity.Mathematics.float3 selectedLocation, Unity.Mathematics.float3 followedLocation, Unity.Mathematics.float3 cameraPos, Unity.Mathematics.float3 cameraUp);
```

- `private CreateMarker(Unity.Entities.Entity target, Unity.Mathematics.float3 position, Game.Rendering.MarkerIconSystem+MarkerType markerType, System.Boolean skipAnimation) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity CreateMarker(Unity.Entities.Entity target, Unity.Mathematics.float3 position, Game.Rendering.MarkerIconSystem+MarkerType markerType, System.Boolean skipAnimation);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
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

- `private RemoveMarker(Unity.Entities.Entity& marker, System.Boolean skipAnimation) : System.Void`  

```csharp
private System.Void RemoveMarker(Unity.Entities.Entity& marker, System.Boolean skipAnimation);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private UpdateMarker(Unity.Entities.Entity& marker, Unity.Entities.Entity target, Game.Rendering.MarkerIconSystem+MarkerType markerType, Unity.Mathematics.float3 position, System.Boolean skipAnimation) : System.Void`  

```csharp
private System.Void UpdateMarker(Unity.Entities.Entity& marker, Unity.Entities.Entity target, Game.Rendering.MarkerIconSystem+MarkerType markerType, Unity.Mathematics.float3 position, System.Boolean skipAnimation);
```


## Nested types

- `Game.Rendering.MarkerIconSystem+MarkerType`  
- `Game.Rendering.MarkerIconSystem+Overlap`  
- `Game.Rendering.MarkerIconSystem+FindOverlapIconsJob`  
- `Game.Rendering.MarkerIconSystem+UpdateMarkerLocationJob`  
- `Game.Rendering.MarkerIconSystem+TypeHandle`  

