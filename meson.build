project('com.github.rajkumaar23.badgie', 'vala', 'c',
    version: '0.1.0'
)

gnome = import('gnome')
i18n = import('i18n')

add_project_arguments(
    '-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name()),
    language: 'c'
)

executable(
    meson.project_name(),
    'src/Application.vala',
    'src/MainWindow.vala',
    dependencies: [
        dependency('gtk+-3.0'),
        dependency('libsoup-2.4'),
        dependency('gee-0.8'),
        dependency('gdk-pixbuf-2.0')
    ],
    install : true
)

#Install our .desktop file so the Applications Menu will see it
install_data(
    join_paths('data', meson.project_name() + '.desktop'),
    install_dir: join_paths(get_option('datadir'), 'applications')
)
    
#Install our .appdata.xml file so AppCenter will see it
install_data(
    join_paths('data', meson.project_name() + '.appdata.xml'),
    install_dir: join_paths(get_option('datadir'), 'metainfo')
)
