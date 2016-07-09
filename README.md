# XMath
Modified DirectXMath for cross-platform compiling

Tested on MSVC LinuxGCC OSXClang IOSClang AndroidGCC

##Todo
Completed column order matrix mathematics

##Sample predefines for including:

```cpp
#if defined(BUILD_ARCH_ARM)
#	if defined(__ARM_NEON) && BUILD_INTRINSICS_LEVEL > 0
#		define _XM_ARM_NEON_INTRINSICS_
#	else
#		define _XM_NO_INTRINSICS_
#	endif
#else
#	if BUILD_INTRINSICS_LEVEL > 0
#		define _XM_SSE_INTRINSICS_
#	endif
#	if BUILD_INTRINSICS_LEVEL > 1
#		define _XM_SSE3_INTRINSICS_
#		define _XM_SSE4_INTRINSICS_
#		define _XM_AVX_INTRINSICS_
#	endif
#	if BUILD_INTRINSICS_LEVEL > 2
#		define _XM_F16C_INTRINSICS_
#	endif
#endif
#if defined(VE_COMPILER_GCC) || defined(BUILD_PLATFORM_IOS)
#	define _XM_NO_CALL_CONVENTION_
#endif
#if defined(BUILD_PLATFORM_IOS) || defined(BUILD_PLATFORM_ANDROID)
#	define _XM_ARM_NEON_NO_ALIGN_
#endif
//#define _XM_NO_INTRINSICS_
#include "XMath/XMath.h"
```
