# Colossal.Mono.Cecil.Cil.ExceptionHandler

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ExceptionHandler
{
    private Colossal.Mono.Cecil.Cil.Instruction try_start;
    private Colossal.Mono.Cecil.Cil.Instruction try_end;
    private Colossal.Mono.Cecil.Cil.Instruction filter_start;
    private Colossal.Mono.Cecil.Cil.Instruction handler_start;
    private Colossal.Mono.Cecil.Cil.Instruction handler_end;
    private Colossal.Mono.Cecil.TypeReference catch_type;
    private Colossal.Mono.Cecil.Cil.ExceptionHandlerType handler_type;

    public Colossal.Mono.Cecil.Cil.Instruction TryStart { get; set; }
    public Colossal.Mono.Cecil.Cil.Instruction TryEnd { get; set; }
    public Colossal.Mono.Cecil.Cil.Instruction FilterStart { get; set; }
    public Colossal.Mono.Cecil.Cil.Instruction HandlerStart { get; set; }
    public Colossal.Mono.Cecil.Cil.Instruction HandlerEnd { get; set; }
    public Colossal.Mono.Cecil.TypeReference CatchType { get; set; }
    public Colossal.Mono.Cecil.Cil.ExceptionHandlerType HandlerType { get; set; }

    public ExceptionHandler(Colossal.Mono.Cecil.Cil.ExceptionHandlerType handlerType);

}
```


## Fields

- `private Colossal.Mono.Cecil.Cil.Instruction try_start`  

```csharp
private Colossal.Mono.Cecil.Cil.Instruction try_start;
```

- `private Colossal.Mono.Cecil.Cil.Instruction try_end`  

```csharp
private Colossal.Mono.Cecil.Cil.Instruction try_end;
```

- `private Colossal.Mono.Cecil.Cil.Instruction filter_start`  

```csharp
private Colossal.Mono.Cecil.Cil.Instruction filter_start;
```

- `private Colossal.Mono.Cecil.Cil.Instruction handler_start`  

```csharp
private Colossal.Mono.Cecil.Cil.Instruction handler_start;
```

- `private Colossal.Mono.Cecil.Cil.Instruction handler_end`  

```csharp
private Colossal.Mono.Cecil.Cil.Instruction handler_end;
```

- `private Colossal.Mono.Cecil.TypeReference catch_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference catch_type;
```

- `private Colossal.Mono.Cecil.Cil.ExceptionHandlerType handler_type`  

```csharp
private Colossal.Mono.Cecil.Cil.ExceptionHandlerType handler_type;
```


## Properties

- `public Colossal.Mono.Cecil.Cil.Instruction TryStart { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction TryStart { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.Instruction TryEnd { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction TryEnd { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.Instruction FilterStart { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction FilterStart { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.Instruction HandlerStart { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction HandlerStart { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.Instruction HandlerEnd { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction HandlerEnd { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference CatchType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference CatchType { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.ExceptionHandlerType HandlerType { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ExceptionHandlerType HandlerType { get; set; }
```


## Constructors

- `public ExceptionHandler(Colossal.Mono.Cecil.Cil.ExceptionHandlerType handlerType)`  

```csharp
public ExceptionHandler(Colossal.Mono.Cecil.Cil.ExceptionHandlerType handlerType);
```


