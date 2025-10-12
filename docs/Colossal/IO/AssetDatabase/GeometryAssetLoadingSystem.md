# Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.Entities.COSystemBase`  

## Fields

- `private System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.GeometryAsset> m_ToBeLoaded`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingHeader`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingBody`  
- `private static const System.Int32 maxNumberOfHeadersLoadingSimulateously`  

## Constructors

- `public GeometryAssetLoadingSystem()`  

## Methods

- `private CheckForCompletedBodies() : System.Void`  
- `private CheckForCompletedHeaders() : System.Void`  
- `public LoadGeometryAsset(Colossal.IO.AssetDatabase.GeometryAsset asset) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private StartLoading() : System.Void`  

