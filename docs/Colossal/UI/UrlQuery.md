# Colossal.UI.UrlQuery

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Collections.Specialized.NameValueCollection`  
**Implements:** `System.Collections.ICollection`, `System.Collections.IEnumerable`, `System.Runtime.Serialization.ISerializable`, `System.Runtime.Serialization.IDeserializationCallback`  

## Constructors

- `public UrlQuery(System.String queryStringOrUrl = null)`  

## Methods

- `public Parse(System.String query) : System.Collections.Specialized.NameValueCollection`  
- `public Read(System.String key, System.Boolean& result) : System.Boolean`  
- `public Read(System.String key, System.Int32& result) : System.Boolean`  
- `public Read(System.String key, System.UInt32& result) : System.Boolean`  
- `public Read(System.String key, System.Single& result) : System.Boolean`  
- `public Read(System.String key, System.String& result) : System.Boolean`  
- `public Read(System.String key, System.Guid& result) : System.Boolean`  
- `public Read<T>(System.String key, T& result) : System.Boolean`  
- `public ReadAsset<T>(System.String key, T& result) : System.Boolean`  
- `public SetValues(System.String key, System.Collections.Generic.IEnumerable<System.String> values) : System.Void`  
- `public virtual ToString() : System.String`  

