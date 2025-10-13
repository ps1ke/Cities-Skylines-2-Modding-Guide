# Colossal.IO.AssetDatabase.AssetDataPath

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AssetDataPath
{
    private readonly System.String m_SubPath;
    private readonly System.String m_AssetName;
    private readonly System.String m_Extension;
    private readonly Colossal.IO.AssetDatabase.EscapeStrategy m_EscapeStrategy;

    public System.String subPath { get; }
    public System.String assetName { get; }
    public System.String extension { get; }

    private AssetDataPath(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);

    public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
    public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
    public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String subPath, System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
    public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
    public System.String ToFilename(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy);
    public System.String ToPath(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy);
    public virtual System.String ToString();
}
```


## Fields

- `private readonly System.String m_SubPath`  

```csharp
private readonly System.String m_SubPath;
```

- `private readonly System.String m_AssetName`  

```csharp
private readonly System.String m_AssetName;
```

- `private readonly System.String m_Extension`  

```csharp
private readonly System.String m_Extension;
```

- `private readonly Colossal.IO.AssetDatabase.EscapeStrategy m_EscapeStrategy`  

```csharp
private readonly Colossal.IO.AssetDatabase.EscapeStrategy m_EscapeStrategy;
```


## Properties

- `public System.String subPath { get }`  

```csharp
public System.String subPath { get; }
```

- `public System.String assetName { get }`  

```csharp
public System.String assetName { get; }
```

- `public System.String extension { get }`  

```csharp
public System.String extension { get; }
```


## Constructors

- `private AssetDataPath(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy)`  

```csharp
private AssetDataPath(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
```


## Methods

- `public static Create(System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  

```csharp
public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
```

- `public static Create(System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  

```csharp
public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
```

- `public static Create(System.String subPath, System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  

```csharp
public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String subPath, System.String assetName, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
```

- `public static Create(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy = Filename) : Colossal.IO.AssetDatabase.AssetDataPath`  

```csharp
public static Colossal.IO.AssetDatabase.AssetDataPath Create(System.String subPath, System.String assetName, System.Boolean hasExtension, Colossal.IO.AssetDatabase.EscapeStrategy escapeStrategy);
```

- `public ToFilename(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy) : System.String`  

```csharp
public System.String ToFilename(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy);
```

- `public ToPath(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy) : System.String`  

```csharp
public System.String ToPath(Colossal.IO.AssetDatabase.IPathEscapePolicy escapePolicy);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


