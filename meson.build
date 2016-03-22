project('proxy-libintl', 'c',
  version : '1',
  meson_version : '>= 0.27.0',
  default_options : [ 'warning_level=1',
                      'c_std=gnu99',
                      'buildtype=debugoptimized' ])

install_headers('libintl.h')

libintl = library('intl',
  'libintl.c',
  c_args: ['-DSTUB_ONLY'],
  install : true,
)
