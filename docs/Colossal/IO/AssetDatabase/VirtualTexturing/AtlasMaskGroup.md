# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `internal System.Int32 m_MultiStackLayersMask`  
- `internal System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+MaterialEntry> materialGuids`  
- `internal System.Collections.Generic.List<System.Int64> textures`  
- `internal System.Collections.Generic.Queue<System.Int32> potentialDuplicates`  
- `internal System.Int32 m_QueueIdex`  

## Properties

- `internal System.Int32 Count { internal get }`  

## Constructors

- `public AtlasMaskGroup(System.Int32 multiStackLayersMask)`  

## Methods

- `public Dequeue(Colossal.Hash128& guid, Colossal.Hash128[]& duplicates) : System.Boolean`  
- `public Enqueue(Colossal.Hash128 guid, System.Int64 textureHash) : System.Void`  
- `public Enqueue(Colossal.Hash128 guid) : System.Void`  
- `public ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]> materialTextures) : System.Int32`  

## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+MaterialEntry`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaskGroup+<>c`  

