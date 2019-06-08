# Windows Data Types

The data types supported by Windows are used to define function return values, function and message parameters, and structure members. They define the size and meaning of these elements.

The following table contains the following types: character, integer, Boolean, pointer, and handle. The character, integer, and Boolean types are common to most C compilers. Most of the pointer-type names begin with a prefix of P or LP. Handles refer to a resource that has been loaded into memory.

| Name       | Description / O2 definition |
| ---------- | ----------- |
| **APIENTRY** | The calling convention for system functions.<br>`#define APIENTRY WINAPI` |
| **ATOM** | An atom.<br>`typedef word ATOM;` |
| **BOOL** | A Boolean variable (should be TRUE or FALSE).<br>`typedef bool BOOL;` |
| **BOOLEAN** | A Boolean variable (should be TRUE or FALSE).<br>`typedef boolean BOOLEAN;` |
| **BYTE** | A byte (8 bits).<br>`typedef byte BYTE;` |
| **CALLBACK** | The calling convention for callback functions.<br>`#define CALLBACK stdcall` (32-bit) `#define CALLBACK ms64` (64-bit) |
| **CCHAR** | An 8-bit Windows (ANSI) character.<br>`typedef char CCHAR;` |
| **CHAR** | An 8-bit Windows (ANSI) character.<br>`typedef char CHAR;` |
| **COLORREF** | The red, green, blue (RGB) color value (32 bits).<br>`typedef dword COLORREF;` |
| **CONST** | A variable whose value is to remain constant during execution.<br>`#define CONST const` |
| **DWORD** | 	A 32-bit unsigned integer. The range is 0 through 4294967295 decimal.<br>`typedef dword DWORD;` |
| **DWORDLONG** | 	A 64-bit unsigned integer. The range is 0 through 18446744073709551615 decimal.<br>`typedef unsigned __int64 DWORDLONG;` |
| **DWORD_PTR** | An unsigned long type for pointer precision. Use when casting a pointer to a long type to perform pointer arithmetic. (Also commonly used for general 32-bit parameters that have been extended to 64 bits in 64-bit Windows.)<br>`typedef ULONG_PTR DWORD_PTR;` |
| **DWORD32** | A 32-bit unsigned integer.<br>`typedef dword DWORD32;` |
| **DWORD64** | A 64-bit unsigned integer.<br>`typedef unsigned __int64 DWORD64;` |
| **FLOAT** | A floating-point variable.<br>`typedef float FLOAT;` |
| **HACCEL** | A handle to an accelerator table.<br>`typedef HANDLE HACCEL;` |
| **HALF_PTR** | A handle to an accelerator table.<br>`typedef int HALF_PTR;` (32-bit) `typedef short HALF_PTR;` (64-bit) |
| **HANDLE** | A handle to an object.<br>`typedef sys HANDLE;` |
| **HBITMAP** | A handle to a bitmap.<br>`typedef HANDLE HBITMAP;` |
| **HBRUSH** | A handle to a brush.<br>`typedef HANDLE HBRUSH;` |
| **HCOLORSPACE** | A handle to a color space.<br>`typedef HANDLE HCOLORSPACE;` |
| **HCONV** | A handle to a dynamic data exchange (DDE) conversation.<br>`typedef HANDLE HCONV;` |
| **HCONVLIST** | A handle to a DDE conversation list.<br>`typedef HANDLE HCONVLIST;` |
| **HCURSOR** | A handle to a cursor.<br>`typedef HANDLE HCURSOR;` |
| **HDC** | A handle to a device context (DC).<br>`typedef HANDLE HDC;` |
| **HDDEDATA** | A handle to DDE data.<br>`typedef HANDLE HDDEDATA;` |
| **HDESK** | A handle to a desktop.<br>`typedef HANDLE HDESK;` |
| **HDROP** | A handle to an internal drop structure.<br>`typedef HANDLE HDROP;` |
| **HDWP** | A handle to a deferred window position structure.<br>`typedef HANDLE HDWP;` |
| **HENHMETAFILE** | A handle to an enhanced metafile.<br>`typedef HANDLE HENHMETAFILE;` |
| **HFILE** | A handle to a file opened by **OpenFile**, not **CreateFile**.<br>`typedef HANDLE HFILE;` |
| **HFONT** | A handle to a font.<br>`typedef HANDLE HFONT;` |
| **HGDIOBJ** | A handle to a GDI objet.<br>`typedef HANDLE HGDIOBJ;` |
| **HGLOBAL** | A handle to a global memory block.<br>`typedef HANDLE HGLOBAL;` |
| **HHOOK** | A handle to a hook.<br>`typedef HANDLE HHOOK;` |
| **HICON** | A handle to an icon.<br>`typedef HANDLE HICON;` |
| **HINSTANCE** | A handle to an instance. This is the base address of the module in memory. HMODULE and HINSTANCE are the same today, but represented different things in 16-bit Windows.<br>`typedef HANDLE HINSTANCE;` |
| **HKEY** | A handle to a registry key.<br>`typedef HANDLE HKEY;` |
| **HKL** | An input locale identifier.<br>`typedef HANDLE HKL;` |
| **HLOCAL** | A handle to a local memory block.<br>`typedef HANDLE HLOCAL;` |
| **HMENU** | A handle to a menu.<br>`typedef HANDLE HMENU;` |
| **HMETAFILE** | A handle to a metafile.<br>`typedef HANDLE HMETAFILE;` |
| **HMODULE** | A handle to a module. The is the base address of the module in memory. HMODULE and HINSTANCE are the same in current versions of Windows, but represented different things in 16-bit Windows.<br>`typedef HANDLE HMODULE;` |
| **HMONITOR** | A handle to a display monitor.<br>`typedef HANDLE HMONITOR;` |
| **HPALETTE** | A handle to a palette.<br>`typedef HANDLE HPALETTE;` |
| **HPEN** | A handle to a pen.<br>`typedef HANDLE HPEN;` |
| **HRESULT** | The return codes used by COM interfaces.<br>`typedef long HRESULT;` |
| **HRGN** | A handle to a region.<br>`typedef HANDLE HRGN;` |
| **HRSRC** | A handle to a resource.<br>`typedef HANDLE HRSRC;` |
| **HSZ** | A handle to a DDE string.<br>`typedef HANDLE HSZ;` |
| **HWINSTA** | A handle to a window station.<br>`typedef HANDLE HWINSTA;` |
| **HWND** | A handle to a window.<br>`typedef HANDLE HWND;` |
| **INT** | A 32-bit signed integer. The range is -2147483648 through 2147483647 decimal.<br>`typedef int INT;` |
| **INT_PTR** | A signed integer type for pointer precision. Use when casting a pointer to an integer to perform pointer arithmetic.<br>`typedef int INT_PTR;` (32-bit) typedef `__int64 INT_PTR;` (64-bit) |
| **INT8** | An 8-bit signed integer.<br>`typedef sbyte INT8;` |
| **INT16** | A 16-bit signed integer.<br>`typedef signed short INT16;` |
| **INT32** | A 32-bit signed integer.<br>`typedef signed int INT32;` |
| **INT64** | A 64-bit signed integer.<br>`typedef signed __int64 INT64;` |
| **LANGID** | A language identifier.<br>`typedef word LANGID;` |
| **LCID** | A locale identifier.<br>`typedef dword LCID;` |
| **LCTYPE** | A locale information type.<br>`typedef dword LCTYPE;` |
| **LGRPID** | A language group identifier.<br>`typedef dword LGRPID;` |
| **LONG** | A 32-bit signed integer. The range is 2147483648 through 2147483647 decimal.<br>`typedef long LONG;` |
| **LONGLONG** | A 64-bit signed integer. The range is 9223372036854775808 through 9223372036854775807 decimal.<br>`typedef __int64 LONGLONG;` |
| **LONG_PTR** | A signed long type for pointer precision. Use when casting a pointer to a long to perform pointer arithmetic.<br>`typedef long LONG_PTR;` (32-bit) `typedef __int64 LONG_PTR;`(64-bit) |
| **LONG32** | A 32-bit signed integer. The range is 2147483648 through 2147483647 decimal.<br>`typedef signed int LONG32;` |
| **LONG64** | A 64-bit signed integer. The range is 9223372036854775808 through 9223372036854775807 decimal.<br>`typedef __int64 LONG64;` |
| **LPARAM** | A message parameter.<br>`typedef LONG_PTR LPARAM;` |
| **LPBOOL** | A pointer to a BOOL.<br>`typedef bool *LPBOOL;` |
| **LPBYTE** | A pointer to a BYTE.<br>`typedef byte *LPBYTE;` |
| **LPCOLORREF** | A pointer to a COLORREF value.<br>`typedef dword *LPCOLORREF;` |
| **LPCSTR** | A pointer to a constant null-terminated string of 8-bit Windows (ANSI) characters.<br>`typedef char *LPCSTR;` |
| **LPCTSTR** | An LPCWSTR if UNICODE is defined, an LPCSTR otherwise.<br>`typedef LPCWSTR LPCTSTR; (UNICODE) typedef LPCSTR LPCTSTR; (ANSI)` |
| **LPCVOID** | A pointer to a constant of any type.<br>`typedef void *LPCVOID;` |
| **LPCWSTR** | A pointer to a constant null-terminated string of 16-bit Unicode characters.<br>`typedef wchar *LPCWSTR;` |
| **LPDWORD** | A pointer to a DWORD.<br>`typedef dword *LPDWORD;` |
| **LPHANDLE** | A pointer to a HANDLE.<br>`typedef HANDLE *LPHANDLE;` |
| **LPINT** | A pointer to an INT.<br>`typedef int *LPINT;` |
| **LPLONG** | A pointer to an LONG.<br>`typedef long *LPLONG;` |
| **LPSTR** | A pointer to a null-terminated string of 8-bit Windows (ANSI) characters.<br>`typedef char *LPSTR;` |
| **LPTSTR** | An LPWSTR if UNICODE is defined, an LPSTR otherwise<br>`typedef LPWSTR LPTSTR;` (UNICODE) `typedef LPSTR LPTSTR;` (ANSI) |
| **LPVOID** | A pointer to any type.<br>`typedef void *LPVOID;` |
| **LPWORD** | A pointer to a a WORD.<br>`typedef word *LPWORD;` |
| **LPWSTR** | A pointer to a null-terminated string of 16-bit Unicode characters.<br>`typedef wchar *LPWSTR;` |
| **LRESULT** | Signed result of message processing.<br>`typedef LONG_PTR LRESULT;` |
| **PBOOL** | A pointer to a BOOL.<br>`typedef bool *PBOOL;` |
| **PBOOLEAN** | A pointer to a BOOLEAN.<br>`typedef boolean *PBOOLEAN;` |
| **PBYTE** | A pointer to a BYTE.<br>`typedef byte *PBYTE;` |
| **PCHAR** | A pointer to a CHAR.<br>`typedef char *PCHAR;` |
| **PCSTR** | A pointer to a constant null-terminated string of 8-bit Windows (ANSI) characters.<br>`typedef char *PCSTR;` |
| **PCTSTR** | A PCWSTR if UNICODE is defined, a PCSTR otherwise.<br>`typedef LPCWSTR PCTSTR;` (UNICODE) `typedef LPCSTR PCTSTR;` (ANSI) |
| **PCWSTR** | A pointer to a constant null-terminated string of 16-bit Unicode characters.<br>`typedef wchar *PCWSTR;` |
| **PDWORD** | A pointer to a DWORD.<br>`typedef dword *PDWORD;` |
| **PDWORDLONG** | A pointer to a DWORDLONG.<br>`typedef DWORDLONG *PDWORDLONG;` |
| **PDWORD_PTR** | A pointer to a DWORD_PTR.<br>`typedef DWORD_PTR *PDWORD_PTR;` |
| **PDWORD32** | A pointer to a DWORD32.<br>`typedef DWORD32 *PDWORD32;` |
| **PDWORD64** | A pointer to a DWORD64.<br>`typedef DWORD64 *PDWORD64;` |
| **PFLOAT** | A pointer to a FLOAT.<br>`typedef float *PFLOAT;` |
| **PHALF_PTR** | A pointer to a HALF_PTR.<br>`typedef HALF_PTR *PHALF_PTR;` |
| **PHANDLE** | A pointer to a HANDLE.<br>`typedef HANDLE *PHANDLE;` |
| **PHKEY** | A pointer to an HKEY.<br>`typedef HKEY *PHKEY;` |
| **PINT** | A pointer to an INT.<br>`typedef int *PINT;` |
| **PINT_PTR** | A pointer to an INT_PTR.<br>`typedef INT_PTR *PINT_PTR;` |
| **PINT8** | A pointer to an INT8.<br>`typedef INT8 *PINT8;` |
| **PINT16** | A pointer to an INT16.<br>`typedef INT16 *PINT16;` |
| **PINT32** | A pointer to an INT32.<br>`typedef INT32 *PINT32;` |
| **PINT64** | A pointer to an INT64.<br>`typedef INT64 *PINT64;` |
| **PLCID** | A pointer to an LCID.<br>`typedef PDWORD PLCID;` |
| **PLONG** | A pointer to an LONG.<br>`typedef LONG *PLONG;` |
| **PLONGLONG** | A pointer to an LONGLONG.<br>`typedef LONGLONG *PLONGLONG;` |
| **PLONG_PTR** | A pointer to an LONG_PTR.<br>`typedef LONG_PTR *PLONG_PTR;` |
| **PLONG32** | A pointer to a LONG32.<br>`typedef LONG32 *PLONG32;` |
| **PLONG64** | A pointer to a LONG64.<br>`typedef LONG64 *PLONG64;` |
| **POINTER_32** | A 32-bit pointer. On a 32-bit system, this is a native pointer. On a 64-bit system, this is a truncated 64-bit pointer. |
| **POINTER_64** | A 64-bit pointer. On a 64-bit system, this is a native pointer. On a 32-bit system, this is a sign-extended 32-bit pointer. |
| **POINTER_SIGNED** | A signed pointer. |
| **POINTER_UNSIGNED** | A unsigned pointer. |
| **PSHORT** | A pointer to an SHORT.<br>`typedef short *PSHORT;` |
| **PSIZE_T** | A pointer to an SIZE_T.<br>`typedef SIZE_T *PSIZE_T;` |
| **PSSIZE_T** | A pointer to an SSIZE_T.<br>`typedef SSIZE_T *PSSIZE_T;` |
| **PSTR** | A pointer to a null-terminated string of 8-bit Windows (ANSI) characters.<br>`typedef char *PSTR;` |
| **PTBYTE** | A pointer to a TBYTE.<br>`typedef TBYTE *PTBYTE;` |
| **PTCHAR** | A pointer to a TCHAR.<br>`typedef TCHAR *PTCHAR;` |
| **PTSTR** | A PWSTR if UNICODE is defined, a PSTR otherwise.<br>`typedef LPWSTR PTSTR;` (UNICODE) `typedef LPSTR PTSTR;` (ANSI) |
| **PUCHAR** | A pointer to a UCHAR.<br>`typedef UCHAR *PUCHAR;` |
| **PUHALF_PTR** | A pointer to a UHALF_PTR.<br>`typedef UHALF_PTR *PUHALF_PTR;` |
| **PUINT** | A pointer to a UINT.<br>`typedef uint *PUINT;` |
| **PUINT_PTR** | A pointer to a UINT.<br>`typedef UINT_PTR *PUINT_PTR;` |
| **PUINT8** | A pointer to a UINT8.<br>`typedef UINT8 *PUINT8;` |
| **PUINT16** | A pointer to a UINT16.<br>`typedef UINT16 *PUINT16;` |
| **PUINT32** | A pointer to a UINT32.<br>`typedef UINT32 *PUINT32;` |
| **PUINT64** | A pointer to a UINT64.<br>`typedef UINT64 *PUINT64;` |
| **PULONG** | A pointer to a ULONG.<br>`typedef ULONG *PULONG;` |
| **PULONGLONG** | A pointer to a ULONGLONG.<br>`typedef ULONGLONG *PULONGLONG;` |
| **PULONG_PTR** | A pointer to a ULONG_PTR.<br>`typedef ULONG_PTR *PULONG_PTR;` |
| **PULONG32** | A pointer to a ULONG32.<br>`typedef ULONG32 *PULONG32;` |
| **PULONG64** | A pointer to a ULONG64.<br>`typedef ULONG64 *PULONG64;` |
| **PUSHORT** | A pointer to a USHORT.<br>`typedef USHORT *PUSHORT;` |
| **PVOID** | A pointer to any type.<br>`typedef void *LPVOID;` |
| **PWCHAR** | A pointer to a WCHAR.<br>`typedef wchar *PWCHAR;` |
| **PWORD** | A pointer to a WORD.<br>`typedef word *PWORD;` |
| **PWSTR** | A pointer to a null-terminated string of 16-bit Unicode characters.<br>`typedef wchar *PWSTR;` |
| **QWORD** | A pointer to a A 64-bit unsigned integer.<br>`typedef qword QWORD;` |
| **SC_HANDLE** | A handle to a service control manager database.<br>`typedef HANDLE SC_HANDLE;` |
| **SC_LOCK** | A lock to a service control manager database.<br>`typedef LPVOID SC_LOCK;` |
| **SERVICE_STATUS_HANDLE** | A handle to a service status value.<br>`typedef HANDLE SERVICE_STATUS_HANDLE;;` |
| **SHORT** | A 16-bit integer. The range is 32768 through 32767 decimal.<br>`typedef short SHORT;` |
| **SIZE_T** | The maximum number of bytes to which a pointer can point. Use for a count that must span the full range of a pointer.<br>`typedef ULONG_PTR SIZE_T;` |
| **SSIZE_T** | A signed version of SIZE_T<br>`typedef LONG_PTR SSIZE_T;` |
| **TBYTE** | A WCHAR if UNICODE is defined, a CHAR otherwise.<br>`typedef wchar TBYTE; (UNICODE) `typedef unsigned char TBYTE;` (ANSI)` |
| **TCHAR** | A WCHAR if UNICODE is defined, a CHAR otherwise.<br>`typedef wchar TCHAR; (UNICODE) `typedef char TCHAR;` (ANSI)` |
| **UCHAR** | An unsigned CHAR.<br>`typedef unsigned char UCHAR;` |
| **UHALF_PTR** | An unsigned HALF_PTR. Use within a structure that contains a pointer and two small fields.<br>`typedef unsigned short UHALF_PTR;` (32-bit) typedef unsigned int UHALF_PTR; (64-bit) |
| **UINT** | An unsigned INT. The range is 0 through 4294967295 decimal.<br>`typedef uint UINT;` |
| **UINT_PTR** | An unsigned INT_PTR.<br>`typedef unsigned int UINT_PTR; (32-bit) typedef unsigned __int64 UINT_PTR; (64-bit)` |
| **UINT8** | An unsigned INT8.<br>`typedef unsigned char UINT8;` |
| **UINT16** | An unsigned INT16.<br>`typedef unsigned short UINT16;` |
| **UINT32** | An unsigned INT32. The range is 0 through 4294967295 decimal.<br>`typedef unsigned int UINT32;` |
| **UINT64** | An unsigned INT64. The range is 0 through 18446744073709551615 decimal.<br>`typedef unsigned __int64 UINT64;` |
| **ULONG** | An unsigned LONG. The range is 0 through 4294967295 decimal.<br>`typedef ulong ULONG;` |
| **ULONGLONG** | A 64-bit unsigned integer. The range is 0 through 18446744073709551615 decimal.<br>`typedef unsigned __int64 ULONGLONG;` |
| **ULONG_PTR** | An unsigned LONG_PTR.<br>`typedef unsigned long ULONG_PTR (32-bit) typedef unsigned __int64 ULONG_PTR; (64-bit)` |
| **ULONG32** | An unsigned LONG32. The range is 0 through 4294967295 decimal.<br>`typedef unsigned int ULONG32;` |
| **ULONG64** | An unsigned LONG64. The range is 0 through 18446744073709551615 decimal.<br>`typedef unsigned __int64 ULONG64;` |
| **UNICODE_STRING** | A Unicode string.<br>`typedef struct _UNICODE_STRING` {<br>  `USHORT  Length;`<br>  `USHORT  MaximumLength;`<br>`  PWSTR  Buffer`;<br>`} UNICODE_STRING;`<br>`typedef UNICODE_STRING *PUNICODE_STRING;`<br>`typedef const UNICODE_STRING *PCUNICODE_STRING;` |
| **USHORT** | An unsigned SHORT. The range is 0 through 65535 decimal.<br>`typedef unsigned short USHORT;` |
| **USN** | An update sequence number (USN).<br>`typedef LONGLONG USN;` |
| **VOID** | Any type.<br>`typedef void VOID;` |
| **WCHAR** | A 16-bit Unicode character.<br>`typedef wchar WCHAR;` |
| **WINAPI** | The calling convention for system functions.<br>`#define WINAPI stdcall (32-bit) #define WINAPI ms64 (64-bit)` |
| **WORD** | A 16-bit unsigned integer. The range is 0 through 65535 decimal.<br>`typedef word WORD;` |
| **WPARAM** | A message parameter.<br>`typedef UINT_PTR WPARAM;` |
