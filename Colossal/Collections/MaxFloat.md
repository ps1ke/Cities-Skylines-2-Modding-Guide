# Colossal.Collections.MaxFloat

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Colossal.Collections.MaxFloat>`  

## Code

```csharp
public sealed struct MaxFloat : Colossal.Collections.IAccumulable<Colossal.Collections.MaxFloat>
{
    public System.Single m_Value;

    public MaxFloat(System.Single value);

    public System.Void Accumulate(Colossal.Collections.MaxFloat other);
}
```


## Fields

- `public System.Single m_Value`  

```csharp
public System.Single m_Value;
```


## Constructors

- `public MaxFloat(System.Single value)`  

```csharp
public MaxFloat(System.Single value);
```


## Methods

- `public Accumulate(Colossal.Collections.MaxFloat other) : System.Void`  

```csharp
public System.Void Accumulate(Colossal.Collections.MaxFloat other);
```


