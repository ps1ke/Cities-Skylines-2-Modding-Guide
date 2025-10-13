# Colossal.Serialization.Entities.ComponentSerializerChunk

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ComponentSerializerChunk
{
    private readonly Unity.Entities.ArchetypeChunk <chunk>k__BackingField;
    private Unity.Burst.Intrinsics.v128 m_EnabledMask;

    public Unity.Entities.ArchetypeChunk chunk { get; }

    public ComponentSerializerChunk(Unity.Entities.ArchetypeChunk chunk, Unity.Burst.Intrinsics.v128 enabledMask);

    public System.Int32 GetEnabledCount();
    public Unity.Entities.ChunkEntityEnumerator GetEnumerator();
}
```


## Fields

- `private readonly Unity.Entities.ArchetypeChunk <chunk>k__BackingField`  

```csharp
private readonly Unity.Entities.ArchetypeChunk <chunk>k__BackingField;
```

- `private Unity.Burst.Intrinsics.v128 m_EnabledMask`  

```csharp
private Unity.Burst.Intrinsics.v128 m_EnabledMask;
```


## Properties

- `public Unity.Entities.ArchetypeChunk chunk { get }`  

```csharp
public Unity.Entities.ArchetypeChunk chunk { get; }
```


## Constructors

- `public ComponentSerializerChunk(Unity.Entities.ArchetypeChunk chunk, Unity.Burst.Intrinsics.v128 enabledMask)`  

```csharp
public ComponentSerializerChunk(Unity.Entities.ArchetypeChunk chunk, Unity.Burst.Intrinsics.v128 enabledMask);
```


## Methods

- `public GetEnabledCount() : System.Int32`  

```csharp
public System.Int32 GetEnabledCount();
```

- `public GetEnumerator() : Unity.Entities.ChunkEntityEnumerator`  

```csharp
public Unity.Entities.ChunkEntityEnumerator GetEnumerator();
```


