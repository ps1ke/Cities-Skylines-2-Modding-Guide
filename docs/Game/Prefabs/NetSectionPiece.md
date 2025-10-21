# Game.Prefabs.NetSectionPiece

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetSectionPiece : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Piece;
    public Game.Prefabs.CompositionFlags m_CompositionAll;
    public Game.Prefabs.CompositionFlags m_CompositionAny;
    public Game.Prefabs.CompositionFlags m_CompositionNone;
    public Game.Prefabs.NetSectionFlags m_SectionAll;
    public Game.Prefabs.NetSectionFlags m_SectionAny;
    public Game.Prefabs.NetSectionFlags m_SectionNone;
    public Game.Prefabs.NetPieceFlags m_Flags;
    public Unity.Mathematics.float3 m_Offset;

}
```


## Fields

- `public Unity.Entities.Entity m_Piece`  

```csharp
public Unity.Entities.Entity m_Piece;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAll`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAll;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAny`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAny;
```

- `public Game.Prefabs.CompositionFlags m_CompositionNone`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionNone;
```

- `public Game.Prefabs.NetSectionFlags m_SectionAll`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionAll;
```

- `public Game.Prefabs.NetSectionFlags m_SectionAny`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionAny;
```

- `public Game.Prefabs.NetSectionFlags m_SectionNone`  

```csharp
public Game.Prefabs.NetSectionFlags m_SectionNone;
```

- `public Game.Prefabs.NetPieceFlags m_Flags`  

```csharp
public Game.Prefabs.NetPieceFlags m_Flags;
```

- `public Unity.Mathematics.float3 m_Offset`  

```csharp
public Unity.Mathematics.float3 m_Offset;
```


