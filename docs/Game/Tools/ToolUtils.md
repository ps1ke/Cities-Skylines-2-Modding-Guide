# Game.Tools.ToolUtils

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single WATER_DEPTH_LIMIT`  
- `public static const System.Int32 MAX_ACTIVE_INFOMODES`  
- `public static const System.Int32 INFOMODE_COLOR_GROUP_COUNT`  
- `public static const System.Int32 INFOMODE_COLOR_GROUP_SIZE`  
- `public static const System.Int32 INFOMODE_COLOR_GROUP_TERRAIN`  
- `public static const System.Int32 INFOMODE_COLOR_GROUP_WATER`  
- `public static const System.Int32 INFOMODE_COLOR_GROUP_OTHER`  

## Methods

- `public static AddSnapLine(Game.Tools.ControlPoint& bestSnapPosition, Unity.Collections.NativeList<Game.Tools.SnapLine> snapLines, Game.Tools.SnapLine snapLine) : System.Void`  
- `public static AddSnapPosition(Game.Tools.ControlPoint& bestSnapPosition, Game.Tools.ControlPoint snapPosition) : System.Void`  
- `public static CalculateRotation(Unity.Mathematics.float2 direction) : Unity.Mathematics.quaternion`  
- `public static CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 origPos, Unity.Mathematics.float3 newPos, Unity.Mathematics.float2 direction) : Unity.Mathematics.float2`  
- `public static CalculateSnapPriority(System.Single level, System.Single priority, System.Single heightWeight, Unity.Mathematics.float3 offset) : Unity.Mathematics.float2`  
- `public static CompareSnapPriority(Unity.Mathematics.float2 priority, Unity.Mathematics.float2 other) : System.Boolean`  
- `public static DirectionSnap(System.Single& bestDirectionDistance, Unity.Mathematics.float3& resultPos, Unity.Mathematics.float3& resultDir, Unity.Mathematics.float3 refPos, Unity.Mathematics.float3 snapOrig, Unity.Mathematics.float3 snapDir, System.Single snapDistance) : System.Void`  
- `public static GetBounds(Game.Tools.Brush brush) : Colossal.Mathematics.Bounds2`  
- `public static GetRandomAge(Unity.Mathematics.Random& random, Game.Tools.AgeMask ageMask) : System.Single`  

