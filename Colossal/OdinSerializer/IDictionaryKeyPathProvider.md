# Colossal.OdinSerializer.IDictionaryKeyPathProvider

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDictionaryKeyPathProvider
{
    public System.String ProviderID { get; }

    public abstract System.Int32 Compare(System.Object x, System.Object y);
    public abstract System.Object GetKeyFromPathString(System.String pathStr);
    public abstract System.String GetPathStringFromKey(System.Object key);
}
```


## Properties

- `public System.String ProviderID { get }`  

```csharp
public System.String ProviderID { get; }
```


## Methods

- `public abstract Compare(System.Object x, System.Object y) : System.Int32`  

```csharp
public abstract System.Int32 Compare(System.Object x, System.Object y);
```

- `public abstract GetKeyFromPathString(System.String pathStr) : System.Object`  

```csharp
public abstract System.Object GetKeyFromPathString(System.String pathStr);
```

- `public abstract GetPathStringFromKey(System.Object key) : System.String`  

```csharp
public abstract System.String GetPathStringFromKey(System.Object key);
```


