# Game.Common.RaycastInput

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RaycastInput
{
    public Colossal.Mathematics.Line3+Segment m_Line;
    public Unity.Mathematics.float3 m_Offset;
    public Game.Common.TypeMask m_TypeMask;
    public Game.Common.RaycastFlags m_Flags;
    public Game.Common.CollisionMask m_CollisionMask;
    public Game.Net.Layer m_NetLayerMask;
    public Game.Areas.AreaTypeMask m_AreaTypeMask;
    public Game.Routes.RouteType m_RouteType;
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Notifications.IconLayerMask m_IconLayerMask;
    public Game.Net.UtilityTypes m_UtilityTypeMask;

    public System.Boolean IsDisabled();
}
```


## Fields

- `public Colossal.Mathematics.Line3+Segment m_Line`  

```csharp
public Colossal.Mathematics.Line3+Segment m_Line;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```

- `public Game.Common.TypeMask m_TypeMask`  

```csharp
public Game.Common.TypeMask m_TypeMask;
```

- `public Game.Common.RaycastFlags m_Flags`  

```csharp
public Game.Common.RaycastFlags m_Flags;
```

- `public Game.Common.CollisionMask m_CollisionMask`  

```csharp
public Game.Common.CollisionMask m_CollisionMask;
```

- `public Game.Net.Layer m_NetLayerMask`  

```csharp
public Game.Net.Layer m_NetLayerMask;
```

- `public Game.Areas.AreaTypeMask m_AreaTypeMask`  

```csharp
public Game.Areas.AreaTypeMask m_AreaTypeMask;
```

- `public Game.Routes.RouteType m_RouteType`  

```csharp
public Game.Routes.RouteType m_RouteType;
```

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public Game.Notifications.IconLayerMask m_IconLayerMask`  

```csharp
public Game.Notifications.IconLayerMask m_IconLayerMask;
```

- `public Game.Net.UtilityTypes m_UtilityTypeMask`  

```csharp
public Game.Net.UtilityTypes m_UtilityTypeMask;
```


## Methods

- `public IsDisabled() : System.Boolean`  

```csharp
public bool IsDisabled()
	{
		return (m_Flags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable | RaycastFlags.ToolDisable | RaycastFlags.FreeCameraDisable)) != 0;
	}
```


