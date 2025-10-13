# Colossal.Mono.Cecil.Cil.Code

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** enum sealed public  

**Base:** `System.Enum`  
**Implements:** `System.IComparable`, `System.ISpanFormattable`, `System.IFormattable`, `System.IConvertible`  

## Code

```csharp
public sealed enum Code : System.IComparable, System.ISpanFormattable, System.IFormattable, System.IConvertible
{
    public System.Int32 value__;
    public static const Colossal.Mono.Cecil.Cil.Code Nop;
    public static const Colossal.Mono.Cecil.Cil.Code Break;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarg_0;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarg_1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarg_2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarg_3;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloc_0;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloc_1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloc_2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloc_3;
    public static const Colossal.Mono.Cecil.Cil.Code Stloc_0;
    public static const Colossal.Mono.Cecil.Cil.Code Stloc_1;
    public static const Colossal.Mono.Cecil.Cil.Code Stloc_2;
    public static const Colossal.Mono.Cecil.Cil.Code Stloc_3;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarg_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarga_S;
    public static const Colossal.Mono.Cecil.Cil.Code Starg_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloc_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloca_S;
    public static const Colossal.Mono.Cecil.Cil.Code Stloc_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ldnull;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_M1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_0;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_3;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_5;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_6;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_7;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_8;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_R4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldc_R8;
    public static const Colossal.Mono.Cecil.Cil.Code Dup;
    public static const Colossal.Mono.Cecil.Cil.Code Pop;
    public static const Colossal.Mono.Cecil.Cil.Code Jmp;
    public static const Colossal.Mono.Cecil.Cil.Code Call;
    public static const Colossal.Mono.Cecil.Cil.Code Calli;
    public static const Colossal.Mono.Cecil.Cil.Code Ret;
    public static const Colossal.Mono.Cecil.Cil.Code Br_S;
    public static const Colossal.Mono.Cecil.Cil.Code Brfalse_S;
    public static const Colossal.Mono.Cecil.Cil.Code Brtrue_S;
    public static const Colossal.Mono.Cecil.Cil.Code Beq_S;
    public static const Colossal.Mono.Cecil.Cil.Code Bge_S;
    public static const Colossal.Mono.Cecil.Cil.Code Bgt_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ble_S;
    public static const Colossal.Mono.Cecil.Cil.Code Blt_S;
    public static const Colossal.Mono.Cecil.Cil.Code Bne_Un_S;
    public static const Colossal.Mono.Cecil.Cil.Code Bge_Un_S;
    public static const Colossal.Mono.Cecil.Cil.Code Bgt_Un_S;
    public static const Colossal.Mono.Cecil.Cil.Code Ble_Un_S;
    public static const Colossal.Mono.Cecil.Cil.Code Blt_Un_S;
    public static const Colossal.Mono.Cecil.Cil.Code Br;
    public static const Colossal.Mono.Cecil.Cil.Code Brfalse;
    public static const Colossal.Mono.Cecil.Cil.Code Brtrue;
    public static const Colossal.Mono.Cecil.Cil.Code Beq;
    public static const Colossal.Mono.Cecil.Cil.Code Bge;
    public static const Colossal.Mono.Cecil.Cil.Code Bgt;
    public static const Colossal.Mono.Cecil.Cil.Code Ble;
    public static const Colossal.Mono.Cecil.Cil.Code Blt;
    public static const Colossal.Mono.Cecil.Cil.Code Bne_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Bge_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Bgt_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Ble_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Blt_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Switch;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_I1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_U1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_I2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_U2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_U4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_I;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_R4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_R8;
    public static const Colossal.Mono.Cecil.Cil.Code Ldind_Ref;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_Ref;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_I1;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_I2;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_R4;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_R8;
    public static const Colossal.Mono.Cecil.Cil.Code Add;
    public static const Colossal.Mono.Cecil.Cil.Code Sub;
    public static const Colossal.Mono.Cecil.Cil.Code Mul;
    public static const Colossal.Mono.Cecil.Cil.Code Div;
    public static const Colossal.Mono.Cecil.Cil.Code Div_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Rem;
    public static const Colossal.Mono.Cecil.Cil.Code Rem_Un;
    public static const Colossal.Mono.Cecil.Cil.Code And;
    public static const Colossal.Mono.Cecil.Cil.Code Or;
    public static const Colossal.Mono.Cecil.Cil.Code Xor;
    public static const Colossal.Mono.Cecil.Cil.Code Shl;
    public static const Colossal.Mono.Cecil.Cil.Code Shr;
    public static const Colossal.Mono.Cecil.Cil.Code Shr_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Neg;
    public static const Colossal.Mono.Cecil.Cil.Code Not;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_I1;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_I2;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_R4;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_R8;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_U4;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_U8;
    public static const Colossal.Mono.Cecil.Cil.Code Callvirt;
    public static const Colossal.Mono.Cecil.Cil.Code Cpobj;
    public static const Colossal.Mono.Cecil.Cil.Code Ldobj;
    public static const Colossal.Mono.Cecil.Cil.Code Ldstr;
    public static const Colossal.Mono.Cecil.Cil.Code Newobj;
    public static const Colossal.Mono.Cecil.Cil.Code Castclass;
    public static const Colossal.Mono.Cecil.Cil.Code Isinst;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_R_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Unbox;
    public static const Colossal.Mono.Cecil.Cil.Code Throw;
    public static const Colossal.Mono.Cecil.Cil.Code Ldfld;
    public static const Colossal.Mono.Cecil.Cil.Code Ldflda;
    public static const Colossal.Mono.Cecil.Cil.Code Stfld;
    public static const Colossal.Mono.Cecil.Cil.Code Ldsfld;
    public static const Colossal.Mono.Cecil.Cil.Code Ldsflda;
    public static const Colossal.Mono.Cecil.Cil.Code Stsfld;
    public static const Colossal.Mono.Cecil.Cil.Code Stobj;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I1_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I2_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I4_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I8_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U1_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U2_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U4_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U8_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Box;
    public static const Colossal.Mono.Cecil.Cil.Code Newarr;
    public static const Colossal.Mono.Cecil.Cil.Code Ldlen;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelema;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U1;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U2;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_R4;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_R8;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_Ref;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_I;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_I1;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_I2;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_R4;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_R8;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_Ref;
    public static const Colossal.Mono.Cecil.Cil.Code Ldelem_Any;
    public static const Colossal.Mono.Cecil.Cil.Code Stelem_Any;
    public static const Colossal.Mono.Cecil.Cil.Code Unbox_Any;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I1;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U1;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I2;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U2;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I4;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U4;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I8;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U8;
    public static const Colossal.Mono.Cecil.Cil.Code Refanyval;
    public static const Colossal.Mono.Cecil.Cil.Code Ckfinite;
    public static const Colossal.Mono.Cecil.Cil.Code Mkrefany;
    public static const Colossal.Mono.Cecil.Cil.Code Ldtoken;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_U2;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_U1;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_I;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U;
    public static const Colossal.Mono.Cecil.Cil.Code Add_Ovf;
    public static const Colossal.Mono.Cecil.Cil.Code Add_Ovf_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Mul_Ovf;
    public static const Colossal.Mono.Cecil.Cil.Code Mul_Ovf_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Sub_Ovf;
    public static const Colossal.Mono.Cecil.Cil.Code Sub_Ovf_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Endfinally;
    public static const Colossal.Mono.Cecil.Cil.Code Leave;
    public static const Colossal.Mono.Cecil.Cil.Code Leave_S;
    public static const Colossal.Mono.Cecil.Cil.Code Stind_I;
    public static const Colossal.Mono.Cecil.Cil.Code Conv_U;
    public static const Colossal.Mono.Cecil.Cil.Code Arglist;
    public static const Colossal.Mono.Cecil.Cil.Code Ceq;
    public static const Colossal.Mono.Cecil.Cil.Code Cgt;
    public static const Colossal.Mono.Cecil.Cil.Code Cgt_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Clt;
    public static const Colossal.Mono.Cecil.Cil.Code Clt_Un;
    public static const Colossal.Mono.Cecil.Cil.Code Ldftn;
    public static const Colossal.Mono.Cecil.Cil.Code Ldvirtftn;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarg;
    public static const Colossal.Mono.Cecil.Cil.Code Ldarga;
    public static const Colossal.Mono.Cecil.Cil.Code Starg;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloc;
    public static const Colossal.Mono.Cecil.Cil.Code Ldloca;
    public static const Colossal.Mono.Cecil.Cil.Code Stloc;
    public static const Colossal.Mono.Cecil.Cil.Code Localloc;
    public static const Colossal.Mono.Cecil.Cil.Code Endfilter;
    public static const Colossal.Mono.Cecil.Cil.Code Unaligned;
    public static const Colossal.Mono.Cecil.Cil.Code Volatile;
    public static const Colossal.Mono.Cecil.Cil.Code Tail;
    public static const Colossal.Mono.Cecil.Cil.Code Initobj;
    public static const Colossal.Mono.Cecil.Cil.Code Constrained;
    public static const Colossal.Mono.Cecil.Cil.Code Cpblk;
    public static const Colossal.Mono.Cecil.Cil.Code Initblk;
    public static const Colossal.Mono.Cecil.Cil.Code No;
    public static const Colossal.Mono.Cecil.Cil.Code Rethrow;
    public static const Colossal.Mono.Cecil.Cil.Code Sizeof;
    public static const Colossal.Mono.Cecil.Cil.Code Refanytype;
    public static const Colossal.Mono.Cecil.Cil.Code Readonly;

}
```


## Fields

- `public System.Int32 value__`  

```csharp
public System.Int32 value__;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Nop`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Nop;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Break`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Break;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarg_0`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarg_0;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarg_1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarg_1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarg_2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarg_2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarg_3`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarg_3;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloc_0`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloc_0;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloc_1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloc_1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloc_2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloc_2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloc_3`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloc_3;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stloc_0`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stloc_0;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stloc_1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stloc_1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stloc_2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stloc_2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stloc_3`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stloc_3;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarg_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarg_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarga_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarga_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Starg_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Starg_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloc_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloc_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloca_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloca_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stloc_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stloc_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldnull`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldnull;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_M1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_M1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_0`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_0;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_3`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_3;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_5`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_5;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_6`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_6;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_7`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_7;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_R4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_R4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldc_R8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldc_R8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Dup`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Dup;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Pop`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Pop;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Jmp`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Jmp;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Call`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Call;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Calli`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Calli;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ret`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ret;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Br_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Br_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Brfalse_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Brfalse_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Brtrue_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Brtrue_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Beq_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Beq_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bge_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bge_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bgt_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bgt_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ble_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ble_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Blt_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Blt_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bne_Un_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bne_Un_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bge_Un_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bge_Un_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bgt_Un_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bgt_Un_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ble_Un_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ble_Un_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Blt_Un_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Blt_Un_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Br`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Br;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Brfalse`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Brfalse;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Brtrue`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Brtrue;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Beq`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Beq;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bge`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bge;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bgt`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bgt;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ble`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ble;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Blt`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Blt;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bne_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bne_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bge_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bge_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Bgt_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Bgt_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ble_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ble_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Blt_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Blt_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Switch`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Switch;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_I1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_I1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_U1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_U1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_I2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_I2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_U2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_U2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_U4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_U4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_I`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_I;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_R4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_R4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_R8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_R8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldind_Ref`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldind_Ref;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_Ref`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_Ref;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_I1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_I1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_I2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_I2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_R4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_R4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_R8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_R8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Add`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Add;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Sub`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Sub;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Mul`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Mul;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Div`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Div;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Div_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Div_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Rem`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Rem;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Rem_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Rem_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code And`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code And;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Or`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Or;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Xor`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Xor;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Shl`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Shl;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Shr`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Shr;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Shr_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Shr_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Neg`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Neg;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Not`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Not;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_I1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_I1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_I2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_I2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_R4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_R4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_R8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_R8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_U4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_U4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_U8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_U8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Callvirt`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Callvirt;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Cpobj`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Cpobj;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldobj`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldobj;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldstr`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldstr;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Newobj`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Newobj;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Castclass`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Castclass;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Isinst`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Isinst;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_R_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_R_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Unbox`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Unbox;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Throw`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Throw;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldfld`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldfld;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldflda`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldflda;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stfld`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stfld;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldsfld`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldsfld;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldsflda`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldsflda;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stsfld`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stsfld;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stobj`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stobj;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I1_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I1_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I2_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I2_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I4_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I4_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I8_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I8_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U1_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U1_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U2_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U2_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U4_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U4_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U8_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U8_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Box`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Box;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Newarr`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Newarr;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldlen`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldlen;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelema`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelema;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_U4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_I;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_R4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_R4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_R8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_R8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_Ref`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_Ref;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_I`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_I;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_I1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_I1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_I2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_I2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_R4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_R4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_R8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_R8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_Ref`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_Ref;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldelem_Any`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldelem_Any;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stelem_Any`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stelem_Any;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Unbox_Any`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Unbox_Any;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U4`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U4;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U8`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U8;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Refanyval`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Refanyval;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ckfinite`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ckfinite;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Mkrefany`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Mkrefany;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldtoken`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldtoken;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_U2`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_U2;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_U1`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_U1;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_I`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_I;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_I;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_Ovf_U;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Add_Ovf`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Add_Ovf;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Add_Ovf_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Add_Ovf_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Mul_Ovf`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Mul_Ovf;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Mul_Ovf_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Mul_Ovf_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Sub_Ovf`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Sub_Ovf;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Sub_Ovf_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Sub_Ovf_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Endfinally`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Endfinally;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Leave`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Leave;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Leave_S`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Leave_S;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stind_I`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stind_I;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Conv_U`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Conv_U;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Arglist`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Arglist;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ceq`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ceq;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Cgt`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Cgt;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Cgt_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Cgt_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Clt`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Clt;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Clt_Un`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Clt_Un;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldftn`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldftn;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldvirtftn`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldvirtftn;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarg`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarg;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldarga`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldarga;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Starg`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Starg;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloc`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloc;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Ldloca`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Ldloca;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Stloc`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Stloc;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Localloc`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Localloc;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Endfilter`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Endfilter;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Unaligned`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Unaligned;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Volatile`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Volatile;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Tail`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Tail;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Initobj`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Initobj;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Constrained`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Constrained;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Cpblk`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Cpblk;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Initblk`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Initblk;
```

- `public static const Colossal.Mono.Cecil.Cil.Code No`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code No;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Rethrow`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Rethrow;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Sizeof`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Sizeof;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Refanytype`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Refanytype;
```

- `public static const Colossal.Mono.Cecil.Cil.Code Readonly`  

```csharp
public static const Colossal.Mono.Cecil.Cil.Code Readonly;
```


