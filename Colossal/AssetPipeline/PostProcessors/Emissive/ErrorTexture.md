# Colossal.AssetPipeline.PostProcessors.Emissive.ErrorTexture

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public class ErrorTexture : System.IDisposable
{
    private System.String m_Name;
    private System.Int32 m_Width;
    private System.Int32 m_height;
    private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format;
    private UnityEngine.Texture2D m_Texture;
    private UnityEngine.Color32[] m_Colors;

    public UnityEngine.Color32 Item { get; set; }
    public System.Int32 Width { get; }
    public System.Int32 Height { get; }

    public ErrorTexture(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format);

    private System.Void CreateTexture();
    public System.Void Dispose();
}
```


## Fields

- `private System.String m_Name`  

```csharp
private System.String m_Name;
```

- `private System.Int32 m_Width`  

```csharp
private System.Int32 m_Width;
```

- `private System.Int32 m_height`  

```csharp
private System.Int32 m_height;
```

- `private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format`  

```csharp
private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format;
```

- `private UnityEngine.Texture2D m_Texture`  

```csharp
private UnityEngine.Texture2D m_Texture;
```

- `private UnityEngine.Color32[] m_Colors`  

```csharp
private UnityEngine.Color32[] m_Colors;
```


## Properties

- `public UnityEngine.Color32 Item { get; set }`  

```csharp
public UnityEngine.Color32 Item { get; set; }
```

- `public System.Int32 Width { get }`  

```csharp
public System.Int32 Width { get; }
```

- `public System.Int32 Height { get }`  

```csharp
public System.Int32 Height { get; }
```


## Constructors

- `public ErrorTexture(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format)`  

```csharp
public ErrorTexture(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format);
```


## Methods

- `private CreateTexture() : System.Void`  

```csharp
private System.Void CreateTexture();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


