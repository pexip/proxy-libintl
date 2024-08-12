project('proxy-libintl', 'c',
  version : '1',
  meson_version : '>= 0.27.0',
  default_options : [ 'warning_level=1',
                      'c_std=gnu99',
                      'buildtype=debugoptimized' ])

install_headers('libintl.h')

intl_lib = library('intl',
  'libintl.c',
  c_args: ['-DSTUB_ONLY'],
  install : true)

intl_dep = declare_dependency(link_with : intl_lib,
  include_directories : include_directories('.'))

pkgconf = configuration_data()
pkgconf.set('prefix', join_paths(get_option('prefix')))
pkgconf.set('exec_prefix', '${prefix}')
pkgconf.set('libdir', '${prefix}/@0@'.format(get_option('libdir')))
pkgconf.set('includedir', '${prefix}/@0@'.format(get_option('includedir')))
pkgconf.set('PACKAGE_VERSION', meson.project_version())
pkg_install_dir = join_paths(get_option('libdir'), 'pkgconfig')

configure_file(input : 'proxy-libintl.pc.in',
  output : 'proxy-libintl.pc',
  configuration : pkgconf,
  install : true,
  install_dir : pkg_install_dir)
