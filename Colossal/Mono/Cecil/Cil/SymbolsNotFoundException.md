# Colossal.Mono.Cecil.Cil.SymbolsNotFoundException

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.IO.FileNotFoundException`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed class SymbolsNotFoundException : System.IO.FileNotFoundException, System.Runtime.Serialization.ISerializable
{
    public SymbolsNotFoundException(System.String message);
    private SymbolsNotFoundException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context);

}
```


## Constructors

- `public SymbolsNotFoundException(System.String message)`  

```csharp
public SymbolsNotFoundException(System.String message);
```

- `private SymbolsNotFoundException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context)`  

```csharp
private SymbolsNotFoundException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context);
```


