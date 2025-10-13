# Colossal.IO.AssetDatabase.AssetDatabaseRequestException

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class AssetDatabaseRequestException : System.Exception, System.Runtime.Serialization.ISerializable
{
    private readonly System.Uri <Uri>k__BackingField;

    public System.Uri Uri { get; }

    public AssetDatabaseRequestException(System.String message, System.Uri uri);
    public AssetDatabaseRequestException(System.String message, System.Uri uri, System.Exception innerException);

    public virtual System.String ToString();
}
```


## Fields

- `private readonly System.Uri <Uri>k__BackingField`  

```csharp
private readonly System.Uri <Uri>k__BackingField;
```


## Properties

- `public System.Uri Uri { get }`  

```csharp
public System.Uri Uri { get; }
```


## Constructors

- `public AssetDatabaseRequestException(System.String message, System.Uri uri)`  

```csharp
public AssetDatabaseRequestException(System.String message, System.Uri uri);
```

- `public AssetDatabaseRequestException(System.String message, System.Uri uri, System.Exception innerException)`  

```csharp
public AssetDatabaseRequestException(System.String message, System.Uri uri, System.Exception innerException);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


