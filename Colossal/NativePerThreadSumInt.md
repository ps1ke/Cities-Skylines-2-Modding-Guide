# Colossal.NativePerThreadSumInt

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`  

## Code

```csharp
public sealed struct NativePerThreadSumInt
{
    private System.Int32* m_Counter;
    private Unity.Collections.Allocator m_AllocatorLabel;
    public static const System.Int32 IntsPerCacheLine;

    public System.Int32 Count { get; set; }
    public System.Boolean IsCreated { get; }

    public NativePerThreadSumInt(Unity.Collections.Allocator label);

    public System.Void Add(System.Int32 x);
    public System.Void Dispose();
    public Colossal.NativePerThreadSumInt+Concurrent ToConcurrent();
}
```


## Fields

- `private System.Int32* m_Counter`  

```csharp
private System.Int32* m_Counter;
```

- `private Unity.Collections.Allocator m_AllocatorLabel`  

```csharp
private Unity.Collections.Allocator m_AllocatorLabel;
```

- `public static const System.Int32 IntsPerCacheLine`  

```csharp
public static const System.Int32 IntsPerCacheLine;
```


## Properties

- `public System.Int32 Count { get; set }`  

```csharp
public System.Int32 Count { get; set; }
```

- `public System.Boolean IsCreated { get }`  

```csharp
public System.Boolean IsCreated { get; }
```


## Constructors

- `public NativePerThreadSumInt(Unity.Collections.Allocator label)`  

```csharp
public NativePerThreadSumInt(Unity.Collections.Allocator label);
```


## Methods

- `public Add(System.Int32 x) : System.Void`  

```csharp
public System.Void Add(System.Int32 x);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ToConcurrent() : Colossal.NativePerThreadSumInt+Concurrent`  

```csharp
public Colossal.NativePerThreadSumInt+Concurrent ToConcurrent();
```


## Nested types

- `Colossal.NativePerThreadSumInt+Concurrent`  

