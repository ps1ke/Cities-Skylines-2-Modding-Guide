# Game.Simulation.UpdateGroupSystem+UpdateGroupSizes

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct UpdateGroupSizes
{
    private Unity.Collections.NativeArray<System.Int32> m_MovingObjectUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_TreeUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_BuildingUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_NetUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_LaneUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_CompanyUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_HouseholdUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_CitizenUpdateGroupSizes;
    private Unity.Collections.NativeArray<System.Int32> m_HouseholdPetUpdateGroupSizes;

    public UpdateGroupSizes(Unity.Collections.Allocator allocator);

    public System.Void Clear();
    public System.Void Dispose();
    public Unity.Collections.NativeArray<System.Int32> Get(Unity.Entities.ArchetypeChunk chunk, Game.Simulation.UpdateGroupSystem+UpdateGroupTypes types);
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_MovingObjectUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MovingObjectUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TreeUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TreeUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_BuildingUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_BuildingUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_NetUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_NetUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_LaneUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_LaneUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CompanyUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CompanyUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_HouseholdUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CitizenUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CitizenUpdateGroupSizes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdPetUpdateGroupSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_HouseholdPetUpdateGroupSizes;
```


## Constructors

- `public UpdateGroupSizes(Unity.Collections.Allocator allocator)`  

```csharp
public UpdateGroupSizes(Unity.Collections.Allocator allocator);
```


## Methods

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Get(Unity.Entities.ArchetypeChunk chunk, Game.Simulation.UpdateGroupSystem+UpdateGroupTypes types) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> Get(Unity.Entities.ArchetypeChunk chunk, Game.Simulation.UpdateGroupSystem+UpdateGroupTypes types);
```


