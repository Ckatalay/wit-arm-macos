# Wiimms ISO Tools - ARM64 Compatible

    ****************************************
    *    __            __ _ ___________    *
    *    \ \          / /| |____   ____|   *
    *     \ \        / / | |    | |        *
    *      \ \  /\  / /  | |    | |        *
    *       \ \/  \/ /   | |    | |        *
    *        \  /\  /    | |    | |        *
    *         \/  \/     |_|    |_|        *
    *                                      *
    *           Wiimms ISO Tools           *
    *         https://wit.wiimm.de/        *
    *                                      *
    ****************************************

## Overview

»Wiimms ISO Tools« is a set of command line tools to extract,
modify and create Wii and GameCube ISO images and WBFS containers.
Development started in 2009.

**This fork adds ARM64/Apple silicon compatibility** to the original project,
enabling the tools to build and run natively on Apple Silicon Macs and other ARM64 platforms.

See https://wit.wiimm.de/ for original project details, documentation and downloads.

## ARM64 Compatibility

This version includes the following enhancements for ARM64 platforms:

- **Memory Alignment Fixes**: Resolved ARM64-specific pointer alignment issues
- **Conditional Packed Attributes**: Smart structure packing that preserves binary compatibility while ensuring proper alignment
- **Apple Silicon Support**: Native compilation and execution on M1/M2/M3 Macs
- **Cross-Platform Build System**: Automatic detection and configuration for ARM64 vs x86 architectures

### Supported Platforms

- ✅ **Apple Silicon Macs** (M1, M2, M3+) - Native ARM64
- ✅ **Linux ARM64** - Native ARM64 
- ✅ **Linux x86/x86_64** - Original compatibility maintained
- ✅ **Windows x86/x86_64** - Original compatibility maintained
- ✅ **Other ARM64 platforms** - Should work with standard ARM64 toolchains

### Technical Details

The ARM64 compatibility layer includes:
- Conditional `DCLIB_PACKED_INTERNAL` attributes that disable struct packing for internal data structures on ARM64
- Preservation of `DCLIB_PACKED_FORMAT` for binary file format compatibility
- ARM64-specific compiler flags (`-fno-strict-aliasing`, `-Wno-address-of-packed-member`)
- Automatic architecture detection in the build system

## Building

```bash
cd project
make
```

The build system automatically detects ARM64 and applies the appropriate compatibility fixes.

<dl>
<dt>Note:</dt>
<dd>
This is a community fork focused on ARM64 compatibility.
The original project is maintained by Wiimm in a private SVN repository,
with official releases exported to the main repository.
</dd>

<dt>License:</dt>
<dd>
This program is free software;
you can redistribute it and/or modify it under the terms of the
GNU General Public License as published by the Free Software Foundation;
either version 2 of the License, or (at your option) any later version.

See file project/gpl-2.0.txt or http://www.gnu.org/licenses/gpl-2.0.txt for details.
</dd>

<dt>ARM64 Modifications:</dt>
<dd>
ARM64 compatibility modifications are released under the same GPL-2.0 license.
Original project copyright and design by Wiimm.
ARM64 compatibility layer added in 2025.
</dd>
</dl>

*Original project by Wiimm, 2009-2024*  
*ARM64 compatibility modifications by Çağatay Kağan Atalay, 2025*
