src = files(
    'src/icons/QlementineIcons.cpp',
)
qrc_files = files(
    'resources/icons/12/qlementine_icons_12_action.qrc',
    'resources/icons/12/qlementine_icons_12_brand.qrc',
    'resources/icons/12/qlementine_icons_12_misc.qrc',
    'resources/icons/12/qlementine_icons_12_navigation.qrc',
    'resources/icons/12/qlementine_icons_12_shape.qrc',
    'resources/icons/12/qlementine_icons_12_software.qrc',
    'resources/icons/16/qlementine_icons_16_action.qrc',
    'resources/icons/16/qlementine_icons_16_audio.qrc',
    'resources/icons/16/qlementine_icons_16_brand.qrc',
    'resources/icons/16/qlementine_icons_16_document.qrc',
    'resources/icons/16/qlementine_icons_16_file.qrc',
    'resources/icons/16/qlementine_icons_16_food.qrc',
    'resources/icons/16/qlementine_icons_16_hardware.qrc',
    'resources/icons/16/qlementine_icons_16_instrument.qrc',
    'resources/icons/16/qlementine_icons_16_media.qrc',
    'resources/icons/16/qlementine_icons_16_misc.qrc',
    'resources/icons/16/qlementine_icons_16_navigation.qrc',
    'resources/icons/16/qlementine_icons_16_page.qrc',
    'resources/icons/16/qlementine_icons_16_shape.qrc',
    'resources/icons/16/qlementine_icons_16_shopping.qrc',
    'resources/icons/16/qlementine_icons_16_software.qrc',
    'resources/icons/16/qlementine_icons_16_text.qrc',
    'resources/icons/24/qlementine_icons_24_action.qrc',
    'resources/icons/24/qlementine_icons_24_brand.qrc',
    'resources/icons/24/qlementine_icons_24_document.qrc',
    'resources/icons/24/qlementine_icons_24_file.qrc',
    'resources/icons/24/qlementine_icons_24_hardware.qrc',
    'resources/icons/24/qlementine_icons_24_instrument.qrc',
    'resources/icons/24/qlementine_icons_24_media.qrc',
    'resources/icons/24/qlementine_icons_24_misc.qrc',
    'resources/icons/24/qlementine_icons_24_navigation.qrc',
    'resources/icons/24/qlementine_icons_24_shape.qrc',
    'resources/icons/24/qlementine_icons_24_shopping.qrc',
    'resources/icons/32/qlementine_icons_32_file.qrc',
    'resources/icons/32/qlementine_icons_32_hardware.qrc',
    'resources/icons/32/qlementine_icons_32_misc.qrc',
    'resources/icons/32/qlementine_icons_32_shape.qrc',
)

resources = qt6.compile_resources(sources: [qrc_files])

include = include_directories('include')

qlementine_icons_lib = library(
    'qlementine-icons',
    sources: [src, resources],
    include_directories: [include],
    dependencies: [qt_dep],
    install: true,
)

qlementine_icons_dep = declare_dependency(
    link_with: qlementine_icons_lib,
    include_directories: include,
)

install_subdir('include', install_dir: get_option('includedir'))

pkg = import('pkgconfig')
pkg.generate(
    name: 'qlementine-icons',
    description: 'Qlementine icon library',
    version: meson.project_version(),
    libraries: qlementine_icons_lib,
    subdirs: 'oclero/qlementine/icons',
)