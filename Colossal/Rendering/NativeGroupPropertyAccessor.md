# Colossal.Rendering.NativeGroupPropertyAccessor

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct NativeGroupPropertyAccessor
{
    internal Colossal.Rendering.UnsafeGroupProperty* m_PropertyPtr;
    internal System.Int32 m_PropertyCount;

    public System.Int32 PropertyCount { get; }

    public System.Int32 GetDataIndex(System.Int32 index);
    public System.Int32 GetPropertyName(System.Int32 index);
}
```


## Fields

- `internal Colossal.Rendering.UnsafeGroupProperty* m_PropertyPtr`  

```csharp
internal Colossal.Rendering.UnsafeGroupProperty* m_PropertyPtr;
```

- `internal System.Int32 m_PropertyCount`  

```csharp
internal System.Int32 m_PropertyCount;
```


## Properties

- `public System.Int32 PropertyCount { get }`  

```csharp
public System.Int32 PropertyCount { get; }
```


## Methods

- `public GetDataIndex(System.Int32 index) : System.Int32`  

```csharp
public System.Int32 GetDataIndex(System.Int32 index);
```

- `public GetPropertyName(System.Int32 index) : System.Int32`  

```csharp
public System.Int32 GetPropertyName(System.Int32 index);
```


