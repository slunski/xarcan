srcs = [
    'arcan.c',
    'arcaninit.c',
    'arcancvt.c',
]

arcan_dep = [
    common_dep,
		gbm_dep,
		libdrm_dep,
		epoxy_dep,
    dependency('arcan-shmif'),
		dependency('arcan-shmif-ext'),
    dependency('xcb'),
    dependency('xcb-shape'),
    dependency('xcb-render'),
    dependency('xcb-renderutil'),
    dependency('xcb-aux'),
    dependency('xcb-image'),
    dependency('xcb-icccm'),
    dependency('xcb-shm', version : '>=1.9.3'),
    dependency('xcb-keysyms'),
    dependency('xcb-randr'),
    dependency('xcb-xkb'),
    dependency('x11-xcb')
]

arcan_server = executable(
    'Xarcan',
    srcs,
    include_directories: [
        inc,
        include_directories('../src')
    ],
    dependencies: arcan_dep,
    link_with: [
        libxserver_main,
        kdrive,
				glamor,
        libxserver_fb,
        libxserver,
        libxserver_config,
        libxserver_xkb_stubs,
        libxserver_xi_stubs,
        libxserver_glx,
        libglxvnd
    ],
    install: true,
)
