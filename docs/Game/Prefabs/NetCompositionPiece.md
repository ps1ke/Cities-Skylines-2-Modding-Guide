# Game.Prefabs.NetCompositionPiece

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetCompositionPiece : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Piece;
    public Unity.Mathematics.float3 m_Offset;
    public Unity.Mathematics.float3 m_Size;
    public Game.Prefabs.NetSectionFlags m_SectionFlags;
    public Game.Prefabs.NetPieceFlags m_PieceFlags;
    public System.Int32 m_SectionIndex;

}
```


## Fields

- `public Unity.Entities.Entity m_Piece`  

```csharp
public Unity.Entities.Entity m_Piece;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```

- `public Unity.Mathematics.float3 m_Size`  

```csharp
public Unity.Mathematics.float3 m_Size;
```

- `public Game.Prefabs.NetSectionFlags m_SectionFlags`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionFlags;
```

- `public Game.Prefabs.NetPieceFlags m_PieceFlags`  

```csharp
public Game.Prefabs.NetPieceFlags m_PieceFlags;
```

- `public System.Int32 m_SectionIndex`  

```csharp
public System.Int32 m_SectionIndex;
```


