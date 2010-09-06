AddOption('--prefix', 
    dest='prefix', 
    type='string', 
    nargs=1, 
    action='store', 
    metavar='DIR', 
    help='installation prefix', default="/usr/local")
env = Environment(PREFIX = GetOption('prefix'), tools = ["default", "packaging"]) 

liblinenoise_so = env.SharedLibrary('linenoise', ['linenoise.c'])

env.Install("$PREFIX/lib", liblinenoise_so)
env.Install("$PREFIX/include", "linenoise.h")
env.Package(NAME      	= 'liblinenoise',
        PACKAGEROOT 	= 'dist',
        VERSION        	= '1.0',
        PACKAGETYPE    	= 'targz')
env.Alias("install", "$PREFIX")
