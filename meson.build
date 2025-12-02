project('archland-settings',
  version: '1.0.0',
  license: 'MIT',
  meson_version: '>= 0.59.0',
)

# Dependencies (required at runtime, checked at build time on Arch)
# These are script-based dependencies, so we just document them
# The PKGBUILD handles actual dependency installation

# Directories
prefix = get_option('prefix')
bindir = prefix / get_option('bindir')
datadir = prefix / get_option('datadir')
applicationsdir = datadir / 'applications'
iconsdir = datadir / 'icons' / 'hicolor'

# Install the main script
install_data(
  'archland-settings',
  install_dir: bindir,
  install_mode: 'rwxr-xr-x',
)

# Install desktop file
install_data(
  'data' / 'org.archland.Settings.desktop',
  install_dir: applicationsdir,
)

# Install icons
install_data(
  'data' / 'icons' / 'hicolor' / 'scalable' / 'apps' / 'org.archland.Settings.svg',
  install_dir: iconsdir / 'scalable' / 'apps',
)

install_data(
  'data' / 'icons' / 'hicolor' / '48x48' / 'apps' / 'org.archland.Settings.png',
  install_dir: iconsdir / '48x48' / 'apps',
)

install_data(
  'data' / 'icons' / 'hicolor' / '128x128' / 'apps' / 'org.archland.Settings.png',
  install_dir: iconsdir / '128x128' / 'apps',
)

# Update icon cache
gnome = import('gnome')
gnome.post_install(
  gtk_update_icon_cache: true,
  update_desktop_database: true,
)
