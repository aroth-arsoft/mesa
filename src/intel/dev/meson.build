# Copyright © 2017 Intel Corporation

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

# TODO: android?

files_libintel_dev = files(
  'gen_debug.c',
  'gen_debug.h',
  'gen_device_info.c',
  'gen_device_info.h',
)

libintel_dev = static_library(
  ['intel_dev'],
  files_libintel_dev,
  include_directories : [inc_common, inc_intel, inc_include],
  c_args : [c_vis_args, no_override_init_args],
)

if with_tests
  test('gen_device_info_test',
       executable(
         'gen_device_info_test',
         'gen_device_info_test.c',
         include_directories : [inc_include, inc_src],
         link_with : libintel_dev,
       ),
       suite : ['intel'],
      )
endif
