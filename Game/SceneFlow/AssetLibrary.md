# Game.SceneFlow.AssetLibrary

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class AssetLibrary : UnityEngine.ScriptableObject
{
    public System.Collections.Generic.List<Game.Prefabs.AssetCollection> m_Collections;
    private System.Int32 m_AssetCount;
    private System.Int32 m_ProgressCount;

    public System.Single progress { get; }

    public AssetLibrary();

    private System.Int32 GetCount();
    public System.Void Load(Game.Prefabs.PrefabSystem prefabSystem, System.Threading.CancellationToken token);
}
```


## Fields

- `public System.Collections.Generic.List<Game.Prefabs.AssetCollection> m_Collections`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.AssetCollection> m_Collections;
```

- `private System.Int32 m_AssetCount`  

```csharp
private System.Int32 m_AssetCount;
```

- `private System.Int32 m_ProgressCount`  

```csharp
private System.Int32 m_ProgressCount;
```


## Properties

- `public System.Single progress { get }`  

```csharp
public System.Single progress { get; }
```


## Constructors

- `public AssetLibrary()`  

```csharp
public AssetLibrary();
```


## Methods

- `private GetCount() : System.Int32`  

```csharp
private System.Int32 GetCount();
```

- `public Load(Game.Prefabs.PrefabSystem prefabSystem, System.Threading.CancellationToken token) : System.Void`  

```csharp
public System.Void Load(Game.Prefabs.PrefabSystem prefabSystem, System.Threading.CancellationToken token);
```


## Nested types

- `Game.SceneFlow.AssetLibrary+<>c__DisplayClass5_0`  

