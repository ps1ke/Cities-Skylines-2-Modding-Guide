# Colossal.IO.AssetDatabase.AtlasFrame

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class AtlasFrame : System.IDisposable, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AtlasFrame+Entry>, System.Collections.IEnumerable
{
    private UnityEngine.Texture2D m_Texture;
    private Colossal.Core.MaxRectsBinPack m_Atlas;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> m_Entries;

    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries { get; }
    public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get; }
    public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get; }
    public UnityEngine.Texture2D texture { get; }
    public System.String name { get; set; }

    public AtlasFrame(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Int32 page);
    public AtlasFrame(UnityEngine.Texture2D texture, System.Boolean rotations, System.Int32 page, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles);

    private UnityEngine.Texture2D CreateTexture(System.Int32 width, System.Int32 height);
    public System.Void Dispose();
    public System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry> GetEnumerator();
    public System.Boolean Grow(System.Boolean forceUniform);
    public System.Void Insert(System.String name, UnityEngine.Texture rt, UnityEngine.Rect region);
    private System.Boolean Reserve(System.Int32 width, System.Int32 height, UnityEngine.Rect& region);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Boolean TryAdd(System.String name, UnityEngine.Texture target);
}
```


## Fields

- `private UnityEngine.Texture2D m_Texture`  

```csharp
private UnityEngine.Texture2D m_Texture;
```

- `private Colossal.Core.MaxRectsBinPack m_Atlas`  

```csharp
private Colossal.Core.MaxRectsBinPack m_Atlas;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> m_Entries`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> m_Entries;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries { get; }
```

- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> freeRectangles { get; }
```

- `public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> usedRectangles { get; }
```

- `public UnityEngine.Texture2D texture { get }`  

```csharp
public UnityEngine.Texture2D texture { get; }
```

- `public System.String name { get; set }`  

```csharp
public System.String name { get; set; }
```


## Constructors

- `public AtlasFrame(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Int32 page)`  

```csharp
public AtlasFrame(System.Int32 width, System.Int32 height, System.Boolean rotations, System.Int32 page);
```

- `public AtlasFrame(UnityEngine.Texture2D texture, System.Boolean rotations, System.Int32 page, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles)`  

```csharp
public AtlasFrame(UnityEngine.Texture2D texture, System.Boolean rotations, System.Int32 page, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries, System.Collections.Generic.List<UnityEngine.Rect> usedRectangles, System.Collections.Generic.List<UnityEngine.Rect> freeRectangles);
```


## Methods

- `private CreateTexture(System.Int32 width, System.Int32 height) : UnityEngine.Texture2D`  

```csharp
private UnityEngine.Texture2D CreateTexture(System.Int32 width, System.Int32 height);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`  

```csharp
public System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry> GetEnumerator();
```

- `public Grow(System.Boolean forceUniform = False) : System.Boolean`  

```csharp
public System.Boolean Grow(System.Boolean forceUniform);
```

- `public Insert(System.String name, UnityEngine.Texture rt, UnityEngine.Rect region) : System.Void`  

```csharp
public System.Void Insert(System.String name, UnityEngine.Texture rt, UnityEngine.Rect region);
```

- `private Reserve(System.Int32 width, System.Int32 height, UnityEngine.Rect& region) : System.Boolean`  

```csharp
private System.Boolean Reserve(System.Int32 width, System.Int32 height, UnityEngine.Rect& region);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public TryAdd(System.String name, UnityEngine.Texture target) : System.Boolean`  

```csharp
public System.Boolean TryAdd(System.String name, UnityEngine.Texture target);
```


## Nested types

- `Colossal.IO.AssetDatabase.AtlasFrame+Entry`  

