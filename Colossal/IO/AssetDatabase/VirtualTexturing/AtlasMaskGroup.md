# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AtlasMaskGroup
{
    internal System.Int32 m_MultiStackLayersMask;
    internal System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+MaterialEntry> materialGuids;
    internal System.Collections.Generic.List<System.Int64> textures;
    internal System.Collections.Generic.Queue<System.Int32> potentialDuplicates;
    internal System.Int32 m_QueueIdex;

    internal System.Int32 Count { internal get; }

    public AtlasMaskGroup(System.Int32 multiStackLayersMask);

    public System.Boolean Dequeue(Colossal.Hash128& guid, Colossal.Hash128[]& duplicates);
    public System.Void Enqueue(Colossal.Hash128 guid, System.Int64 textureHash);
    public System.Void Enqueue(Colossal.Hash128 guid);
    public System.Int32 ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
}
```


## Fields

- `internal System.Int32 m_MultiStackLayersMask`  

```csharp
internal System.Int32 m_MultiStackLayersMask;
```

- `internal System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+MaterialEntry> materialGuids`  

```csharp
internal System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+MaterialEntry> materialGuids;
```

- `internal System.Collections.Generic.List<System.Int64> textures`  

```csharp
internal System.Collections.Generic.List<System.Int64> textures;
```

- `internal System.Collections.Generic.Queue<System.Int32> potentialDuplicates`  

```csharp
internal System.Collections.Generic.Queue<System.Int32> potentialDuplicates;
```

- `internal System.Int32 m_QueueIdex`  

```csharp
internal System.Int32 m_QueueIdex;
```


## Properties

- `internal System.Int32 Count { internal get }`  

```csharp
internal System.Int32 Count { internal get; }
```


## Constructors

- `public AtlasMaskGroup(System.Int32 multiStackLayersMask)`  

```csharp
public AtlasMaskGroup(System.Int32 multiStackLayersMask);
```


## Methods

- `public Dequeue(Colossal.Hash128& guid, Colossal.Hash128[]& duplicates) : System.Boolean`  

```csharp
public System.Boolean Dequeue(Colossal.Hash128& guid, Colossal.Hash128[]& duplicates);
```

- `public Enqueue(Colossal.Hash128 guid, System.Int64 textureHash) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Hash128 guid, System.Int64 textureHash);
```

- `public Enqueue(Colossal.Hash128 guid) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Hash128 guid);
```

- `public ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures) : System.Int32`  

```csharp
public System.Int32 ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures);
```


## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+MaterialEntry`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+<>c`  

