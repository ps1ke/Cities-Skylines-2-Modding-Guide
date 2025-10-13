# Game.Prefabs.CharacterElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct CharacterElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Style;
    public Game.Rendering.BlendWeights m_ShapeWeights;
    public Game.Rendering.BlendWeights m_TextureWeights;
    public Game.Rendering.BlendWeights m_OverlayWeights;
    public Game.Rendering.BlendWeights m_MaskWeights;
    public System.Int32 m_RestPoseClipIndex;
    public System.Int32 m_CorrectiveClipIndex;

}
```


## Fields

- `public Unity.Entities.Entity m_Style`  

```csharp
public Unity.Entities.Entity m_Style;
```

- `public Game.Rendering.BlendWeights m_ShapeWeights`  

```csharp
public Game.Rendering.BlendWeights m_ShapeWeights;
```

- `public Game.Rendering.BlendWeights m_TextureWeights`  

```csharp
public Game.Rendering.BlendWeights m_TextureWeights;
```

- `public Game.Rendering.BlendWeights m_OverlayWeights`  

```csharp
public Game.Rendering.BlendWeights m_OverlayWeights;
```

- `public Game.Rendering.BlendWeights m_MaskWeights`  

```csharp
public Game.Rendering.BlendWeights m_MaskWeights;
```

- `public System.Int32 m_RestPoseClipIndex`  

```csharp
public System.Int32 m_RestPoseClipIndex;
```

- `public System.Int32 m_CorrectiveClipIndex`  

```csharp
public System.Int32 m_CorrectiveClipIndex;
```


