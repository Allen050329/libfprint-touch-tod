
examples = [
    'enroll',
    'identify',
    'img-capture',
    'manage-prints',
    'verify',
]

foreach example: examples
    executable(example,
        [ example + '.c', 'storage.c', 'utilities.c' ],
        dependencies: [
            libfprint_dep,
            glib_dep,
        ],
    )
endforeach

executable('cpp-test',
    'cpp-test.cpp',
    dependencies: libfprint_dep,
)

if installed_tests
    install_subdir('prints',
        install_dir: installed_tests_testdir)
endif

if get_option('tod')
    executable('tod-inspector',
        sources: 'tod-inspector.c',
        dependencies: [
            libfprint_dep,
            tod_dep,
        ],
    )
endif
