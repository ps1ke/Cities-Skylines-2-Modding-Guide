# Colossal.OdinSerializer.Vector4DictionaryKeyPathProvider

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.BaseDictionaryKeyPathProvider<UnityEngine.Vector4>`  
**Implements:** `Colossal.OdinSerializer.IDictionaryKeyPathProvider<UnityEngine.Vector4>`, `Colossal.OdinSerializer.IDictionaryKeyPathProvider`, `System.Collections.Generic.IComparer<UnityEngine.Vector4>`  

## Code

```csharp
public sealed class Vector4DictionaryKeyPathProvider : Colossal.OdinSerializer.BaseDictionaryKeyPathProvider<UnityEngine.Vector4>, Colossal.OdinSerializer.IDictionaryKeyPathProvider<UnityEngine.Vector4>, Colossal.OdinSerializer.IDictionaryKeyPathProvider, System.Collections.Generic.IComparer<UnityEngine.Vector4>
{
    public System.String ProviderID { get; }

    public Vector4DictionaryKeyPathProvider();

    public virtual System.Int32 Compare(UnityEngine.Vector4 x, UnityEngine.Vector4 y);
    public virtual UnityEngine.Vector4 GetKeyFromPathString(System.String pathStr);
    public virtual System.String GetPathStringFromKey(UnityEngine.Vector4 key);
}
```


## Properties

- `public System.String ProviderID { get }`  

```csharp
public System.String ProviderID { get; }
```


## Constructors

- `public Vector4DictionaryKeyPathProvider()`  

```csharp
public Vector4DictionaryKeyPathProvider();
```


## Methods

- `public virtual Compare(UnityEngine.Vector4 x, UnityEngine.Vector4 y) : System.Int32`  

```csharp
public virtual System.Int32 Compare(UnityEngine.Vector4 x, UnityEngine.Vector4 y);
```

- `public virtual GetKeyFromPathString(System.String pathStr) : UnityEngine.Vector4`  

```csharp
public virtual UnityEngine.Vector4 GetKeyFromPathString(System.String pathStr);
```

- `public virtual GetPathStringFromKey(UnityEngine.Vector4 key) : System.String`  

```csharp
public virtual System.String GetPathStringFromKey(UnityEngine.Vector4 key);
```


