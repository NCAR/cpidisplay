# -*- python -*-

import os

umask = os.umask(0o002)
env = Environment(platform = 'posix',ENV= os.environ)
env['JLOCAL'] = os.environ['JLOCAL']

env.Command('cpidisplay.sav', ['src/cpidisplay.pro', 'src/cpiread.pro'], 'cd src && ( echo .compile cpidisplay ; echo .compile cpiread ; echo resolve_all ; echo \'save, /routines, filename="../cpidisplay.sav"\' ) | idl')


# Targets are only to install files.
Alias('install', env.Install('$JLOCAL/bin', 'cpidisplay'))
Alias('install', env.Install('$JLOCAL/idl/lib/cpi', 'cpidisplay.sav'))
Alias('install', env.Install('/net/ftp/pub/archive/RAF-src', 'cpidisplay.sav'))
