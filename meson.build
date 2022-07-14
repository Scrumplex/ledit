project('ledit', 'c', 'cpp',
  default_options: [
    'cpp_std=c++17'
  ])

cppc = meson.get_compiler('cpp')

is_linux = host_machine.system() != 'windows' and host_machine.system() != 'darwin'

sources = [
  'src/glad.c',
  'src/la.cc',
  'src/main.cc'
]

glfw3_dep = dependency('glfw3')
freetype2_dep = dependency('freetype2')

fontconfig_dep = dependency('fontconfig', required: is_linux)
dl_dep = cppc.find_library('dl', required: is_linux)

executable('ledit', sources, dependencies: [glfw3_dep, freetype2_dep, fontconfig_dep, dl_dep])
