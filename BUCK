posix_exported_headers = subdir_glob([
  ('UnitTest++', 'Posix/**/*.h'),
])

posix_sources = glob([
  'UnitTest++/Posix/**/*.cpp',
])

windows_exported_headers = subdir_glob([
  ('UnitTest++', 'Win32/**/*.h'),
])

windows_sources = glob([
  'UnitTest++/Win32/**/*.cpp',
])

cxx_library(
  name = 'unittest-cpp',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'UnitTest++/*.h'),
  ]),
  exported_platform_headers = [
    ('default', posix_exported_headers),
    ('^macos.*', posix_exported_headers),
    ('^linux.*', posix_exported_headers),
    ('^windows.*', windows_exported_headers),
  ],
  srcs = glob([
    'UnitTest++/*.cpp',
  ]),
  platform_srcs = [
    ('default', posix_sources),
    ('^macos.*', posix_sources),
    ('^linux.*', posix_sources),
    ('^windows.*', windows_sources),
  ],
  visibility = [
    'PUBLIC',
  ],
)
