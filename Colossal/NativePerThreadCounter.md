# Colossal.NativePerThreadCounter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`  

## Code

```csharp
public sealed struct NativePerThreadCounter
{
    private System.Int32* m_Counter;
    private Unity.Collections.Allocator m_AllocatorLabel;
    public static const System.Int32 IntsPerCacheLine;

    public System.Int32 Count { get; set; }
    public System.Boolean IsCreated { get; }

    public NativePerThreadCounter(Unity.Collections.Allocator label);

    public System.Void Dispose();
    public System.Void Increment();
    public Colossal.NativePerThreadCounter+Concurrent ToConcurrent();
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

- `public NativePerThreadCounter(Unity.Collections.Allocator label)`  

```csharp
public NativePerThreadCounter(Unity.Collections.Allocator label);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Increment() : System.Void`  

```csharp
public System.Void Increment();
```

- `public ToConcurrent() : Colossal.NativePerThreadCounter+Concurrent`  

```csharp
public Colossal.NativePerThreadCounter+Concurrent ToConcurrent();
```


## Nested types

- `Colossal.NativePerThreadCounter+Concurrent`  

