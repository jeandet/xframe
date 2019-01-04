project('xframe', 'cpp', version:'0.1.0', license:'BSD-3-Clause', default_options : ['warning_level=3', 'cpp_std=c++14'])

xframe_dependencies = []
xframe_cpp_arg = []

xframe_dependencies+=[
  dependency('xtl', version:'>=0.5.1', fallback : ['xtl', 'xtl_dep']),
  dependency('xtensor', version:'>=0.19.1', fallback : ['xtensor', 'xtensor_dep'])
]


xframe_dep = declare_dependency(include_directories:include_directories('include'), dependencies:xframe_dependencies, compile_args:xframe_cpp_arg)

install_headers([
 'include/xframe/xvariable.hpp',
 'include/xframe/xaxis_variant.hpp',
 'include/xframe/xframe_expression.hpp',
 'include/xframe/xaxis_meta.hpp',
 'include/xframe/xvariable_scalar.hpp',
 'include/xframe/xvector_variant.hpp',
 'include/xframe/xframe_config.hpp',
 'include/xframe/xaxis_default.hpp',
 'include/xframe/xdynamic_variable.hpp',
 'include/xframe/xvariable_assign.hpp',
 'include/xframe/xaxis_label_slice.hpp',
 'include/xframe/xaxis.hpp',
 'include/xframe/xreindex_data.hpp',
 'include/xframe/xvariable_meta.hpp',
 'include/xframe/xaxis_view.hpp',
 'include/xframe/xselecting.hpp',
 'include/xframe/xvariable_function.hpp',
 'include/xframe/xcoordinate.hpp',
 'include/xframe/xsequence_view.hpp',
 'include/xframe/xcoordinate_base.hpp',
 'include/xframe/xaxis_math.hpp',
 'include/xframe/xaxis_expression_leaf.hpp',
 'include/xframe/xvariable_view.hpp',
 'include/xframe/xcoordinate_view.hpp',
 'include/xframe/xaxis_base.hpp',
 'include/xframe/xvariable_math.hpp',
 'include/xframe/xreindex_view.hpp',
 'include/xframe/xvariable_base.hpp',
 'include/xframe/xaxis_function.hpp',
 'include/xframe/xio.hpp',
 'include/xframe/xvariable_masked_view.hpp',
 'include/xframe/xdynamic_variable_impl.hpp',
 'include/xframe/xnamed_axis.hpp',
 'include/xframe/xcoordinate_system.hpp',
 'include/xframe/xaxis_index_slice.hpp',
 'include/xframe/xframe_trace.hpp',
 'include/xframe/xdimension.hpp',
 'include/xframe/xaxis_scalar.hpp',
 'include/xframe/xframe_utils.hpp',
 'include/xframe/xcoordinate_chain.hpp'],
 subdir:'xframe'
)

pkgc = import('pkgconfig')
pkgc.generate(name: 'xframe',
    version: meson.project_version(),
    description: 'C++ dataframe'
)


tests_sources = [
 'test/main.cpp',
 'test/test_xaxis.cpp',
 'test/test_xaxis_default.cpp',
 'test/test_xaxis_function.cpp',
 'test/test_xaxis_variant.cpp',
 'test/test_xaxis_view.cpp',
 'test/test_xcoordinate.cpp',
 'test/test_xcoordinate_chain.cpp',
 'test/test_xcoordinate_view.cpp',
 'test/test_xdimension.cpp',
 'test/test_xdynamic_variable.cpp',
 'test/test_xframe_utils.cpp',
 'test/test_xnamed_axis.cpp',
 'test/test_xreindex_view.cpp',
 'test/test_xsequence_view.cpp',
 'test/test_xvariable.cpp',
 'test/test_xvariable_assign.cpp',
 'test/test_xvariable_function.cpp',
 'test/test_xvariable_masked_view.cpp',
 'test/test_xvariable_math.cpp',
 'test/test_xvariable_noalias.cpp',
 'test/test_xvariable_scalar.cpp',
 'test/test_xvariable_view.cpp',
 'test/test_xvariable_view_assign.cpp',
 'test/test_xvector_variant.cpp'
 ]

if get_option('BUILD_TESTS')
  gtest_dep = dependency('gtest', main : true, fallback : ['gtest', 'gtest_dep'])
  test_exe = executable('xframe-test', tests_sources, dependencies:[xframe_dep, gtest_dep])
  test('xframe-test', test_exe)
endif