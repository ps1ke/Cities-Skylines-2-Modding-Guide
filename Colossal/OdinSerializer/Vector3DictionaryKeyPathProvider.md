# Colossal.OdinSerializer.Vector3DictionaryKeyPathProvider

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.BaseDictionaryKeyPathProvider<UnityEngine.Vector3>`  
**Implements:** `Colossal.OdinSerializer.IDictionaryKeyPathProvider<UnityEngine.Vector3>`, `Colossal.OdinSerializer.IDictionaryKeyPathProvider`, `System.Collections.Generic.IComparer<UnityEngine.Vector3>`  

## Code

```csharp
public sealed class Vector3DictionaryKeyPathProvider : Colossal.OdinSerializer.BaseDictionaryKeyPathProvider<UnityEngine.Vector3>, Colossal.OdinSerializer.IDictionaryKeyPathProvider<UnityEngine.Vector3>, Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.Collections.Generic.IComparer<UnityEngine.Vector3>
{
    public System.String ProviderID { get; }

    public Vector3DictionaryKeyPathProvider();

    public virtual System.Int32 Compare(UnityEngine.Vector3 x, UnityEngine.Vector3 y);
    public virtual UnityEngine.Vector3 GetKeyFromPathString(System.String pathStr);
    public virtual System.String GetPathStringFromKey(UnityEngine.Vector3 key);
}
```


## Properties

- `public System.String ProviderID { get }`  

```csharp
public System.String ProviderID { get; }
```


## Constructors

- `public Vector3DictionaryKeyPathProvider()`  

```csharp
public Vector3DictionaryKeyPathProvider();
```


## Methods

- `public virtual Compare(UnityEngine.Vector3 x, UnityEngine.Vector3 y) : System.Int32`  

```csharp
public virtual System.Int32 Compare(UnityEngine.Vector3 x, UnityEngine.Vector3 y);
```

- `public virtual GetKeyFromPathString(System.String pathStr) : UnityEngine.Vector3`  

```csharp
public virtual UnityEngine.Vector3 GetKeyFromPathString(System.String pathStr);
```

- `public virtual GetPathStringFromKey(UnityEngine.Vector3 key) : System.String`  

```csharp
public virtual System.String GetPathStringFromKey(UnityEngine.Vector3 key);
```


