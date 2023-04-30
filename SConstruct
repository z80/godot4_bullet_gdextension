#!/usr/bin/env python
import os
import sys

#import pdb
#pdb.set_trace()
with open( './aaa.txt', 'w' ) as f:
    f.write( "hello!" )


env = SConscript("godot_cpp/SConstruct")

# For reference:
# - CCFLAGS are compilation flags shared between C and C++
# - CFLAGS are for C-specific compilation flags
# - CXXFLAGS are for C++-specific compilation flags
# - CPPFLAGS are for pre-processor flags
# - CPPDEFINES are for pre-processor defines
# - LINKFLAGS are for linking flags

# tweak this if you want to use different folders, or more folders, to store your source code in.

thirdparty_dir = "src/thirdparty/bullet/"
bullet2_src = [
    # BulletCollision
    "BulletCollision/BroadphaseCollision/btAxisSweep3.cpp",
    "BulletCollision/BroadphaseCollision/btBroadphaseProxy.cpp",
    "BulletCollision/BroadphaseCollision/btCollisionAlgorithm.cpp",
    "BulletCollision/BroadphaseCollision/btDbvt.cpp",
    "BulletCollision/BroadphaseCollision/btDbvtBroadphase.cpp",
    "BulletCollision/BroadphaseCollision/btDispatcher.cpp",
    "BulletCollision/BroadphaseCollision/btOverlappingPairCache.cpp",
    "BulletCollision/BroadphaseCollision/btQuantizedBvh.cpp",
    "BulletCollision/BroadphaseCollision/btSimpleBroadphase.cpp",
    "BulletCollision/CollisionDispatch/btActivatingCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btBoxBoxCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btBox2dBox2dCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btBoxBoxDetector.cpp",
    "BulletCollision/CollisionDispatch/btCollisionDispatcher.cpp",
    "BulletCollision/CollisionDispatch/btCollisionDispatcherMt.cpp",
    "BulletCollision/CollisionDispatch/btCollisionObject.cpp",
    "BulletCollision/CollisionDispatch/btCollisionWorld.cpp",
    "BulletCollision/CollisionDispatch/btCollisionWorldImporter.cpp",
    "BulletCollision/CollisionDispatch/btCompoundCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btCompoundCompoundCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btConvexConcaveCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btConvexConvexAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btConvexPlaneCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btConvex2dConvex2dAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btDefaultCollisionConfiguration.cpp",
    "BulletCollision/CollisionDispatch/btEmptyCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btGhostObject.cpp",
    "BulletCollision/CollisionDispatch/btHashedSimplePairCache.cpp",
    "BulletCollision/CollisionDispatch/btInternalEdgeUtility.cpp",
    "BulletCollision/CollisionDispatch/btManifoldResult.cpp",
    "BulletCollision/CollisionDispatch/btSimulationIslandManager.cpp",
    "BulletCollision/CollisionDispatch/btSphereBoxCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btSphereSphereCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btSphereTriangleCollisionAlgorithm.cpp",
    "BulletCollision/CollisionDispatch/btUnionFind.cpp",
    "BulletCollision/CollisionDispatch/SphereTriangleDetector.cpp",
    "BulletCollision/CollisionShapes/btBoxShape.cpp",
    "BulletCollision/CollisionShapes/btBox2dShape.cpp",
    "BulletCollision/CollisionShapes/btBvhTriangleMeshShape.cpp",
    "BulletCollision/CollisionShapes/btCapsuleShape.cpp",
    "BulletCollision/CollisionShapes/btCollisionShape.cpp",
    "BulletCollision/CollisionShapes/btCompoundShape.cpp",
    "BulletCollision/CollisionShapes/btConcaveShape.cpp",
    "BulletCollision/CollisionShapes/btConeShape.cpp",
    "BulletCollision/CollisionShapes/btConvexHullShape.cpp",
    "BulletCollision/CollisionShapes/btConvexInternalShape.cpp",
    "BulletCollision/CollisionShapes/btConvexPointCloudShape.cpp",
    "BulletCollision/CollisionShapes/btConvexPolyhedron.cpp",
    "BulletCollision/CollisionShapes/btConvexShape.cpp",
    "BulletCollision/CollisionShapes/btConvex2dShape.cpp",
    "BulletCollision/CollisionShapes/btConvexTriangleMeshShape.cpp",
    "BulletCollision/CollisionShapes/btCylinderShape.cpp",
    "BulletCollision/CollisionShapes/btEmptyShape.cpp",
    "BulletCollision/CollisionShapes/btHeightfieldTerrainShape.cpp",
    "BulletCollision/CollisionShapes/btMiniSDF.cpp",
    "BulletCollision/CollisionShapes/btMinkowskiSumShape.cpp",
    "BulletCollision/CollisionShapes/btMultimaterialTriangleMeshShape.cpp",
    "BulletCollision/CollisionShapes/btMultiSphereShape.cpp",
    "BulletCollision/CollisionShapes/btOptimizedBvh.cpp",
    "BulletCollision/CollisionShapes/btPolyhedralConvexShape.cpp",
    "BulletCollision/CollisionShapes/btScaledBvhTriangleMeshShape.cpp",
    "BulletCollision/CollisionShapes/btSdfCollisionShape.cpp",
    "BulletCollision/CollisionShapes/btShapeHull.cpp",
    "BulletCollision/CollisionShapes/btSphereShape.cpp",
    "BulletCollision/CollisionShapes/btStaticPlaneShape.cpp",
    "BulletCollision/CollisionShapes/btStridingMeshInterface.cpp",
    "BulletCollision/CollisionShapes/btTetrahedronShape.cpp",
    "BulletCollision/CollisionShapes/btTriangleBuffer.cpp",
    "BulletCollision/CollisionShapes/btTriangleCallback.cpp",
    "BulletCollision/CollisionShapes/btTriangleIndexVertexArray.cpp",
    "BulletCollision/CollisionShapes/btTriangleIndexVertexMaterialArray.cpp",
    "BulletCollision/CollisionShapes/btTriangleMesh.cpp",
    "BulletCollision/CollisionShapes/btTriangleMeshShape.cpp",
    "BulletCollision/CollisionShapes/btUniformScalingShape.cpp",
    "BulletCollision/Gimpact/btContactProcessing.cpp",
    "BulletCollision/Gimpact/btGenericPoolAllocator.cpp",
    "BulletCollision/Gimpact/btGImpactBvh.cpp",
    "BulletCollision/Gimpact/btGImpactCollisionAlgorithm.cpp",
    "BulletCollision/Gimpact/btGImpactQuantizedBvh.cpp",
    "BulletCollision/Gimpact/btGImpactShape.cpp",
    "BulletCollision/Gimpact/btTriangleShapeEx.cpp",
    "BulletCollision/Gimpact/gim_box_set.cpp",
    "BulletCollision/Gimpact/gim_contact.cpp",
    "BulletCollision/Gimpact/gim_memory.cpp",
    "BulletCollision/Gimpact/gim_tri_collision.cpp",
    "BulletCollision/NarrowPhaseCollision/btContinuousConvexCollision.cpp",
    "BulletCollision/NarrowPhaseCollision/btConvexCast.cpp",
    "BulletCollision/NarrowPhaseCollision/btGjkConvexCast.cpp",
    "BulletCollision/NarrowPhaseCollision/btGjkEpa2.cpp",
    "BulletCollision/NarrowPhaseCollision/btGjkEpaPenetrationDepthSolver.cpp",
    "BulletCollision/NarrowPhaseCollision/btGjkPairDetector.cpp",
    "BulletCollision/NarrowPhaseCollision/btMinkowskiPenetrationDepthSolver.cpp",
    "BulletCollision/NarrowPhaseCollision/btPersistentManifold.cpp",
    "BulletCollision/NarrowPhaseCollision/btRaycastCallback.cpp",
    "BulletCollision/NarrowPhaseCollision/btSubSimplexConvexCast.cpp",
    "BulletCollision/NarrowPhaseCollision/btVoronoiSimplexSolver.cpp",
    "BulletCollision/NarrowPhaseCollision/btPolyhedralContactClipping.cpp",
    # BulletDynamics
    "BulletDynamics/Character/btKinematicCharacterController.cpp",
    "BulletDynamics/ConstraintSolver/btConeTwistConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btContactConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btFixedConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btGearConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btGeneric6DofConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btGeneric6DofSpringConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btGeneric6DofSpring2Constraint.cpp",
    "BulletDynamics/ConstraintSolver/btHinge2Constraint.cpp",
    "BulletDynamics/ConstraintSolver/btHingeConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btPoint2PointConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btSequentialImpulseConstraintSolver.cpp",
    "BulletDynamics/ConstraintSolver/btSequentialImpulseConstraintSolverMt.cpp",
    "BulletDynamics/ConstraintSolver/btBatchedConstraints.cpp",
    "BulletDynamics/ConstraintSolver/btNNCGConstraintSolver.cpp",
    "BulletDynamics/ConstraintSolver/btSliderConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btSolve2LinearConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btTypedConstraint.cpp",
    "BulletDynamics/ConstraintSolver/btUniversalConstraint.cpp",
    "BulletDynamics/Dynamics/btDiscreteDynamicsWorld.cpp",
    "BulletDynamics/Dynamics/btDiscreteDynamicsWorldMt.cpp",
    "BulletDynamics/Dynamics/btSimulationIslandManagerMt.cpp",
    "BulletDynamics/Dynamics/btRigidBody.cpp",
    "BulletDynamics/Dynamics/btSimpleDynamicsWorld.cpp",
    # "BulletDynamics/Dynamics/Bullet-C-API.cpp",
    "BulletDynamics/Vehicle/btRaycastVehicle.cpp",
    "BulletDynamics/Vehicle/btWheelInfo.cpp",
    "BulletDynamics/Featherstone/btMultiBody.cpp",
    "BulletDynamics/Featherstone/btMultiBodyConstraint.cpp",
    "BulletDynamics/Featherstone/btMultiBodyConstraintSolver.cpp",
    "BulletDynamics/Featherstone/btMultiBodyDynamicsWorld.cpp",
    "BulletDynamics/Featherstone/btMultiBodyFixedConstraint.cpp",
    "BulletDynamics/Featherstone/btMultiBodyGearConstraint.cpp",
    "BulletDynamics/Featherstone/btMultiBodyJointLimitConstraint.cpp",
    "BulletDynamics/Featherstone/btMultiBodyJointMotor.cpp",
    "BulletDynamics/Featherstone/btMultiBodyMLCPConstraintSolver.cpp",
    "BulletDynamics/Featherstone/btMultiBodyPoint2Point.cpp",
    "BulletDynamics/Featherstone/btMultiBodySliderConstraint.cpp",
    "BulletDynamics/Featherstone/btMultiBodySphericalJointLimit.cpp",
    "BulletDynamics/Featherstone/btMultiBodySphericalJointMotor.cpp",
    "BulletDynamics/MLCPSolvers/btDantzigLCP.cpp",
    "BulletDynamics/MLCPSolvers/btMLCPSolver.cpp",
    "BulletDynamics/MLCPSolvers/btLemkeAlgorithm.cpp",
    # BulletInverseDynamics
    # -- Unused for now so not included.
    # BulletSoftBody
    "BulletSoftBody/btSoftBody.cpp",
    "BulletSoftBody/btSoftBodyConcaveCollisionAlgorithm.cpp",
    "BulletSoftBody/btSoftBodyHelpers.cpp",
    "BulletSoftBody/btSoftBodyRigidBodyCollisionConfiguration.cpp",
    "BulletSoftBody/btSoftRigidCollisionAlgorithm.cpp",
    "BulletSoftBody/btSoftRigidDynamicsWorld.cpp",
    "BulletSoftBody/btSoftMultiBodyDynamicsWorld.cpp",
    "BulletSoftBody/btSoftSoftCollisionAlgorithm.cpp",
    "BulletSoftBody/btDefaultSoftBodySolver.cpp",
    "BulletSoftBody/btDeformableBackwardEulerObjective.cpp",
    "BulletSoftBody/btDeformableBodySolver.cpp",
    "BulletSoftBody/btDeformableMultiBodyConstraintSolver.cpp",
    "BulletSoftBody/btDeformableContactProjection.cpp",
    "BulletSoftBody/btDeformableMultiBodyDynamicsWorld.cpp",
    "BulletSoftBody/btDeformableContactConstraint.cpp",
    "BulletSoftBody/BulletReducedDeformableBody/btReducedDeformableBody.cpp",
    "BulletSoftBody/BulletReducedDeformableBody/btReducedDeformableBodyHelpers.cpp",
    "BulletSoftBody/BulletReducedDeformableBody/btReducedDeformableBodySolver.cpp",
    "BulletSoftBody/BulletReducedDeformableBody/btReducedDeformableContactConstraint.cpp",
    "BulletSoftBody/poly34.cpp",
    # LinearMath
    "LinearMath/btAlignedAllocator.cpp",
    "LinearMath/btConvexHull.cpp",
    "LinearMath/btConvexHullComputer.cpp",
    "LinearMath/btGeometryUtil.cpp",
    "LinearMath/btPolarDecomposition.cpp",
    "LinearMath/btQuickprof.cpp",
    "LinearMath/btReducedVector.cpp",
    "LinearMath/btSerializer.cpp",
    "LinearMath/btSerializer64.cpp",
    "LinearMath/btThreads.cpp",
    "LinearMath/btVector3.cpp",
    "LinearMath/TaskScheduler/btTaskScheduler.cpp",
    "LinearMath/TaskScheduler/btThreadSupportPosix.cpp",
    "LinearMath/TaskScheduler/btThreadSupportWin32.cpp",
]

thirdparty_sources = [thirdparty_dir + file for file in bullet2_src]
sources = Glob("src/modules/bullet/*.cpp")
sources = sources + thirdparty_sources

#env.Prepend(CPPPATH=["godot_cpp/include/godot_cpp"])
env.Append(CPPPATH=[thirdparty_dir, "src/modules/bullet"])

env.Append(CPPDEFINES=["BT_USE_OLD_DAMPING_METHOD", "BT_THREADSAFE"])

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
