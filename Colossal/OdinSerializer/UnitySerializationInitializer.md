# Colossal.OdinSerializer.UnitySerializationInitializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class UnitySerializationInitializer
{
    private static readonly System.Object LOCK;
    private static System.Boolean initialized;
    private static UnityEngine.RuntimePlatform <CurrentPlatform>k__BackingField;

    public static System.Boolean Initialized { get; }
    public static UnityEngine.RuntimePlatform CurrentPlatform { get; private set; }

    public static System.Void Initialize();
    private static System.Void InitializeRuntime();
}
```


## Fields

- `private static readonly System.Object LOCK`  

```csharp
private static readonly System.Object LOCK;
```

- `private static System.Boolean initialized`  

```csharp
private static System.Boolean initialized;
```

- `private static UnityEngine.RuntimePlatform <CurrentPlatform>k__BackingField`  

```csharp
private static UnityEngine.RuntimePlatform <CurrentPlatform>k__BackingField;
```


## Properties

- `public static System.Boolean Initialized { get }`  

```csharp
public static System.Boolean Initialized { get; }
```

- `public static UnityEngine.RuntimePlatform CurrentPlatform { get; private set }`  

```csharp
public static UnityEngine.RuntimePlatform CurrentPlatform { get; private set; }
```


## Methods

- `public static Initialize() : System.Void`  

```csharp
public static System.Void Initialize();
```

- `private static InitializeRuntime() : System.Void`  

```csharp
private static System.Void InitializeRuntime();
```


