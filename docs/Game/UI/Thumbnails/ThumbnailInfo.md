# Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.Thumbnails`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IEquatable<Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo>`  

## Code

```csharp
public class ThumbnailInfo : System.IEquatable<Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo>
{
    public System.Object baseObjectRef;
    public UnityEngine.Camera camera;
    public Colossal.IO.AssetDatabase.AtlasFrame atlasFrame;
    public UnityEngine.Rect region;
    public Game.UI.Thumbnails.ThumbnailCache+Status status;

    public ThumbnailInfo();

    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Object baseObjectRef`  

```csharp
public System.Object baseObjectRef;
```

- `public UnityEngine.Camera camera`  

```csharp
public UnityEngine.Camera camera;
```

- `public Colossal.IO.AssetDatabase.AtlasFrame atlasFrame`  

```csharp
public Colossal.IO.AssetDatabase.AtlasFrame atlasFrame;
```

- `public UnityEngine.Rect region`  

```csharp
public UnityEngine.Rect region;
```

- `public Game.UI.Thumbnails.ThumbnailCache+Status status`  

```csharp
public Game.UI.Thumbnails.ThumbnailCache+Status status;
```


## Constructors

- `public ThumbnailInfo()`  

```csharp
public ThumbnailInfo();
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Thumbnails.ThumbnailCache+ThumbnailInfo other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


