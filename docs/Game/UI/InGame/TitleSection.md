# Game.UI.InGame.TitleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  
- `private System.String <icon>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  
- `private System.String icon { private get; private set }`  

## Constructors

- `public TitleSection()`  

## Methods

- `public static GetVirtualKeyboardLocaleKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnRename(System.String newName) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

