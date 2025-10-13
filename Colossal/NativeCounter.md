# Colossal.NativeCounter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`  

## Code

```csharp
public sealed struct NativeCounter
{
    private System.Int32* m_Counter;
    private Unity.Collections.Allocator m_AllocatorLabel;

    public System.Int32 Count { get; set; }
    public System.Boolean IsCreated { get; }

    public NativeCounter(Unity.Collections.Allocator label);

    public System.Void Dispose();
    public System.Void Increment();
    public Colossal.NativeCounter+Concurrent ToConcurrent();
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

- `public NativeCounter(Unity.Collections.Allocator label)`  

```csharp
public NativeCounter(Unity.Collections.Allocator label);
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

- `public ToConcurrent() : Colossal.NativeCounter+Concurrent`  

```csharp
public Colossal.NativeCounter+Concurrent ToConcurrent();
```


## Nested types

- `Colossal.NativeCounter+Concurrent`  

