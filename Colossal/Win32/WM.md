# Colossal.Win32.WM

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** enum sealed public  

**Base:** `System.Enum`  
**Implements:** `System.IComparable`, `System.ISpanFormattable`, `System.IFormattable`, `System.IConvertible`  

## Code

```csharp
public sealed enum WM : System.IComparable, System.ISpanFormattable, System.IFormattable, System.IConvertible
{
    public System.UInt32 value__;
    public static const Colossal.Win32.WM NULL;
    public static const Colossal.Win32.WM CREATE;
    public static const Colossal.Win32.WM DESTROY;
    public static const Colossal.Win32.WM MOVE;
    public static const Colossal.Win32.WM SIZE;
    public static const Colossal.Win32.WM ACTIVATE;
    public static const Colossal.Win32.WM SETFOCUS;
    public static const Colossal.Win32.WM KILLFOCUS;
    public static const Colossal.Win32.WM ENABLE;
    public static const Colossal.Win32.WM SETREDRAW;
    public static const Colossal.Win32.WM SETTEXT;
    public static const Colossal.Win32.WM GETTEXT;
    public static const Colossal.Win32.WM GETTEXTLENGTH;
    public static const Colossal.Win32.WM PAINT;
    public static const Colossal.Win32.WM CLOSE;
    public static const Colossal.Win32.WM QUERYENDSESSION;
    public static const Colossal.Win32.WM QUERYOPEN;
    public static const Colossal.Win32.WM ENDSESSION;
    public static const Colossal.Win32.WM QUIT;
    public static const Colossal.Win32.WM ERASEBKGND;
    public static const Colossal.Win32.WM SYSCOLORCHANGE;
    public static const Colossal.Win32.WM SHOWWINDOW;
    public static const Colossal.Win32.WM WININICHANGE;
    public static const Colossal.Win32.WM SETTINGCHANGE;
    public static const Colossal.Win32.WM DEVMODECHANGE;
    public static const Colossal.Win32.WM ACTIVATEAPP;
    public static const Colossal.Win32.WM FONTCHANGE;
    public static const Colossal.Win32.WM TIMECHANGE;
    public static const Colossal.Win32.WM CANCELMODE;
    public static const Colossal.Win32.WM SETCURSOR;
    public static const Colossal.Win32.WM MOUSEACTIVATE;
    public static const Colossal.Win32.WM CHILDACTIVATE;
    public static const Colossal.Win32.WM QUEUESYNC;
    public static const Colossal.Win32.WM GETMINMAXINFO;
    public static const Colossal.Win32.WM PAINTICON;
    public static const Colossal.Win32.WM ICONERASEBKGND;
    public static const Colossal.Win32.WM NEXTDLGCTL;
    public static const Colossal.Win32.WM SPOOLERSTATUS;
    public static const Colossal.Win32.WM DRAWITEM;
    public static const Colossal.Win32.WM MEASUREITEM;
    public static const Colossal.Win32.WM DELETEITEM;
    public static const Colossal.Win32.WM VKEYTOITEM;
    public static const Colossal.Win32.WM CHARTOITEM;
    public static const Colossal.Win32.WM SETFONT;
    public static const Colossal.Win32.WM GETFONT;
    public static const Colossal.Win32.WM SETHOTKEY;
    public static const Colossal.Win32.WM GETHOTKEY;
    public static const Colossal.Win32.WM QUERYDRAGICON;
    public static const Colossal.Win32.WM COMPAREITEM;
    public static const Colossal.Win32.WM GETOBJECT;
    public static const Colossal.Win32.WM COMPACTING;
    public static const Colossal.Win32.WM COMMNOTIFY;
    public static const Colossal.Win32.WM WINDOWPOSCHANGING;
    public static const Colossal.Win32.WM WINDOWPOSCHANGED;
    public static const Colossal.Win32.WM POWER;
    public static const Colossal.Win32.WM COPYDATA;
    public static const Colossal.Win32.WM CANCELJOURNAL;
    public static const Colossal.Win32.WM NOTIFY;
    public static const Colossal.Win32.WM INPUTLANGCHANGEREQUEST;
    public static const Colossal.Win32.WM INPUTLANGCHANGE;
    public static const Colossal.Win32.WM TCARD;
    public static const Colossal.Win32.WM HELP;
    public static const Colossal.Win32.WM USERCHANGED;
    public static const Colossal.Win32.WM NOTIFYFORMAT;
    public static const Colossal.Win32.WM CONTEXTMENU;
    public static const Colossal.Win32.WM STYLECHANGING;
    public static const Colossal.Win32.WM STYLECHANGED;
    public static const Colossal.Win32.WM DISPLAYCHANGE;
    public static const Colossal.Win32.WM GETICON;
    public static const Colossal.Win32.WM SETICON;
    public static const Colossal.Win32.WM NCCREATE;
    public static const Colossal.Win32.WM NCDESTROY;
    public static const Colossal.Win32.WM NCCALCSIZE;
    public static const Colossal.Win32.WM NCHITTEST;
    public static const Colossal.Win32.WM NCPAINT;
    public static const Colossal.Win32.WM NCACTIVATE;
    public static const Colossal.Win32.WM GETDLGCODE;
    public static const Colossal.Win32.WM SYNCPAINT;
    public static const Colossal.Win32.WM NCMOUSEMOVE;
    public static const Colossal.Win32.WM NCLBUTTONDOWN;
    public static const Colossal.Win32.WM NCLBUTTONUP;
    public static const Colossal.Win32.WM NCLBUTTONDBLCLK;
    public static const Colossal.Win32.WM NCRBUTTONDOWN;
    public static const Colossal.Win32.WM NCRBUTTONUP;
    public static const Colossal.Win32.WM NCRBUTTONDBLCLK;
    public static const Colossal.Win32.WM NCMBUTTONDOWN;
    public static const Colossal.Win32.WM NCMBUTTONUP;
    public static const Colossal.Win32.WM NCMBUTTONDBLCLK;
    public static const Colossal.Win32.WM NCXBUTTONDOWN;
    public static const Colossal.Win32.WM NCXBUTTONUP;
    public static const Colossal.Win32.WM NCXBUTTONDBLCLK;
    public static const Colossal.Win32.WM INPUT_DEVICE_CHANGE;
    public static const Colossal.Win32.WM INPUT;
    public static const Colossal.Win32.WM KEYFIRST;
    public static const Colossal.Win32.WM KEYDOWN;
    public static const Colossal.Win32.WM KEYUP;
    public static const Colossal.Win32.WM CHAR;
    public static const Colossal.Win32.WM DEADCHAR;
    public static const Colossal.Win32.WM SYSKEYDOWN;
    public static const Colossal.Win32.WM SYSKEYUP;
    public static const Colossal.Win32.WM SYSCHAR;
    public static const Colossal.Win32.WM SYSDEADCHAR;
    public static const Colossal.Win32.WM UNICHAR;
    public static const Colossal.Win32.WM KEYLAST;
    public static const Colossal.Win32.WM IME_STARTCOMPOSITION;
    public static const Colossal.Win32.WM IME_ENDCOMPOSITION;
    public static const Colossal.Win32.WM IME_COMPOSITION;
    public static const Colossal.Win32.WM IME_KEYLAST;
    public static const Colossal.Win32.WM INITDIALOG;
    public static const Colossal.Win32.WM COMMAND;
    public static const Colossal.Win32.WM SYSCOMMAND;
    public static const Colossal.Win32.WM TIMER;
    public static const Colossal.Win32.WM HSCROLL;
    public static const Colossal.Win32.WM VSCROLL;
    public static const Colossal.Win32.WM INITMENU;
    public static const Colossal.Win32.WM INITMENUPOPUP;
    public static const Colossal.Win32.WM MENUSELECT;
    public static const Colossal.Win32.WM MENUCHAR;
    public static const Colossal.Win32.WM ENTERIDLE;
    public static const Colossal.Win32.WM MENURBUTTONUP;
    public static const Colossal.Win32.WM MENUDRAG;
    public static const Colossal.Win32.WM MENUGETOBJECT;
    public static const Colossal.Win32.WM UNINITMENUPOPUP;
    public static const Colossal.Win32.WM MENUCOMMAND;
    public static const Colossal.Win32.WM CHANGEUISTATE;
    public static const Colossal.Win32.WM UPDATEUISTATE;
    public static const Colossal.Win32.WM QUERYUISTATE;
    public static const Colossal.Win32.WM CTLCOLORMSGBOX;
    public static const Colossal.Win32.WM CTLCOLOREDIT;
    public static const Colossal.Win32.WM CTLCOLORLISTBOX;
    public static const Colossal.Win32.WM CTLCOLORBTN;
    public static const Colossal.Win32.WM CTLCOLORDLG;
    public static const Colossal.Win32.WM CTLCOLORSCROLLBAR;
    public static const Colossal.Win32.WM CTLCOLORSTATIC;
    public static const Colossal.Win32.WM MOUSEFIRST;
    public static const Colossal.Win32.WM MOUSEMOVE;
    public static const Colossal.Win32.WM LBUTTONDOWN;
    public static const Colossal.Win32.WM LBUTTONUP;
    public static const Colossal.Win32.WM LBUTTONDBLCLK;
    public static const Colossal.Win32.WM RBUTTONDOWN;
    public static const Colossal.Win32.WM RBUTTONUP;
    public static const Colossal.Win32.WM RBUTTONDBLCLK;
    public static const Colossal.Win32.WM MBUTTONDOWN;
    public static const Colossal.Win32.WM MBUTTONUP;
    public static const Colossal.Win32.WM MBUTTONDBLCLK;
    public static const Colossal.Win32.WM MOUSEWHEEL;
    public static const Colossal.Win32.WM XBUTTONDOWN;
    public static const Colossal.Win32.WM XBUTTONUP;
    public static const Colossal.Win32.WM XBUTTONDBLCLK;
    public static const Colossal.Win32.WM MOUSEHWHEEL;
    public static const Colossal.Win32.WM MOUSELAST;
    public static const Colossal.Win32.WM PARENTNOTIFY;
    public static const Colossal.Win32.WM ENTERMENULOOP;
    public static const Colossal.Win32.WM EXITMENULOOP;
    public static const Colossal.Win32.WM NEXTMENU;
    public static const Colossal.Win32.WM SIZING;
    public static const Colossal.Win32.WM CAPTURECHANGED;
    public static const Colossal.Win32.WM MOVING;
    public static const Colossal.Win32.WM POWERBROADCAST;
    public static const Colossal.Win32.WM DEVICECHANGE;
    public static const Colossal.Win32.WM MDICREATE;
    public static const Colossal.Win32.WM MDIDESTROY;
    public static const Colossal.Win32.WM MDIACTIVATE;
    public static const Colossal.Win32.WM MDIRESTORE;
    public static const Colossal.Win32.WM MDINEXT;
    public static const Colossal.Win32.WM MDIMAXIMIZE;
    public static const Colossal.Win32.WM MDITILE;
    public static const Colossal.Win32.WM MDICASCADE;
    public static const Colossal.Win32.WM MDIICONARRANGE;
    public static const Colossal.Win32.WM MDIGETACTIVE;
    public static const Colossal.Win32.WM MDISETMENU;
    public static const Colossal.Win32.WM ENTERSIZEMOVE;
    public static const Colossal.Win32.WM EXITSIZEMOVE;
    public static const Colossal.Win32.WM DROPFILES;
    public static const Colossal.Win32.WM MDIREFRESHMENU;
    public static const Colossal.Win32.WM IME_SETCONTEXT;
    public static const Colossal.Win32.WM IME_NOTIFY;
    public static const Colossal.Win32.WM IME_CONTROL;
    public static const Colossal.Win32.WM IME_COMPOSITIONFULL;
    public static const Colossal.Win32.WM IME_SELECT;
    public static const Colossal.Win32.WM IME_CHAR;
    public static const Colossal.Win32.WM IME_REQUEST;
    public static const Colossal.Win32.WM IME_KEYDOWN;
    public static const Colossal.Win32.WM IME_KEYUP;
    public static const Colossal.Win32.WM MOUSEHOVER;
    public static const Colossal.Win32.WM MOUSELEAVE;
    public static const Colossal.Win32.WM NCMOUSEHOVER;
    public static const Colossal.Win32.WM NCMOUSELEAVE;
    public static const Colossal.Win32.WM WTSSESSION_CHANGE;
    public static const Colossal.Win32.WM TABLET_FIRST;
    public static const Colossal.Win32.WM TABLET_LAST;
    public static const Colossal.Win32.WM CUT;
    public static const Colossal.Win32.WM COPY;
    public static const Colossal.Win32.WM PASTE;
    public static const Colossal.Win32.WM CLEAR;
    public static const Colossal.Win32.WM UNDO;
    public static const Colossal.Win32.WM RENDERFORMAT;
    public static const Colossal.Win32.WM RENDERALLFORMATS;
    public static const Colossal.Win32.WM DESTROYCLIPBOARD;
    public static const Colossal.Win32.WM DRAWCLIPBOARD;
    public static const Colossal.Win32.WM PAINTCLIPBOARD;
    public static const Colossal.Win32.WM VSCROLLCLIPBOARD;
    public static const Colossal.Win32.WM SIZECLIPBOARD;
    public static const Colossal.Win32.WM ASKCBFORMATNAME;
    public static const Colossal.Win32.WM CHANGECBCHAIN;
    public static const Colossal.Win32.WM HSCROLLCLIPBOARD;
    public static const Colossal.Win32.WM QUERYNEWPALETTE;
    public static const Colossal.Win32.WM PALETTEISCHANGING;
    public static const Colossal.Win32.WM PALETTECHANGED;
    public static const Colossal.Win32.WM HOTKEY;
    public static const Colossal.Win32.WM PRINT;
    public static const Colossal.Win32.WM PRINTCLIENT;
    public static const Colossal.Win32.WM APPCOMMAND;
    public static const Colossal.Win32.WM THEMECHANGED;
    public static const Colossal.Win32.WM CLIPBOARDUPDATE;
    public static const Colossal.Win32.WM DWMCOMPOSITIONCHANGED;
    public static const Colossal.Win32.WM DWMNCRENDERINGCHANGED;
    public static const Colossal.Win32.WM DWMCOLORIZATIONCOLORCHANGED;
    public static const Colossal.Win32.WM DWMWINDOWMAXIMIZEDCHANGE;
    public static const Colossal.Win32.WM GETTITLEBARINFOEX;
    public static const Colossal.Win32.WM HANDHELDFIRST;
    public static const Colossal.Win32.WM HANDHELDLAST;
    public static const Colossal.Win32.WM AFXFIRST;
    public static const Colossal.Win32.WM AFXLAST;
    public static const Colossal.Win32.WM PENWINFIRST;
    public static const Colossal.Win32.WM PENWINLAST;
    public static const Colossal.Win32.WM APP;
    public static const Colossal.Win32.WM USER;
    public static const Colossal.Win32.WM CPL_LAUNCH;
    public static const Colossal.Win32.WM CPL_LAUNCHED;
    public static const Colossal.Win32.WM SYSTIMER;

}
```


## Fields

- `public System.UInt32 value__`  

```csharp
public System.UInt32 value__;
```

- `public static const Colossal.Win32.WM NULL`  

```csharp
public static const Colossal.Win32.WM NULL;
```

- `public static const Colossal.Win32.WM CREATE`  

```csharp
public static const Colossal.Win32.WM CREATE;
```

- `public static const Colossal.Win32.WM DESTROY`  

```csharp
public static const Colossal.Win32.WM DESTROY;
```

- `public static const Colossal.Win32.WM MOVE`  

```csharp
public static const Colossal.Win32.WM MOVE;
```

- `public static const Colossal.Win32.WM SIZE`  

```csharp
public static const Colossal.Win32.WM SIZE;
```

- `public static const Colossal.Win32.WM ACTIVATE`  

```csharp
public static const Colossal.Win32.WM ACTIVATE;
```

- `public static const Colossal.Win32.WM SETFOCUS`  

```csharp
public static const Colossal.Win32.WM SETFOCUS;
```

- `public static const Colossal.Win32.WM KILLFOCUS`  

```csharp
public static const Colossal.Win32.WM KILLFOCUS;
```

- `public static const Colossal.Win32.WM ENABLE`  

```csharp
public static const Colossal.Win32.WM ENABLE;
```

- `public static const Colossal.Win32.WM SETREDRAW`  

```csharp
public static const Colossal.Win32.WM SETREDRAW;
```

- `public static const Colossal.Win32.WM SETTEXT`  

```csharp
public static const Colossal.Win32.WM SETTEXT;
```

- `public static const Colossal.Win32.WM GETTEXT`  

```csharp
public static const Colossal.Win32.WM GETTEXT;
```

- `public static const Colossal.Win32.WM GETTEXTLENGTH`  

```csharp
public static const Colossal.Win32.WM GETTEXTLENGTH;
```

- `public static const Colossal.Win32.WM PAINT`  

```csharp
public static const Colossal.Win32.WM PAINT;
```

- `public static const Colossal.Win32.WM CLOSE`  

```csharp
public static const Colossal.Win32.WM CLOSE;
```

- `public static const Colossal.Win32.WM QUERYENDSESSION`  

```csharp
public static const Colossal.Win32.WM QUERYENDSESSION;
```

- `public static const Colossal.Win32.WM QUERYOPEN`  

```csharp
public static const Colossal.Win32.WM QUERYOPEN;
```

- `public static const Colossal.Win32.WM ENDSESSION`  

```csharp
public static const Colossal.Win32.WM ENDSESSION;
```

- `public static const Colossal.Win32.WM QUIT`  

```csharp
public static const Colossal.Win32.WM QUIT;
```

- `public static const Colossal.Win32.WM ERASEBKGND`  

```csharp
public static const Colossal.Win32.WM ERASEBKGND;
```

- `public static const Colossal.Win32.WM SYSCOLORCHANGE`  

```csharp
public static const Colossal.Win32.WM SYSCOLORCHANGE;
```

- `public static const Colossal.Win32.WM SHOWWINDOW`  

```csharp
public static const Colossal.Win32.WM SHOWWINDOW;
```

- `public static const Colossal.Win32.WM WININICHANGE`  

```csharp
public static const Colossal.Win32.WM WININICHANGE;
```

- `public static const Colossal.Win32.WM SETTINGCHANGE`  

```csharp
public static const Colossal.Win32.WM SETTINGCHANGE;
```

- `public static const Colossal.Win32.WM DEVMODECHANGE`  

```csharp
public static const Colossal.Win32.WM DEVMODECHANGE;
```

- `public static const Colossal.Win32.WM ACTIVATEAPP`  

```csharp
public static const Colossal.Win32.WM ACTIVATEAPP;
```

- `public static const Colossal.Win32.WM FONTCHANGE`  

```csharp
public static const Colossal.Win32.WM FONTCHANGE;
```

- `public static const Colossal.Win32.WM TIMECHANGE`  

```csharp
public static const Colossal.Win32.WM TIMECHANGE;
```

- `public static const Colossal.Win32.WM CANCELMODE`  

```csharp
public static const Colossal.Win32.WM CANCELMODE;
```

- `public static const Colossal.Win32.WM SETCURSOR`  

```csharp
public static const Colossal.Win32.WM SETCURSOR;
```

- `public static const Colossal.Win32.WM MOUSEACTIVATE`  

```csharp
public static const Colossal.Win32.WM MOUSEACTIVATE;
```

- `public static const Colossal.Win32.WM CHILDACTIVATE`  

```csharp
public static const Colossal.Win32.WM CHILDACTIVATE;
```

- `public static const Colossal.Win32.WM QUEUESYNC`  

```csharp
public static const Colossal.Win32.WM QUEUESYNC;
```

- `public static const Colossal.Win32.WM GETMINMAXINFO`  

```csharp
public static const Colossal.Win32.WM GETMINMAXINFO;
```

- `public static const Colossal.Win32.WM PAINTICON`  

```csharp
public static const Colossal.Win32.WM PAINTICON;
```

- `public static const Colossal.Win32.WM ICONERASEBKGND`  

```csharp
public static const Colossal.Win32.WM ICONERASEBKGND;
```

- `public static const Colossal.Win32.WM NEXTDLGCTL`  

```csharp
public static const Colossal.Win32.WM NEXTDLGCTL;
```

- `public static const Colossal.Win32.WM SPOOLERSTATUS`  

```csharp
public static const Colossal.Win32.WM SPOOLERSTATUS;
```

- `public static const Colossal.Win32.WM DRAWITEM`  

```csharp
public static const Colossal.Win32.WM DRAWITEM;
```

- `public static const Colossal.Win32.WM MEASUREITEM`  

```csharp
public static const Colossal.Win32.WM MEASUREITEM;
```

- `public static const Colossal.Win32.WM DELETEITEM`  

```csharp
public static const Colossal.Win32.WM DELETEITEM;
```

- `public static const Colossal.Win32.WM VKEYTOITEM`  

```csharp
public static const Colossal.Win32.WM VKEYTOITEM;
```

- `public static const Colossal.Win32.WM CHARTOITEM`  

```csharp
public static const Colossal.Win32.WM CHARTOITEM;
```

- `public static const Colossal.Win32.WM SETFONT`  

```csharp
public static const Colossal.Win32.WM SETFONT;
```

- `public static const Colossal.Win32.WM GETFONT`  

```csharp
public static const Colossal.Win32.WM GETFONT;
```

- `public static const Colossal.Win32.WM SETHOTKEY`  

```csharp
public static const Colossal.Win32.WM SETHOTKEY;
```

- `public static const Colossal.Win32.WM GETHOTKEY`  

```csharp
public static const Colossal.Win32.WM GETHOTKEY;
```

- `public static const Colossal.Win32.WM QUERYDRAGICON`  

```csharp
public static const Colossal.Win32.WM QUERYDRAGICON;
```

- `public static const Colossal.Win32.WM COMPAREITEM`  

```csharp
public static const Colossal.Win32.WM COMPAREITEM;
```

- `public static const Colossal.Win32.WM GETOBJECT`  

```csharp
public static const Colossal.Win32.WM GETOBJECT;
```

- `public static const Colossal.Win32.WM COMPACTING`  

```csharp
public static const Colossal.Win32.WM COMPACTING;
```

- `public static const Colossal.Win32.WM COMMNOTIFY`  

```csharp
public static const Colossal.Win32.WM COMMNOTIFY;
```

- `public static const Colossal.Win32.WM WINDOWPOSCHANGING`  

```csharp
public static const Colossal.Win32.WM WINDOWPOSCHANGING;
```

- `public static const Colossal.Win32.WM WINDOWPOSCHANGED`  

```csharp
public static const Colossal.Win32.WM WINDOWPOSCHANGED;
```

- `public static const Colossal.Win32.WM POWER`  

```csharp
public static const Colossal.Win32.WM POWER;
```

- `public static const Colossal.Win32.WM COPYDATA`  

```csharp
public static const Colossal.Win32.WM COPYDATA;
```

- `public static const Colossal.Win32.WM CANCELJOURNAL`  

```csharp
public static const Colossal.Win32.WM CANCELJOURNAL;
```

- `public static const Colossal.Win32.WM NOTIFY`  

```csharp
public static const Colossal.Win32.WM NOTIFY;
```

- `public static const Colossal.Win32.WM INPUTLANGCHANGEREQUEST`  

```csharp
public static const Colossal.Win32.WM INPUTLANGCHANGEREQUEST;
```

- `public static const Colossal.Win32.WM INPUTLANGCHANGE`  

```csharp
public static const Colossal.Win32.WM INPUTLANGCHANGE;
```

- `public static const Colossal.Win32.WM TCARD`  

```csharp
public static const Colossal.Win32.WM TCARD;
```

- `public static const Colossal.Win32.WM HELP`  

```csharp
public static const Colossal.Win32.WM HELP;
```

- `public static const Colossal.Win32.WM USERCHANGED`  

```csharp
public static const Colossal.Win32.WM USERCHANGED;
```

- `public static const Colossal.Win32.WM NOTIFYFORMAT`  

```csharp
public static const Colossal.Win32.WM NOTIFYFORMAT;
```

- `public static const Colossal.Win32.WM CONTEXTMENU`  

```csharp
public static const Colossal.Win32.WM CONTEXTMENU;
```

- `public static const Colossal.Win32.WM STYLECHANGING`  

```csharp
public static const Colossal.Win32.WM STYLECHANGING;
```

- `public static const Colossal.Win32.WM STYLECHANGED`  

```csharp
public static const Colossal.Win32.WM STYLECHANGED;
```

- `public static const Colossal.Win32.WM DISPLAYCHANGE`  

```csharp
public static const Colossal.Win32.WM DISPLAYCHANGE;
```

- `public static const Colossal.Win32.WM GETICON`  

```csharp
public static const Colossal.Win32.WM GETICON;
```

- `public static const Colossal.Win32.WM SETICON`  

```csharp
public static const Colossal.Win32.WM SETICON;
```

- `public static const Colossal.Win32.WM NCCREATE`  

```csharp
public static const Colossal.Win32.WM NCCREATE;
```

- `public static const Colossal.Win32.WM NCDESTROY`  

```csharp
public static const Colossal.Win32.WM NCDESTROY;
```

- `public static const Colossal.Win32.WM NCCALCSIZE`  

```csharp
public static const Colossal.Win32.WM NCCALCSIZE;
```

- `public static const Colossal.Win32.WM NCHITTEST`  

```csharp
public static const Colossal.Win32.WM NCHITTEST;
```

- `public static const Colossal.Win32.WM NCPAINT`  

```csharp
public static const Colossal.Win32.WM NCPAINT;
```

- `public static const Colossal.Win32.WM NCACTIVATE`  

```csharp
public static const Colossal.Win32.WM NCACTIVATE;
```

- `public static const Colossal.Win32.WM GETDLGCODE`  

```csharp
public static const Colossal.Win32.WM GETDLGCODE;
```

- `public static const Colossal.Win32.WM SYNCPAINT`  

```csharp
public static const Colossal.Win32.WM SYNCPAINT;
```

- `public static const Colossal.Win32.WM NCMOUSEMOVE`  

```csharp
public static const Colossal.Win32.WM NCMOUSEMOVE;
```

- `public static const Colossal.Win32.WM NCLBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM NCLBUTTONDOWN;
```

- `public static const Colossal.Win32.WM NCLBUTTONUP`  

```csharp
public static const Colossal.Win32.WM NCLBUTTONUP;
```

- `public static const Colossal.Win32.WM NCLBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM NCLBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM NCRBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM NCRBUTTONDOWN;
```

- `public static const Colossal.Win32.WM NCRBUTTONUP`  

```csharp
public static const Colossal.Win32.WM NCRBUTTONUP;
```

- `public static const Colossal.Win32.WM NCRBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM NCRBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM NCMBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM NCMBUTTONDOWN;
```

- `public static const Colossal.Win32.WM NCMBUTTONUP`  

```csharp
public static const Colossal.Win32.WM NCMBUTTONUP;
```

- `public static const Colossal.Win32.WM NCMBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM NCMBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM NCXBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM NCXBUTTONDOWN;
```

- `public static const Colossal.Win32.WM NCXBUTTONUP`  

```csharp
public static const Colossal.Win32.WM NCXBUTTONUP;
```

- `public static const Colossal.Win32.WM NCXBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM NCXBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM INPUT_DEVICE_CHANGE`  

```csharp
public static const Colossal.Win32.WM INPUT_DEVICE_CHANGE;
```

- `public static const Colossal.Win32.WM INPUT`  

```csharp
public static const Colossal.Win32.WM INPUT;
```

- `public static const Colossal.Win32.WM KEYFIRST`  

```csharp
public static const Colossal.Win32.WM KEYFIRST;
```

- `public static const Colossal.Win32.WM KEYDOWN`  

```csharp
public static const Colossal.Win32.WM KEYDOWN;
```

- `public static const Colossal.Win32.WM KEYUP`  

```csharp
public static const Colossal.Win32.WM KEYUP;
```

- `public static const Colossal.Win32.WM CHAR`  

```csharp
public static const Colossal.Win32.WM CHAR;
```

- `public static const Colossal.Win32.WM DEADCHAR`  

```csharp
public static const Colossal.Win32.WM DEADCHAR;
```

- `public static const Colossal.Win32.WM SYSKEYDOWN`  

```csharp
public static const Colossal.Win32.WM SYSKEYDOWN;
```

- `public static const Colossal.Win32.WM SYSKEYUP`  

```csharp
public static const Colossal.Win32.WM SYSKEYUP;
```

- `public static const Colossal.Win32.WM SYSCHAR`  

```csharp
public static const Colossal.Win32.WM SYSCHAR;
```

- `public static const Colossal.Win32.WM SYSDEADCHAR`  

```csharp
public static const Colossal.Win32.WM SYSDEADCHAR;
```

- `public static const Colossal.Win32.WM UNICHAR`  

```csharp
public static const Colossal.Win32.WM UNICHAR;
```

- `public static const Colossal.Win32.WM KEYLAST`  

```csharp
public static const Colossal.Win32.WM KEYLAST;
```

- `public static const Colossal.Win32.WM IME_STARTCOMPOSITION`  

```csharp
public static const Colossal.Win32.WM IME_STARTCOMPOSITION;
```

- `public static const Colossal.Win32.WM IME_ENDCOMPOSITION`  

```csharp
public static const Colossal.Win32.WM IME_ENDCOMPOSITION;
```

- `public static const Colossal.Win32.WM IME_COMPOSITION`  

```csharp
public static const Colossal.Win32.WM IME_COMPOSITION;
```

- `public static const Colossal.Win32.WM IME_KEYLAST`  

```csharp
public static const Colossal.Win32.WM IME_KEYLAST;
```

- `public static const Colossal.Win32.WM INITDIALOG`  

```csharp
public static const Colossal.Win32.WM INITDIALOG;
```

- `public static const Colossal.Win32.WM COMMAND`  

```csharp
public static const Colossal.Win32.WM COMMAND;
```

- `public static const Colossal.Win32.WM SYSCOMMAND`  

```csharp
public static const Colossal.Win32.WM SYSCOMMAND;
```

- `public static const Colossal.Win32.WM TIMER`  

```csharp
public static const Colossal.Win32.WM TIMER;
```

- `public static const Colossal.Win32.WM HSCROLL`  

```csharp
public static const Colossal.Win32.WM HSCROLL;
```

- `public static const Colossal.Win32.WM VSCROLL`  

```csharp
public static const Colossal.Win32.WM VSCROLL;
```

- `public static const Colossal.Win32.WM INITMENU`  

```csharp
public static const Colossal.Win32.WM INITMENU;
```

- `public static const Colossal.Win32.WM INITMENUPOPUP`  

```csharp
public static const Colossal.Win32.WM INITMENUPOPUP;
```

- `public static const Colossal.Win32.WM MENUSELECT`  

```csharp
public static const Colossal.Win32.WM MENUSELECT;
```

- `public static const Colossal.Win32.WM MENUCHAR`  

```csharp
public static const Colossal.Win32.WM MENUCHAR;
```

- `public static const Colossal.Win32.WM ENTERIDLE`  

```csharp
public static const Colossal.Win32.WM ENTERIDLE;
```

- `public static const Colossal.Win32.WM MENURBUTTONUP`  

```csharp
public static const Colossal.Win32.WM MENURBUTTONUP;
```

- `public static const Colossal.Win32.WM MENUDRAG`  

```csharp
public static const Colossal.Win32.WM MENUDRAG;
```

- `public static const Colossal.Win32.WM MENUGETOBJECT`  

```csharp
public static const Colossal.Win32.WM MENUGETOBJECT;
```

- `public static const Colossal.Win32.WM UNINITMENUPOPUP`  

```csharp
public static const Colossal.Win32.WM UNINITMENUPOPUP;
```

- `public static const Colossal.Win32.WM MENUCOMMAND`  

```csharp
public static const Colossal.Win32.WM MENUCOMMAND;
```

- `public static const Colossal.Win32.WM CHANGEUISTATE`  

```csharp
public static const Colossal.Win32.WM CHANGEUISTATE;
```

- `public static const Colossal.Win32.WM UPDATEUISTATE`  

```csharp
public static const Colossal.Win32.WM UPDATEUISTATE;
```

- `public static const Colossal.Win32.WM QUERYUISTATE`  

```csharp
public static const Colossal.Win32.WM QUERYUISTATE;
```

- `public static const Colossal.Win32.WM CTLCOLORMSGBOX`  

```csharp
public static const Colossal.Win32.WM CTLCOLORMSGBOX;
```

- `public static const Colossal.Win32.WM CTLCOLOREDIT`  

```csharp
public static const Colossal.Win32.WM CTLCOLOREDIT;
```

- `public static const Colossal.Win32.WM CTLCOLORLISTBOX`  

```csharp
public static const Colossal.Win32.WM CTLCOLORLISTBOX;
```

- `public static const Colossal.Win32.WM CTLCOLORBTN`  

```csharp
public static const Colossal.Win32.WM CTLCOLORBTN;
```

- `public static const Colossal.Win32.WM CTLCOLORDLG`  

```csharp
public static const Colossal.Win32.WM CTLCOLORDLG;
```

- `public static const Colossal.Win32.WM CTLCOLORSCROLLBAR`  

```csharp
public static const Colossal.Win32.WM CTLCOLORSCROLLBAR;
```

- `public static const Colossal.Win32.WM CTLCOLORSTATIC`  

```csharp
public static const Colossal.Win32.WM CTLCOLORSTATIC;
```

- `public static const Colossal.Win32.WM MOUSEFIRST`  

```csharp
public static const Colossal.Win32.WM MOUSEFIRST;
```

- `public static const Colossal.Win32.WM MOUSEMOVE`  

```csharp
public static const Colossal.Win32.WM MOUSEMOVE;
```

- `public static const Colossal.Win32.WM LBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM LBUTTONDOWN;
```

- `public static const Colossal.Win32.WM LBUTTONUP`  

```csharp
public static const Colossal.Win32.WM LBUTTONUP;
```

- `public static const Colossal.Win32.WM LBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM LBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM RBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM RBUTTONDOWN;
```

- `public static const Colossal.Win32.WM RBUTTONUP`  

```csharp
public static const Colossal.Win32.WM RBUTTONUP;
```

- `public static const Colossal.Win32.WM RBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM RBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM MBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM MBUTTONDOWN;
```

- `public static const Colossal.Win32.WM MBUTTONUP`  

```csharp
public static const Colossal.Win32.WM MBUTTONUP;
```

- `public static const Colossal.Win32.WM MBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM MBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM MOUSEWHEEL`  

```csharp
public static const Colossal.Win32.WM MOUSEWHEEL;
```

- `public static const Colossal.Win32.WM XBUTTONDOWN`  

```csharp
public static const Colossal.Win32.WM XBUTTONDOWN;
```

- `public static const Colossal.Win32.WM XBUTTONUP`  

```csharp
public static const Colossal.Win32.WM XBUTTONUP;
```

- `public static const Colossal.Win32.WM XBUTTONDBLCLK`  

```csharp
public static const Colossal.Win32.WM XBUTTONDBLCLK;
```

- `public static const Colossal.Win32.WM MOUSEHWHEEL`  

```csharp
public static const Colossal.Win32.WM MOUSEHWHEEL;
```

- `public static const Colossal.Win32.WM MOUSELAST`  

```csharp
public static const Colossal.Win32.WM MOUSELAST;
```

- `public static const Colossal.Win32.WM PARENTNOTIFY`  

```csharp
public static const Colossal.Win32.WM PARENTNOTIFY;
```

- `public static const Colossal.Win32.WM ENTERMENULOOP`  

```csharp
public static const Colossal.Win32.WM ENTERMENULOOP;
```

- `public static const Colossal.Win32.WM EXITMENULOOP`  

```csharp
public static const Colossal.Win32.WM EXITMENULOOP;
```

- `public static const Colossal.Win32.WM NEXTMENU`  

```csharp
public static const Colossal.Win32.WM NEXTMENU;
```

- `public static const Colossal.Win32.WM SIZING`  

```csharp
public static const Colossal.Win32.WM SIZING;
```

- `public static const Colossal.Win32.WM CAPTURECHANGED`  

```csharp
public static const Colossal.Win32.WM CAPTURECHANGED;
```

- `public static const Colossal.Win32.WM MOVING`  

```csharp
public static const Colossal.Win32.WM MOVING;
```

- `public static const Colossal.Win32.WM POWERBROADCAST`  

```csharp
public static const Colossal.Win32.WM POWERBROADCAST;
```

- `public static const Colossal.Win32.WM DEVICECHANGE`  

```csharp
public static const Colossal.Win32.WM DEVICECHANGE;
```

- `public static const Colossal.Win32.WM MDICREATE`  

```csharp
public static const Colossal.Win32.WM MDICREATE;
```

- `public static const Colossal.Win32.WM MDIDESTROY`  

```csharp
public static const Colossal.Win32.WM MDIDESTROY;
```

- `public static const Colossal.Win32.WM MDIACTIVATE`  

```csharp
public static const Colossal.Win32.WM MDIACTIVATE;
```

- `public static const Colossal.Win32.WM MDIRESTORE`  

```csharp
public static const Colossal.Win32.WM MDIRESTORE;
```

- `public static const Colossal.Win32.WM MDINEXT`  

```csharp
public static const Colossal.Win32.WM MDINEXT;
```

- `public static const Colossal.Win32.WM MDIMAXIMIZE`  

```csharp
public static const Colossal.Win32.WM MDIMAXIMIZE;
```

- `public static const Colossal.Win32.WM MDITILE`  

```csharp
public static const Colossal.Win32.WM MDITILE;
```

- `public static const Colossal.Win32.WM MDICASCADE`  

```csharp
public static const Colossal.Win32.WM MDICASCADE;
```

- `public static const Colossal.Win32.WM MDIICONARRANGE`  

```csharp
public static const Colossal.Win32.WM MDIICONARRANGE;
```

- `public static const Colossal.Win32.WM MDIGETACTIVE`  

```csharp
public static const Colossal.Win32.WM MDIGETACTIVE;
```

- `public static const Colossal.Win32.WM MDISETMENU`  

```csharp
public static const Colossal.Win32.WM MDISETMENU;
```

- `public static const Colossal.Win32.WM ENTERSIZEMOVE`  

```csharp
public static const Colossal.Win32.WM ENTERSIZEMOVE;
```

- `public static const Colossal.Win32.WM EXITSIZEMOVE`  

```csharp
public static const Colossal.Win32.WM EXITSIZEMOVE;
```

- `public static const Colossal.Win32.WM DROPFILES`  

```csharp
public static const Colossal.Win32.WM DROPFILES;
```

- `public static const Colossal.Win32.WM MDIREFRESHMENU`  

```csharp
public static const Colossal.Win32.WM MDIREFRESHMENU;
```

- `public static const Colossal.Win32.WM IME_SETCONTEXT`  

```csharp
public static const Colossal.Win32.WM IME_SETCONTEXT;
```

- `public static const Colossal.Win32.WM IME_NOTIFY`  

```csharp
public static const Colossal.Win32.WM IME_NOTIFY;
```

- `public static const Colossal.Win32.WM IME_CONTROL`  

```csharp
public static const Colossal.Win32.WM IME_CONTROL;
```

- `public static const Colossal.Win32.WM IME_COMPOSITIONFULL`  

```csharp
public static const Colossal.Win32.WM IME_COMPOSITIONFULL;
```

- `public static const Colossal.Win32.WM IME_SELECT`  

```csharp
public static const Colossal.Win32.WM IME_SELECT;
```

- `public static const Colossal.Win32.WM IME_CHAR`  

```csharp
public static const Colossal.Win32.WM IME_CHAR;
```

- `public static const Colossal.Win32.WM IME_REQUEST`  

```csharp
public static const Colossal.Win32.WM IME_REQUEST;
```

- `public static const Colossal.Win32.WM IME_KEYDOWN`  

```csharp
public static const Colossal.Win32.WM IME_KEYDOWN;
```

- `public static const Colossal.Win32.WM IME_KEYUP`  

```csharp
public static const Colossal.Win32.WM IME_KEYUP;
```

- `public static const Colossal.Win32.WM MOUSEHOVER`  

```csharp
public static const Colossal.Win32.WM MOUSEHOVER;
```

- `public static const Colossal.Win32.WM MOUSELEAVE`  

```csharp
public static const Colossal.Win32.WM MOUSELEAVE;
```

- `public static const Colossal.Win32.WM NCMOUSEHOVER`  

```csharp
public static const Colossal.Win32.WM NCMOUSEHOVER;
```

- `public static const Colossal.Win32.WM NCMOUSELEAVE`  

```csharp
public static const Colossal.Win32.WM NCMOUSELEAVE;
```

- `public static const Colossal.Win32.WM WTSSESSION_CHANGE`  

```csharp
public static const Colossal.Win32.WM WTSSESSION_CHANGE;
```

- `public static const Colossal.Win32.WM TABLET_FIRST`  

```csharp
public static const Colossal.Win32.WM TABLET_FIRST;
```

- `public static const Colossal.Win32.WM TABLET_LAST`  

```csharp
public static const Colossal.Win32.WM TABLET_LAST;
```

- `public static const Colossal.Win32.WM CUT`  

```csharp
public static const Colossal.Win32.WM CUT;
```

- `public static const Colossal.Win32.WM COPY`  

```csharp
public static const Colossal.Win32.WM COPY;
```

- `public static const Colossal.Win32.WM PASTE`  

```csharp
public static const Colossal.Win32.WM PASTE;
```

- `public static const Colossal.Win32.WM CLEAR`  

```csharp
public static const Colossal.Win32.WM CLEAR;
```

- `public static const Colossal.Win32.WM UNDO`  

```csharp
public static const Colossal.Win32.WM UNDO;
```

- `public static const Colossal.Win32.WM RENDERFORMAT`  

```csharp
public static const Colossal.Win32.WM RENDERFORMAT;
```

- `public static const Colossal.Win32.WM RENDERALLFORMATS`  

```csharp
public static const Colossal.Win32.WM RENDERALLFORMATS;
```

- `public static const Colossal.Win32.WM DESTROYCLIPBOARD`  

```csharp
public static const Colossal.Win32.WM DESTROYCLIPBOARD;
```

- `public static const Colossal.Win32.WM DRAWCLIPBOARD`  

```csharp
public static const Colossal.Win32.WM DRAWCLIPBOARD;
```

- `public static const Colossal.Win32.WM PAINTCLIPBOARD`  

```csharp
public static const Colossal.Win32.WM PAINTCLIPBOARD;
```

- `public static const Colossal.Win32.WM VSCROLLCLIPBOARD`  

```csharp
public static const Colossal.Win32.WM VSCROLLCLIPBOARD;
```

- `public static const Colossal.Win32.WM SIZECLIPBOARD`  

```csharp
public static const Colossal.Win32.WM SIZECLIPBOARD;
```

- `public static const Colossal.Win32.WM ASKCBFORMATNAME`  

```csharp
public static const Colossal.Win32.WM ASKCBFORMATNAME;
```

- `public static const Colossal.Win32.WM CHANGECBCHAIN`  

```csharp
public static const Colossal.Win32.WM CHANGECBCHAIN;
```

- `public static const Colossal.Win32.WM HSCROLLCLIPBOARD`  

```csharp
public static const Colossal.Win32.WM HSCROLLCLIPBOARD;
```

- `public static const Colossal.Win32.WM QUERYNEWPALETTE`  

```csharp
public static const Colossal.Win32.WM QUERYNEWPALETTE;
```

- `public static const Colossal.Win32.WM PALETTEISCHANGING`  

```csharp
public static const Colossal.Win32.WM PALETTEISCHANGING;
```

- `public static const Colossal.Win32.WM PALETTECHANGED`  

```csharp
public static const Colossal.Win32.WM PALETTECHANGED;
```

- `public static const Colossal.Win32.WM HOTKEY`  

```csharp
public static const Colossal.Win32.WM HOTKEY;
```

- `public static const Colossal.Win32.WM PRINT`  

```csharp
public static const Colossal.Win32.WM PRINT;
```

- `public static const Colossal.Win32.WM PRINTCLIENT`  

```csharp
public static const Colossal.Win32.WM PRINTCLIENT;
```

- `public static const Colossal.Win32.WM APPCOMMAND`  

```csharp
public static const Colossal.Win32.WM APPCOMMAND;
```

- `public static const Colossal.Win32.WM THEMECHANGED`  

```csharp
public static const Colossal.Win32.WM THEMECHANGED;
```

- `public static const Colossal.Win32.WM CLIPBOARDUPDATE`  

```csharp
public static const Colossal.Win32.WM CLIPBOARDUPDATE;
```

- `public static const Colossal.Win32.WM DWMCOMPOSITIONCHANGED`  

```csharp
public static const Colossal.Win32.WM DWMCOMPOSITIONCHANGED;
```

- `public static const Colossal.Win32.WM DWMNCRENDERINGCHANGED`  

```csharp
public static const Colossal.Win32.WM DWMNCRENDERINGCHANGED;
```

- `public static const Colossal.Win32.WM DWMCOLORIZATIONCOLORCHANGED`  

```csharp
public static const Colossal.Win32.WM DWMCOLORIZATIONCOLORCHANGED;
```

- `public static const Colossal.Win32.WM DWMWINDOWMAXIMIZEDCHANGE`  

```csharp
public static const Colossal.Win32.WM DWMWINDOWMAXIMIZEDCHANGE;
```

- `public static const Colossal.Win32.WM GETTITLEBARINFOEX`  

```csharp
public static const Colossal.Win32.WM GETTITLEBARINFOEX;
```

- `public static const Colossal.Win32.WM HANDHELDFIRST`  

```csharp
public static const Colossal.Win32.WM HANDHELDFIRST;
```

- `public static const Colossal.Win32.WM HANDHELDLAST`  

```csharp
public static const Colossal.Win32.WM HANDHELDLAST;
```

- `public static const Colossal.Win32.WM AFXFIRST`  

```csharp
public static const Colossal.Win32.WM AFXFIRST;
```

- `public static const Colossal.Win32.WM AFXLAST`  

```csharp
public static const Colossal.Win32.WM AFXLAST;
```

- `public static const Colossal.Win32.WM PENWINFIRST`  

```csharp
public static const Colossal.Win32.WM PENWINFIRST;
```

- `public static const Colossal.Win32.WM PENWINLAST`  

```csharp
public static const Colossal.Win32.WM PENWINLAST;
```

- `public static const Colossal.Win32.WM APP`  

```csharp
public static const Colossal.Win32.WM APP;
```

- `public static const Colossal.Win32.WM USER`  

```csharp
public static const Colossal.Win32.WM USER;
```

- `public static const Colossal.Win32.WM CPL_LAUNCH`  

```csharp
public static const Colossal.Win32.WM CPL_LAUNCH;
```

- `public static const Colossal.Win32.WM CPL_LAUNCHED`  

```csharp
public static const Colossal.Win32.WM CPL_LAUNCHED;
```

- `public static const Colossal.Win32.WM SYSTIMER`  

```csharp
public static const Colossal.Win32.WM SYSTIMER;
```


