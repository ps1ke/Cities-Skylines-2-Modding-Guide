# PDX.SDK.Network.Util.ContentTypeExtensionMethods

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Network.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ContentTypeExtensionMethods
{
    private static System.Collections.Generic.Dictionary<PDX.SDK.Network.Enums.ContentType, System.String> ContentTypeStrings;

    public static PDX.SDK.Network.Enums.ContentType GetContentTypeEnum(System.String type);
    public static System.String ToContentTypeString(PDX.SDK.Network.Enums.ContentType type);
}
```


## Fields

- `private static System.Collections.Generic.Dictionary<PDX.SDK.Network.Enums.ContentType, System.String> ContentTypeStrings`  

```csharp
private static System.Collections.Generic.Dictionary<PDX.SDK.Network.Enums.ContentType, System.String> ContentTypeStrings;
```


## Methods

- `public static GetContentTypeEnum(System.String type) : PDX.SDK.Network.Enums.ContentType`  

```csharp
public static PDX.SDK.Network.Enums.ContentType GetContentTypeEnum(System.String type);
```

- `public static ToContentTypeString(PDX.SDK.Network.Enums.ContentType type) : System.String`  

```csharp
public static System.String ToContentTypeString(PDX.SDK.Network.Enums.ContentType type);
```


