project(
	'dragonTI',
	'cpp',
	version: '0.0.1',
	meson_version: '>= 0.53'
)

targetChip = option('chip')
if targetChip == 'unknown'
	error('You must set the target Tiva-C to use')
endif

dragonTI_dep = declare_dependency(
	compile_args: '-D@0@'.format(targetChip.to_upper()),
	include_directories: include_directory('.'),
	link_args: ['-T', '@0@/@1@/linkerScript.ld'.format(meson.current_source_dir(), targetChip)]
)
