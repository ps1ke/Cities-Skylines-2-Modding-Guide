# Colossal.UI.UrlQuery

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Collections.Specialized.NameValueCollection`  
**Implements:** `System.Collections.ICollection`, `System.Collections.IEnumerable`, `System.Runtime.Serialization.ISerializable`, `System.Runtime.Serialization.IDeserializationCallback`  

## Code

```csharp
public class UrlQuery : System.Collections.Specialized.NameValueCollection, System.Collections.ICollection, System.Collections.IEnumerable, System.Runtime.Serialization.ISerializable, System.Runtime.Serialization.IDeserializationCallback
{
    public UrlQuery(System.String queryStringOrUrl);

    public System.Collections.Specialized.NameValueCollection Parse(System.String query);
    public System.Boolean Read(System.String key, System.Boolean& result);
    public System.Boolean Read(System.String key, System.Int32& result);
    public System.Boolean Read(System.String key, System.UInt32& result);
    public System.Boolean Read(System.String key, System.Single& result);
    public System.Boolean Read(System.String key, System.String& result);
    public System.Boolean Read(System.String key, System.Guid& result);
    public System.Boolean Read<T>(System.String key, T& result);
    public System.Boolean ReadAsset<T>(System.String key, T& result);
    public System.Void SetValues(System.String key, System.Collections.Generic.IEnumerable<System.String> values);
    public virtual System.String ToString();
}
```


## Constructors

- `public UrlQuery(System.String queryStringOrUrl = null)`  

```csharp
public UrlQuery(System.String queryStringOrUrl);
```


## Methods

- `public Parse(System.String query) : System.Collections.Specialized.NameValueCollection`  

```csharp
public System.Collections.Specialized.NameValueCollection Parse(System.String query);
```

- `public Read(System.String key, System.Boolean& result) : System.Boolean`  

```csharp
public System.Boolean Read(System.String key, System.Boolean& result);
```

- `public Read(System.String key, System.Int32& result) : System.Boolean`  

```csharp
public System.Boolean Read(System.String key, System.Int32& result);
```

- `public Read(System.String key, System.UInt32& result) : System.Boolean`  

```csharp
public System.Boolean Read(System.String key, System.UInt32& result);
```

- `public Read(System.String key, System.Single& result) : System.Boolean`  

```csharp
public System.Boolean Read(System.String key, System.Single& result);
```

- `public Read(System.String key, System.String& result) : System.Boolean`  

```csharp
public System.Boolean Read(System.String key, System.String& result);
```

- `public Read(System.String key, System.Guid& result) : System.Boolean`  

```csharp
public System.Boolean Read(System.String key, System.Guid& result);
```

- `public Read<T>(System.String key, T& result) : System.Boolean`  

```csharp
public System.Boolean Read<T>(System.String key, T& result);
```

- `public ReadAsset<T>(System.String key, T& result) : System.Boolean`  

```csharp
public System.Boolean ReadAsset<T>(System.String key, T& result);
```

- `public SetValues(System.String key, System.Collections.Generic.IEnumerable<System.String> values) : System.Void`  

```csharp
public System.Void SetValues(System.String key, System.Collections.Generic.IEnumerable<System.String> values);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


