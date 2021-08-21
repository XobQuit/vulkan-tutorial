#gen = generator(
#    glslc_prog,
#    output : '@PLAINNAME@.spv',
#    arguments : [ '@INPUT@', '-o', '@OUTPUT@' ]
#)

#spirv_files = gen.process('triangle.vert', 'triangle.frag')

shader_files = [ 'triangle.vert', 'triangle.frag' ]
#outfile = 'triangle.vert.spv'

#mytarget = custom_target(
#  'shaders',
#  output : ['@BASENAME@.spv'],
#  input : shader_files,
#  command : [glslc_prog, '@INPUT@', '-o', '@OUTPUT@'],
#  install : true,
#  install_dir : 'subdir'
#)

shader_targets = []
foreach s : shader_files
    shader_targets += custom_target(
        '@0@.spv'.format(s),
        command : [glslc_prog, '@INPUT@', '-o', '@OUTPUT@'],
        input : s, 
        output : '@PLAINNAME@.spv',
        build_by_default: true
    )
endforeach
