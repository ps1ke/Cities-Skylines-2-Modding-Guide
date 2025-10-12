# Game.Input.CompositeInstance

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Input.ICustomComposite`  

## Fields

- `private System.Boolean m_IsRebindable`  
- `private System.Boolean m_IsModifiersRebindable`  
- `private System.Boolean m_AllowModifiers`  
- `private System.Boolean m_CanBeEmpty`  
- `private System.Boolean m_DeveloperOnly`  
- `private Colossal.Platform m_Platform`  
- `private System.Boolean m_BuiltIn`  
- `private System.Boolean m_IsDummy`  
- `private System.Boolean m_IsHidden`  
- `public Game.Input.OptionGroupOverride m_OptionGroupOverride`  
- `private Game.Input.Usages m_Usages`  
- `private System.String <typeName>k__BackingField`  
- `private System.Guid <linkedGuid>k__BackingField`  
- `private readonly System.Collections.Generic.List<UnityEngine.InputSystem.Utilities.NameAndParameters> <processors>k__BackingField`  
- `private readonly System.Collections.Generic.List<UnityEngine.InputSystem.Utilities.NameAndParameters> <interactions>k__BackingField`  
- `private Game.Input.Mode <mode>k__BackingField`  

## Properties

- `public System.String typeName { get; internal set }`  
- `public System.Boolean isRebindable { get; set }`  
- `public System.Boolean isModifiersRebindable { get; set }`  
- `public System.Boolean allowModifiers { get; set }`  
- `public System.Boolean canBeEmpty { get; set }`  
- `public System.Boolean developerOnly { get; set }`  
- `public Colossal.Platform platform { get; set }`  
- `public System.Boolean builtIn { get; set }`  
- `public System.Boolean isDummy { get; set }`  
- `public System.Boolean isHidden { get; set }`  
- `public Game.Input.OptionGroupOverride optionGroupOverride { get; set }`  
- `public Game.Input.Usages usages { get; set }`  
- `public System.Guid linkedGuid { get; set }`  
- `public System.Collections.Generic.List<UnityEngine.InputSystem.Utilities.NameAndParameters> processors { get }`  
- `public System.Collections.Generic.List<UnityEngine.InputSystem.Utilities.NameAndParameters> interactions { get }`  
- `public Game.Input.Mode mode { get; set }`  
- `public Game.Input.InputManager+CompositeData compositeData { get }`  
- `public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; set }`  

## Constructors

- `public CompositeInstance(System.String typeName)`  
- `public CompositeInstance(UnityEngine.InputSystem.Utilities.NameAndParameters parameters)`  
- `public CompositeInstance(UnityEngine.InputSystem.Utilities.NameAndParameters parameters, UnityEngine.InputSystem.Utilities.NameAndParameters usages)`  

