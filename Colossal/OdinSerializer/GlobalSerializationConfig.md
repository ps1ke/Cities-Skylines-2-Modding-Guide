# Colossal.OdinSerializer.GlobalSerializationConfig

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class GlobalSerializationConfig
{
    private static readonly Colossal.OdinSerializer.GlobalSerializationConfig instance;

    public static Colossal.OdinSerializer.GlobalSerializationConfig Instance { get; }
    public Colossal.OdinSerializer.ILogger Logger { get; }
    public Colossal.OdinSerializer.DataFormat EditorSerializationFormat { get; }
    public Colossal.OdinSerializer.DataFormat BuildSerializationFormat { get; }
    public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get; }
    public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get; }
    internal static System.Boolean HasInstanceLoaded { internal get; }

    public GlobalSerializationConfig();

    internal static System.Void LoadInstanceIfAssetExists();
}
```


## Fields

- `private static readonly Colossal.OdinSerializer.GlobalSerializationConfig instance`  

```csharp
private static readonly Colossal.OdinSerializer.GlobalSerializationConfig instance;
```


## Properties

- `public static Colossal.OdinSerializer.GlobalSerializationConfig Instance { get }`  

```csharp
public static Colossal.OdinSerializer.GlobalSerializationConfig Instance { get; }
```

- `public Colossal.OdinSerializer.ILogger Logger { get }`  

```csharp
public Colossal.OdinSerializer.ILogger Logger { get; }
```

- `public Colossal.OdinSerializer.DataFormat EditorSerializationFormat { get }`  

```csharp
public Colossal.OdinSerializer.DataFormat EditorSerializationFormat { get; }
```

- `public Colossal.OdinSerializer.DataFormat BuildSerializationFormat { get }`  

```csharp
public Colossal.OdinSerializer.DataFormat BuildSerializationFormat { get; }
```

- `public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get }`  

```csharp
public Colossal.OdinSerializer.LoggingPolicy LoggingPolicy { get; }
```

- `public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get }`  

```csharp
public Colossal.OdinSerializer.ErrorHandlingPolicy ErrorHandlingPolicy { get; }
```

- `internal static System.Boolean HasInstanceLoaded { internal get }`  

```csharp
internal static System.Boolean HasInstanceLoaded { internal get; }
```


## Constructors

- `public GlobalSerializationConfig()`  

```csharp
public GlobalSerializationConfig();
```


## Methods

- `internal static LoadInstanceIfAssetExists() : System.Void`  

```csharp
internal static System.Void LoadInstanceIfAssetExists();
```


