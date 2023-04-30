#!/usr/bin/env python
import os
import sys

#import pdb
#pdb.set_trace()

env = SConscript("godot_cpp/SConstruct")

# For reference:
# - CCFLAGS are compilation flags shared between C and C++
# - CFLAGS are for C-specific compilation flags
# - CXXFLAGS are for C++-specific compilation flags
# - CPPFLAGS are for pre-processor flags
# - CPPDEFINES are for pre-processor defines
# - LINKFLAGS are for linking flags

# tweak this if you want to use different folders, or more folders, to store your source code in.
env.Append(CPPPATH=["src/"])
sources = Glob("src/*.cpp")

#env.Append(CPPDEFINES = ['__BT_DISABLE_SSE__']) 

env.Append(CPPPATH=["src/thirdparty/bullet"])
#sources += Glob( "src/thirdparty/bullet/*.cpp" )

#env.Append(CPPPATH=["src/thirdparty/bullet/BulletCollision"])
sources += Glob( "src/thirdparty/bullet/BulletCollision/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletCollision/BroadphaseCollision"])
sources += Glob( "src/thirdparty/bullet/BulletCollision/BroadphaseCollision/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletCollision/CollisionDispatch"])
sources += Glob( "src/thirdparty/bullet/BulletCollision/CollisionDispatch/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletCollision/CollisionShapes"])
sources += Glob( "src/thirdparty/bullet/BulletCollision/CollisionShapes/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletCollision/Gimpact"])
sources += Glob( "src/thirdparty/bullet/BulletCollision/Gimpact/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletCollision/NarrowPhaseCollision"])
sources += Glob( "src/thirdparty/bullet/BulletCollision/NarrowPhaseCollision/*.cpp" )

#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics/Character"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/Character/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics/ConstraintSolver"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/ConstraintSolver/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics/Dynamics"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/Dynamics/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics/Featherstone"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/Featherstone/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics/MLCPSolvers"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/MLCPSolvers/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletDynamics/Vehicle"])
sources += Glob( "src/thirdparty/bullet/BulletDynamics/Vehicle/*.cpp" )

#env.Append(CPPPATH=["src/thirdparty/bullet/BulletSoftBody"])
sources += Glob( "src/thirdparty/bullet/BulletSoftBody/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/BulletSoftBody/BulletReducedDeformableBody"])
sources += Glob( "src/thirdparty/bullet/BulletSoftBody/BulletReducedDeformableBody/*.cpp" )

#env.Append(CPPPATH=["src/thirdparty/bullet/LinearMath"])
sources += Glob( "src/thirdparty/bullet/LinearMath/*.cpp" )
#env.Append(CPPPATH=["src/thirdparty/bullet/LinearMath/TaskScheduler"])
sources += Glob( "src/thirdparty/bullet/LinearMath/TaskScheduler/*.cpp" )


if env["platform"] == "macos":
    library = env.SharedLibrary(
        "demo/bin/libgdbullet.{}.{}.framework/libgdbullet.{}.{}".format(
            env["platform"], env["target"], env["platform"], env["target"]
        ),
        source=sources,
    )
else:
    library = env.SharedLibrary(
        "demo/bin/libgdbullet{}{}".format(env["suffix"], env["SHLIBSUFFIX"]),
        source=sources,
    )

Default(library)
