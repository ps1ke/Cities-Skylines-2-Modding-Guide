# Colossal.AssetPipeline.LOD

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class LOD : System.IDisposable
{
    public Colossal.AssetPipeline.Geometry geometry;
    public Colossal.AssetPipeline.Surface[] surfaces;
    public readonly System.Int32 level;

    public System.String name { get; }

    public LOD(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Surface[] surfaces, System.Int32 level);

    public System.Void Dispose();
    public static System.String MakeName(System.String name, System.Int32 level);
    public Colossal.AssetPipeline.LOD+UnityInstance ToGameObject(System.Boolean hideAndDontSave);
}
```


## Fields

- `public Colossal.AssetPipeline.Geometry geometry`  

```csharp
public Colossal.AssetPipeline.Geometry geometry;
```

- `public Colossal.AssetPipeline.Surface[] surfaces`  

```csharp
public Colossal.AssetPipeline.Surface[] surfaces;
```

- `public readonly System.Int32 level`  

```csharp
public readonly System.Int32 level;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```


## Constructors

- `public LOD(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Surface[] surfaces, System.Int32 level)`  

```csharp
public LOD(Colossal.AssetPipeline.Geometry geometry, Colossal.AssetPipeline.Surface[] surfaces, System.Int32 level);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public static MakeName(System.String name, System.Int32 level) : System.String`  

```csharp
public static System.String MakeName(System.String name, System.Int32 level);
```

- `public ToGameObject(System.Boolean hideAndDontSave) : Colossal.AssetPipeline.LOD+UnityInstance`  

```csharp
public Colossal.AssetPipeline.LOD+UnityInstance ToGameObject(System.Boolean hideAndDontSave);
```


## Nested types

- `Colossal.AssetPipeline.LOD+UnityInstance`  

