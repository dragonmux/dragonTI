# SPDX-License-Identifier: BSD-3-Clause

project(
	'dragonTI',
	'cpp',
	version: '0.0.1',
	meson_version: '>= 0.53'
)

targetChip = get_option('chip')
if targetChip == 'unknown'
	error('You must set the target Tiva-C to use')
endif

dragonTI_dep = declare_dependency(
	compile_args: '-D@0@'.format(targetChip.to_upper()),
	include_directories: include_directories('.'),
	link_args: ['-T', '@0@/@1@/linkerScript.ld'.format(meson.current_source_dir(), targetChip)]
)
