# Colossal.AssetPipeline.LOD+UnityInstance

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UnityInstance : System.IDisposable
{
    private UnityEngine.GameObject m_Root;
    private System.Collections.Generic.List<UnityEngine.Object> m_Resources;

    public UnityEngine.GameObject root { get; }

    public UnityInstance(Colossal.AssetPipeline.LOD lod, System.Boolean hideAndDontSave);

    public System.Void Dispose();
}
```


## Fields

- `private UnityEngine.GameObject m_Root`  

```csharp
private UnityEngine.GameObject m_Root;
```

- `private System.Collections.Generic.List<UnityEngine.Object> m_Resources`  

```csharp
private System.Collections.Generic.List<UnityEngine.Object> m_Resources;
```


## Properties

- `public UnityEngine.GameObject root { get }`  

```csharp
public UnityEngine.GameObject root { get; }
```


## Constructors

- `public UnityInstance(Colossal.AssetPipeline.LOD lod, System.Boolean hideAndDontSave)`  

```csharp
public UnityInstance(Colossal.AssetPipeline.LOD lod, System.Boolean hideAndDontSave);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


