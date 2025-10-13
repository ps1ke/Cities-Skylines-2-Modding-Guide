# Colossal.OdinSerializer.Vector2DictionaryKeyPathProvider

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.BaseDictionaryKeyPathProvider<UnityEngine.Vector2>`  
**Implements:** `Colossal.OdinSerializer.IDictionaryKeyPathProvider<UnityEngine.Vector2>`, `Colossal.OdinSerializer.IDictionaryKeyPathProvider`, `System.Collections.Generic.IComparer<UnityEngine.Vector2>`  

## Code

```csharp
public sealed class Vector2DictionaryKeyPathProvider : Colossal.OdinSerializer.BaseDictionaryKeyPathProvider<UnityEngine.Vector2>, Colossal.OdinSerializer.IDictionaryKeyPathProvider<UnityEngine.Vector2>, Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.Collections.Generic.IComparer<UnityEngine.Vector2>
{
    public System.String ProviderID { get; }

    public Vector2DictionaryKeyPathProvider();

    public virtual System.Int32 Compare(UnityEngine.Vector2 x, UnityEngine.Vector2 y);
    public virtual UnityEngine.Vector2 GetKeyFromPathString(System.String pathStr);
    public virtual System.String GetPathStringFromKey(UnityEngine.Vector2 key);
}
```


## Properties

- `public System.String ProviderID { get }`  

```csharp
public System.String ProviderID { get; }
```


## Constructors

- `public Vector2DictionaryKeyPathProvider()`  

```csharp
public Vector2DictionaryKeyPathProvider();
```


## Methods

- `public virtual Compare(UnityEngine.Vector2 x, UnityEngine.Vector2 y) : System.Int32`  

```csharp
public virtual System.Int32 Compare(UnityEngine.Vector2 x, UnityEngine.Vector2 y);
```

- `public virtual GetKeyFromPathString(System.String pathStr) : UnityEngine.Vector2`  

```csharp
public virtual UnityEngine.Vector2 GetKeyFromPathString(System.String pathStr);
```

- `public virtual GetPathStringFromKey(UnityEngine.Vector2 key) : System.String`  

```csharp
public virtual System.String GetPathStringFromKey(UnityEngine.Vector2 key);
```


