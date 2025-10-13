# Game.Objects.RaycastJobs+GetSourceRangesJob

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct GetSourceRangesJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList;
    public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList;
    public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList`  

```csharp
public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_EdgeList;
```

- `public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList`  

```csharp
public Unity.Collections.NativeList<Game.Common.RaycastSystem+EntityResult> m_StaticObjectList;
```

- `public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges`  

```csharp
public Unity.Collections.NativeArray<Unity.Mathematics.int4> m_Ranges;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


