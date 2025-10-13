# Colossal.Collections.AverageFloat

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Colossal.Collections.AverageFloat>`  

## Code

```csharp
public sealed struct AverageFloat : Colossal.Collections.IAccumulable<Colossal.Collections.AverageFloat>
{
    public System.Single m_Total;
    public System.Int32 m_Count;

    public System.Single average { get; }

    public System.Void Accumulate(Colossal.Collections.AverageFloat other);
}
```


## Fields

- `public System.Single m_Total`  

```csharp
public System.Single m_Total;
```

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```


## Properties

- `public System.Single average { get }`  

```csharp
public System.Single average { get; }
```


## Methods

- `public Accumulate(Colossal.Collections.AverageFloat other) : System.Void`  

```csharp
public System.Void Accumulate(Colossal.Collections.AverageFloat other);
```


