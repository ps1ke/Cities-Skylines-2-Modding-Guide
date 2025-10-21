# Game.UI.Widgets.EnumFieldBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IFieldBuilderFactory`  

## Code

```csharp
public class EnumFieldBuilders : Game.UI.Widgets.IFieldBuilderFactory
{
    public static readonly System.Collections.Generic.Dictionary<System.Type, Game.UI.Widgets.EnumMember[]> kMemberCache;

    public EnumFieldBuilders();

    private static Game.UI.Widgets.EnumMember[] BuildMembers(System.Type memberType, System.Converter<System.Object, System.UInt64> fromObject);
    public static System.Boolean GetConverters(System.Type memberType, System.Converter`2[[System.Object, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& fromObject, System.Converter`2[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Object, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& toObject);
    public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
}
```


## Fields

- `public static readonly System.Collections.Generic.Dictionary<System.Type, Game.UI.Widgets.EnumMember[]> kMemberCache`  

```csharp
public static readonly System.Collections.Generic.Dictionary<System.Type, Game.UI.Widgets.EnumMember[]> kMemberCache;
```


## Constructors

- `public EnumFieldBuilders()`  

```csharp
public EnumFieldBuilders();
```


## Methods

- `private static BuildMembers(System.Type memberType, System.Converter<System.Object, System.UInt64> fromObject) : Game.UI.Widgets.EnumMember[]`  

```csharp
private static Game.UI.Widgets.EnumMember[] BuildMembers(System.Type memberType, System.Converter<System.Object, System.UInt64> fromObject);
```

- `public static GetConverters(System.Type memberType, System.Converter`2[[System.Object, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& fromObject, System.Converter`2[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Object, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& toObject) : System.Boolean`  

```csharp
public static System.Boolean GetConverters(System.Type memberType, System.Converter`2[[System.Object, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& fromObject, System.Converter`2[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Object, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& toObject);
```

- `public TryCreate(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
public Game.UI.Widgets.FieldBuilder TryCreate(System.Type memberType, System.Object[] attributes);
```


## Nested types

- `Game.UI.Widgets.EnumFieldBuilders+<>c`  
- `Game.UI.Widgets.EnumFieldBuilders+<>c__DisplayClass1_0`  

