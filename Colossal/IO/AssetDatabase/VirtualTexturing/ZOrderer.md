# Colossal.IO.AssetDatabase.VirtualTexturing.ZOrderer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ZOrderer
{
    private readonly System.Int32 m_TotalSize;
    private System.Int32 m_Index;
    private static readonly System.Int32[] Morton2dLut;

    public System.Int32 TotalNbBlocks { get; }
    public System.Int32 NbReservedBlocks { get; }

    public ZOrderer(System.Int32 totalSize);

    public System.Boolean CanAllocate(System.Int32 nbIndices);
    private static System.Int64 CompactBits(System.Int64 n);
    private static Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords Decode(System.Int64 key);
    private static System.Int32 Encode(System.Int32 x, System.Int32 y);
    public static Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords GetCoords(System.Int32 index);
    public static System.Int32 GetIndex(System.Int32 column, System.Int32 row);
    public System.Int32 ReserveMultipleRects(System.Int32 nbIndices);
}
```


## Fields

- `private readonly System.Int32 m_TotalSize`  

```csharp
private readonly System.Int32 m_TotalSize;
```

- `private System.Int32 m_Index`  

```csharp
private System.Int32 m_Index;
```

- `private static readonly System.Int32[] Morton2dLut`  

```csharp
private static readonly System.Int32[] Morton2dLut;
```


## Properties

- `public System.Int32 TotalNbBlocks { get }`  

```csharp
public System.Int32 TotalNbBlocks { get; }
```

- `public System.Int32 NbReservedBlocks { get }`  

```csharp
public System.Int32 NbReservedBlocks { get; }
```


## Constructors

- `public ZOrderer(System.Int32 totalSize)`  

```csharp
public ZOrderer(System.Int32 totalSize);
```


## Methods

- `public CanAllocate(System.Int32 nbIndices) : System.Boolean`  

```csharp
public System.Boolean CanAllocate(System.Int32 nbIndices);
```

- `private static CompactBits(System.Int64 n) : System.Int64`  

```csharp
private static System.Int64 CompactBits(System.Int64 n);
```

- `private static Decode(System.Int64 key) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords`  

```csharp
private static Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords Decode(System.Int64 key);
```

- `private static Encode(System.Int32 x, System.Int32 y) : System.Int32`  

```csharp
private static System.Int32 Encode(System.Int32 x, System.Int32 y);
```

- `public static GetCoords(System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords`  

```csharp
public static Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords GetCoords(System.Int32 index);
```

- `public static GetIndex(System.Int32 column, System.Int32 row) : System.Int32`  

```csharp
public static System.Int32 GetIndex(System.Int32 column, System.Int32 row);
```

- `public ReserveMultipleRects(System.Int32 nbIndices) : System.Int32`  

```csharp
public System.Int32 ReserveMultipleRects(System.Int32 nbIndices);
```


