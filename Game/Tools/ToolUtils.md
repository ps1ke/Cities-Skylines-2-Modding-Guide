# Game.Tools.ToolUtils

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ToolUtils
{
    public static const System.Single WATER_DEPTH_LIMIT;
    public static const System.Int32 MAX_ACTIVE_INFOMODES;
    public static const System.Int32 INFOMODE_COLOR_GROUP_COUNT;
    public static const System.Int32 INFOMODE_COLOR_GROUP_SIZE;
    public static const System.Int32 INFOMODE_COLOR_GROUP_TERRAIN;
    public static const System.Int32 INFOMODE_COLOR_GROUP_WATER;
    public static const System.Int32 INFOMODE_COLOR_GROUP_OTHER;

    public static System.Void AddSnapLine(Game.Tools.ControlPoint& bestSnapPosition, Unity.Collections.NativeList<Game.Tools.SnapLine> snapLines, Game.Tools.SnapLine snapLine);
    public static System.Void AddSnapPosition(Game.Tools.ControlPoint& bestSnapPosition, Game.Tools.ControlPoint snapPosition);
    public static Unity.Mathematics.quaternion CalculateRotation(Unity.Mathematics.float2 direction);
    public static Unity.Mathematics.float2 CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 origPos, Unity.Mathematics.float3 newPos, Unity.Mathematics.float2 direction);
    public static Unity.Mathematics.float2 CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 offset);
    public static System.Boolean CompareSnapPriority(Unity.Mathematics.float2 priority, Unity.Mathematics.float2 other);
    public static System.Void DirectionSnap(System.Single& bestDirectionDistance, Unity.Mathematics.float3& resultPos, Unity.Mathematics.float3& resultDir, Unity.Mathematics.float3 refPos, Unity.Mathematics.float3 snapOrig, Unity.Mathematics.float3 snapDir, System.Single snapDistance);
    public static Colossal.Mathematics.Bounds2 GetBounds(Game.Tools.Brush brush);
    public static System.Single GetRandomAge(Unity.Mathematics.Random& random, Game.Tools.AgeMask ageMask);
}
```


## Fields

- `public static const System.Single WATER_DEPTH_LIMIT`  

```csharp
public static const System.Single WATER_DEPTH_LIMIT;
```

- `public static const System.Int32 MAX_ACTIVE_INFOMODES`  

```csharp
public static const System.Int32 MAX_ACTIVE_INFOMODES;
```

- `public static const System.Int32 INFOMODE_COLOR_GROUP_COUNT`  

```csharp
public static const System.Int32 INFOMODE_COLOR_GROUP_COUNT;
```

- `public static const System.Int32 INFOMODE_COLOR_GROUP_SIZE`  

```csharp
public static const System.Int32 INFOMODE_COLOR_GROUP_SIZE;
```

- `public static const System.Int32 INFOMODE_COLOR_GROUP_TERRAIN`  

```csharp
public static const System.Int32 INFOMODE_COLOR_GROUP_TERRAIN;
```

- `public static const System.Int32 INFOMODE_COLOR_GROUP_WATER`  

```csharp
public static const System.Int32 INFOMODE_COLOR_GROUP_WATER;
```

- `public static const System.Int32 INFOMODE_COLOR_GROUP_OTHER`  

```csharp
public static const System.Int32 INFOMODE_COLOR_GROUP_OTHER;
```


## Methods

- `public static AddSnapLine(Game.Tools.ControlPoint& bestSnapPosition, Unity.Collections.NativeList<Game.Tools.SnapLine> snapLines, Game.Tools.SnapLine snapLine) : System.Void`  

```csharp
public static System.Void AddSnapLine(Game.Tools.ControlPoint& bestSnapPosition, Unity.Collections.NativeList<Game.Tools.SnapLine> snapLines, Game.Tools.SnapLine snapLine);
```

- `public static AddSnapPosition(Game.Tools.ControlPoint& bestSnapPosition, Game.Tools.ControlPoint snapPosition) : System.Void`  

```csharp
public static System.Void AddSnapPosition(Game.Tools.ControlPoint& bestSnapPosition, Game.Tools.ControlPoint snapPosition);
```

- `public static CalculateRotation(Unity.Mathematics.float2 direction) : Unity.Mathematics.quaternion`  

```csharp
public static Unity.Mathematics.quaternion CalculateRotation(Unity.Mathematics.float2 direction);
```

- `public static CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 origPos, Unity.Mathematics.float3 newPos, Unity.Mathematics.float2 direction) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 origPos, Unity.Mathematics.float3 newPos, Unity.Mathematics.float2 direction);
```

- `public static CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 offset) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 offset);
```

- `public static CompareSnapPriority(Unity.Mathematics.float2 priority, Unity.Mathematics.float2 other) : System.Boolean`  

```csharp
public static System.Boolean CompareSnapPriority(Unity.Mathematics.float2 priority, Unity.Mathematics.float2 other);
```

- `public static DirectionSnap(System.Single& bestDirectionDistance, Unity.Mathematics.float3& resultPos, Unity.Mathematics.float3& resultDir, Unity.Mathematics.float3 refPos, Unity.Mathematics.float3 snapOrig, Unity.Mathematics.float3 snapDir, System.Single snapDistance) : System.Void`  

```csharp
public static System.Void DirectionSnap(System.Single& bestDirectionDistance, Unity.Mathematics.float3& resultPos, Unity.Mathematics.float3& resultDir, Unity.Mathematics.float3 refPos, Unity.Mathematics.float3 snapOrig, Unity.Mathematics.float3 snapDir, System.Single snapDistance);
```

- `public static GetBounds(Game.Tools.Brush brush) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 GetBounds(Game.Tools.Brush brush);
```

- `public static GetRandomAge(Unity.Mathematics.Random& random, Game.Tools.AgeMask ageMask) : System.Single`  

```csharp
public static System.Single GetRandomAge(Unity.Mathematics.Random& random, Game.Tools.AgeMask ageMask);
```


