Import('RTT_ROOT')
Import('rtconfig')

from building import *
import os

PIXMAN_VERSION = '0.34.0'
PIXMAN_PATH = 'pixman-' + PIXMAN_VERSION
cwd = GetCurrentDir()
LOCAL_CCFLAGS = ""

# core source files 
src = Split('''
pixman.c
pixman-access.c
pixman-access-accessors.c
pixman-arm.c
pixman-bits-image.c
pixman-combine32.c
pixman-combine-float.c
pixman-conical-gradient.c
pixman-edge.c
pixman-edge-accessors.c
pixman-fast-path.c
pixman-general.c
pixman-gradient-walker.c
pixman-image.c
pixman-implementation.c
pixman-linear-gradient.c
pixman-matrix.c
pixman-mips.c
pixman-mmx.c
pixman-noop.c
pixman-ppc.c
pixman-radial-gradient.c
pixman-region16.c
pixman-region32.c
pixman-solid-fill.c
pixman-timer.c
pixman-trap.c
pixman-utils.c
pixman-x86.c
''')

if rtconfig.CROSS_TOOL == "keil":
    LOCAL_CCFLAGS += ' --gnu -W'

for item in range(len(src)):
    src[item] = PIXMAN_PATH + '/pixman/' + src[item]

CPPDEFINES  = ['PIXMAN_NO_TLS', 'PACKAGE']

CPPPATH = [cwd + '/' + PIXMAN_PATH + '/pixman']

group = DefineGroup('pixman', src, depend = ['PKG_USING_PIXMAN'], CPPDEFINES = CPPDEFINES, CPPPATH = CPPPATH, LOCAL_CCFLAGS = LOCAL_CCFLAGS)

Return('group')
