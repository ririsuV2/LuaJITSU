This is a fork of LuaJIT that adds these operators: !=, !, && and || without removing vanilla ones.
All modifications are done in lexer (lj_lex.c).

## Example
```lua
local nah = !true
local meh = 0 != 1
local duh = true && false
local bruh = false || true
```

It also has Lua 5.2 compatibility enabled in msvcbuild.bat file,
if you want to disable it - open msvcbuild.bat and find the line at the top
that starts with @set LJCOMPILE=cl, and remove "/DLUAJIT_ENABLE_LUA52COMPAT" from it.

## Building with msvcbuild.bat
Navigate here: "YOUR VISUAL STUDIO DIRECTORY/VERSION/Community/VC/Auxiliary/Build"

(for me it's "C:/Program Files/Microsoft Visual Studio/2022/Community/VC/Auxiliary/Build")

Then find vcvars32.bat and vcvars64.bat here. Run the appropriate one depending
on if you want to build LuaJIT as x86 or x64, and then run msvcbuild.bat from the LuaJIT/src dir,
but in the same console you have run vcvars**.bat.

> **_NOTE:_**  To build LuaJIT statically (using msvcbuild.bat), type: msvcbuild.bat static

## Step by step for absolute beginners
- Run cmd.exe
- Type "YOUR VISUAL STUDIO DIRECTORY/VERSION/Community/VC/Auxiliary/Build/vcvars64.bat"
- Type "cd SOMELOCATION/luajit/src"
- Type "msvcbuild.bat" or "msvcbuild.bat static" if you want to build a static library (.lib) instead of dynamic one (.dll)

--------

LuaJIT is a Just-In-Time (JIT) compiler for the Lua programming language. It's homepage: https://luajit.org/

LuaJIT is Copyright (C) 2005-2023 Mike Pall.
LuaJIT is free software, released under the MIT license.
See full Copyright Notice in the COPYRIGHT file or in luajit.h.

Documentation for LuaJIT is available at the directory doc/luajit.html

💜