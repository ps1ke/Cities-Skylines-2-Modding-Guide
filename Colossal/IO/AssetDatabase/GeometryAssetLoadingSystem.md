# Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.Entities.COSystemBase`  

## Code

```csharp
public class GeometryAssetLoadingSystem : Colossal.Entities.COSystemBase
{
    private System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.GeometryAsset> m_ToBeLoaded;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingHeader;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingBody;
    private static const System.Int32 maxNumberOfHeadersLoadingSimulateously;

    public GeometryAssetLoadingSystem();

    private System.Void CheckForCompletedBodies();
    private System.Void CheckForCompletedHeaders();
    public System.Void LoadGeometryAsset(Colossal.IO.AssetDatabase.GeometryAsset asset);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void StartLoading();
}
```


## Fields

- `private System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.GeometryAsset> m_ToBeLoaded`  

```csharp
private System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.GeometryAsset> m_ToBeLoaded;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingHeader`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingHeader;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingBody`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingBody;
```

- `private static const System.Int32 maxNumberOfHeadersLoadingSimulateously`  

```csharp
private static const System.Int32 maxNumberOfHeadersLoadingSimulateously;
```


## Constructors

- `public GeometryAssetLoadingSystem()`  

```csharp
public GeometryAssetLoadingSystem();
```


## Methods

- `private CheckForCompletedBodies() : System.Void`  

```csharp
private System.Void CheckForCompletedBodies();
```

- `private CheckForCompletedHeaders() : System.Void`  

```csharp
private System.Void CheckForCompletedHeaders();
```

- `public LoadGeometryAsset(Colossal.IO.AssetDatabase.GeometryAsset asset) : System.Void`  

```csharp
public System.Void LoadGeometryAsset(Colossal.IO.AssetDatabase.GeometryAsset asset);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private StartLoading() : System.Void`  

```csharp
private System.Void StartLoading();
```


