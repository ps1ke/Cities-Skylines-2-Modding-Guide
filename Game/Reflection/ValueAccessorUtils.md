# Game.Reflection.ValueAccessorUtils

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValueAccessorUtils
{
    public static Game.Reflection.IValueAccessor CreateMemberAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member);
    public static Game.Reflection.IValueAccessor CreateNativeArrayItemAccessor(Game.Reflection.IValueAccessor accessor, System.Int32 index);
}
```


## Methods

- `public static CreateMemberAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member) : Game.Reflection.IValueAccessor`  

```csharp
public static Game.Reflection.IValueAccessor CreateMemberAccessor(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member);
```

- `public static CreateNativeArrayItemAccessor(Game.Reflection.IValueAccessor accessor, System.Int32 index) : Game.Reflection.IValueAccessor`  

```csharp
public static Game.Reflection.IValueAccessor CreateNativeArrayItemAccessor(Game.Reflection.IValueAccessor accessor, System.Int32 index);
```


