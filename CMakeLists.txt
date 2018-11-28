# cmake version
cmake_minimum_required(VERSION 3.2)
CMAKE_POLICY(SET CMP0054 NEW)

# name of the project
PROJECT(ODE)

# allow easier if-else syntax
SET(CMAKE_ALLOW_LOOSE_LOOP_CONSTRUCTS TRUE)

# output the system name
MESSAGE(STATUS "Configuring ODE for a ${CMAKE_SYSTEM} system")

set(ODE_HDR
ode/src/array.h
ode/src/collision_kernel.h
ode/src/collision_libccd.h
ode/src/collision_space_internal.h
ode/src/collision_std.h
ode/src/collision_transform.h
ode/src/collision_trimesh_colliders.h
ode/src/collision_trimesh_internal.h
ode/src/collision_util.h
ode/src/config.h
ode/src/error.h
ode/src/heightfield.h
ode/src/lcp.h
ode/src/mat.h
ode/src/matrix.h
ode/src/objects.h
ode/src/obstack.h
ode/src/odemath.h
ode/src/odeou.h
ode/src/odetls.h
ode/src/quickstep.h
ode/src/step.h
ode/src/threading_atomics_provs.h
ode/src/threading_base.h
ode/src/threading_fake_sync.h
ode/src/threading_impl.h
ode/src/threading_impl_posix.h
ode/src/threading_impl_templates.h
ode/src/threading_impl_win.h
ode/src/threadingutils.h
ode/src/typedefs.h
ode/src/util.h
)

set(ODE_SRC_CPP
ode/src/array.cpp
ode/src/box.cpp
ode/src/capsule.cpp
ode/src/collision_cylinder_box.cpp
ode/src/collision_cylinder_plane.cpp
ode/src/collision_cylinder_sphere.cpp
ode/src/collision_cylinder_trimesh.cpp
ode/src/collision_kernel.cpp
ode/src/collision_libccd.cpp
ode/src/collision_quadtreespace.cpp
ode/src/collision_sapspace.cpp
ode/src/collision_space.cpp
ode/src/collision_transform.cpp
ode/src/collision_trimesh_box.cpp
ode/src/collision_trimesh_ccylinder.cpp
ode/src/collision_trimesh_disabled.cpp
ode/src/collision_trimesh_distance.cpp
ode/src/collision_trimesh_gimpact.cpp
ode/src/collision_trimesh_opcode.cpp
ode/src/collision_trimesh_plane.cpp
ode/src/collision_trimesh_ray.cpp
ode/src/collision_trimesh_sphere.cpp
ode/src/collision_trimesh_trimesh.cpp
ode/src/collision_trimesh_trimesh_new.cpp
ode/src/collision_util.cpp
ode/src/convex.cpp
ode/src/cylinder.cpp
ode/src/error.cpp
ode/src/export-dif.cpp
ode/src/heightfield.cpp
ode/src/lcp.cpp
ode/src/mass.cpp
ode/src/mat.cpp
ode/src/matrix.cpp
ode/src/memory.cpp
ode/src/misc.cpp
ode/src/objects.cpp
ode/src/obstack.cpp
ode/src/ode.cpp
ode/src/odeinit.cpp
ode/src/odemath.cpp
ode/src/odeou.cpp
ode/src/odetls.cpp
ode/src/plane.cpp
ode/src/quickstep.cpp
ode/src/ray.cpp
ode/src/rotation.cpp
ode/src/sphere.cpp
ode/src/step.cpp
ode/src/threading_base.cpp
ode/src/threading_impl.cpp
ode/src/threading_pool_posix.cpp
ode/src/threading_pool_win.cpp
ode/src/timer.cpp
ode/src/util.cpp
)

set(ODE_SRC_C
ode/src/fastdot.c
ode/src/fastldlt.c
ode/src/fastlsolve.c
ode/src/fastltsolve.c
ode/src/nextafterf.c
)

set(OPCODE_SRC
  OPCODE/OPC_AABBCollider.cpp
  OPCODE/OPC_AABBCollider.h
  OPCODE/OPC_AABBTree.cpp
  OPCODE/OPC_AABBTree.h
  OPCODE/OPC_BaseModel.cpp
  OPCODE/OPC_BaseModel.h
  OPCODE/OPC_BoxBoxOverlap.h
  OPCODE/OPC_Collider.cpp
  OPCODE/OPC_Collider.h
  OPCODE/OPC_Common.cpp
  OPCODE/OPC_Common.h
  OPCODE/OPC_HybridModel.cpp
  OPCODE/OPC_HybridModel.h
  OPCODE/OPC_IceHook.h
  OPCODE/OPC_LSSAABBOverlap.h
  OPCODE/OPC_LSSCollider.cpp
  OPCODE/OPC_LSSCollider.h
  OPCODE/OPC_LSSTriOverlap.h
  OPCODE/OPC_MeshInterface.cpp
  OPCODE/OPC_MeshInterface.h
  OPCODE/OPC_Model.cpp
  OPCODE/OPC_Model.h
  OPCODE/OPC_OBBCollider.cpp
  OPCODE/OPC_OBBCollider.h
  OPCODE/OPC_OptimizedTree.cpp
  OPCODE/OPC_OptimizedTree.h
  OPCODE/OPC_Picking.cpp
  OPCODE/OPC_Picking.h
  OPCODE/OPC_PlanesAABBOverlap.h
  OPCODE/OPC_PlanesCollider.cpp
  OPCODE/OPC_PlanesCollider.h
  OPCODE/OPC_PlanesTriOverlap.h
  OPCODE/OPC_RayAABBOverlap.h
  OPCODE/OPC_RayCollider.cpp
  OPCODE/OPC_RayCollider.h
  OPCODE/OPC_RayTriOverlap.h
  OPCODE/OPC_Settings.h
  OPCODE/OPC_SphereAABBOverlap.h
  OPCODE/OPC_SphereCollider.cpp
  OPCODE/OPC_SphereCollider.h
  OPCODE/OPC_SphereTriOverlap.h
  OPCODE/OPC_TreeBuilders.cpp
  OPCODE/OPC_TreeBuilders.h
  OPCODE/OPC_TreeCollider.cpp
  OPCODE/OPC_TreeCollider.h
  OPCODE/OPC_TriBoxOverlap.h
  OPCODE/OPC_TriTriOverlap.h
  OPCODE/OPC_VolumeCollider.cpp
  OPCODE/OPC_VolumeCollider.h
  OPCODE/Opcode.cpp
  OPCODE/Opcode.h
  OPCODE/Stdafx.h
)

set(ODE_JOINTS 
ode/src/joints/amotor.cpp
ode/src/joints/amotor.h
ode/src/joints/ball.cpp
ode/src/joints/ball.h
ode/src/joints/contact.cpp
ode/src/joints/contact.h
ode/src/joints/dball.cpp
ode/src/joints/dball.h
ode/src/joints/dhinge.cpp
ode/src/joints/dhinge.h
ode/src/joints/fixed.cpp
ode/src/joints/fixed.h
ode/src/joints/hinge.cpp
ode/src/joints/hinge.h
ode/src/joints/hinge2.cpp
ode/src/joints/hinge2.h
ode/src/joints/joint.cpp
ode/src/joints/joint.h
ode/src/joints/joint_internal.h
ode/src/joints/joints.h
ode/src/joints/lmotor.cpp
ode/src/joints/lmotor.h
ode/src/joints/Makefile.am
ode/src/joints/Makefile.in
ode/src/joints/null.cpp
ode/src/joints/null.h
ode/src/joints/piston.cpp
ode/src/joints/piston.h
ode/src/joints/plane2d.cpp
ode/src/joints/plane2d.h
ode/src/joints/pr.cpp
ode/src/joints/pr.h
ode/src/joints/pu.cpp
ode/src/joints/pu.h
ode/src/joints/slider.cpp
ode/src/joints/slider.h
ode/src/joints/transmission.cpp
ode/src/joints/transmission.h
ode/src/joints/universal.cpp
ode/src/joints/universal.h
)

set(SRC_ICE
  OPCODE/Ice/IceAABB.cpp
  OPCODE/Ice/IceAABB.h
  OPCODE/Ice/IceAxes.h
  OPCODE/Ice/IceBoundingSphere.h
  OPCODE/Ice/IceContainer.cpp
  OPCODE/Ice/IceContainer.h
  OPCODE/Ice/IceFPU.h
  OPCODE/Ice/IceHPoint.cpp
  OPCODE/Ice/IceHPoint.h
  OPCODE/Ice/IceIndexedTriangle.cpp
  OPCODE/Ice/IceIndexedTriangle.h
  OPCODE/Ice/IceLSS.h
  OPCODE/Ice/IceMatrix3x3.cpp
  OPCODE/Ice/IceMatrix3x3.h
  OPCODE/Ice/IceMatrix4x4.cpp
  OPCODE/Ice/IceMatrix4x4.h
  OPCODE/Ice/IceMemoryMacros.h
  OPCODE/Ice/IceOBB.cpp
  OPCODE/Ice/IceOBB.h
  OPCODE/Ice/IcePairs.h
  OPCODE/Ice/IcePlane.cpp
  OPCODE/Ice/IcePlane.h
  OPCODE/Ice/IcePoint.cpp
  OPCODE/Ice/IcePoint.h
  OPCODE/Ice/IcePreprocessor.h
  OPCODE/Ice/IceRandom.cpp
  OPCODE/Ice/IceRandom.h
  OPCODE/Ice/IceRay.cpp
  OPCODE/Ice/IceRay.h
  OPCODE/Ice/IceRevisitedRadix.cpp
  OPCODE/Ice/IceRevisitedRadix.h
  OPCODE/Ice/IceSegment.cpp
  OPCODE/Ice/IceSegment.h
  OPCODE/Ice/IceTriangle.cpp
  OPCODE/Ice/IceTriangle.h
  OPCODE/Ice/IceTriList.h
  OPCODE/Ice/IceTypes.h
  OPCODE/Ice/IceUtils.cpp
  OPCODE/Ice/IceUtils.h
)

set(OU_SRC
ou/src/ou/atomic.cpp
ou/src/ou/customization.cpp
ou/src/ou/malloc.cpp
ou/src/ou/threadlocalstorage.cpp
)

source_group(ode_headers FILES ${ODE_HDR})
source_group(ode_src_cpp FILES ${ODE_SRC_CPP})
source_group(ode_src_c FILES ${ODE_SRC_C})

add_library(ode ${ODE_SRC_CPP} ${ODE_SRC_C} ${ODE_HDR} ${OPCODE_SRC} ${ODE_JOINTS} ${SRC_ICE} ${OU_SRC})
target_include_directories(ode PRIVATE . ${CMAKE_CURRENT_SOURCE_DIR}/include ${CMAKE_CURRENT_SOURCE_DIR}/ou/include  ${CMAKE_CURRENT_SOURCE_DIR}/OPCODE ${CMAKE_CURRENT_SOURCE_DIR}/ode/src ${CMAKE_CURRENT_SOURCE_DIR}/libccd/src)
target_compile_definitions(ode PRIVATE dDOUBLE=1 CCD_DOUBLE=1)

#add_executable(demo_cylvssphere ode/demo/demo_cylvssphere.cpp)
#target_include_directories(demo_cylvssphere PRIVATE . ${CMAKE_CURRENT_SOURCE_DIR}/include ${CMAKE_CURRENT_SOURCE_DIR}/ou/include  ${CMAKE_CURRENT_SOURCE_DIR}/OPCODE ${CMAKE_CURRENT_SOURCE_DIR}/libccd/src ${CMAKE_CURRENT_SOURCE_DIR}/ode/src/joints ${CMAKE_CURRENT_SOURCE_DIR}/OPCODE/Ice)
#target_compile_definitions(demo_cylvssphere PRIVATE dDOUBLE=1 CCD_DOUBLE=1)
#target_link_libraries(demo_cylvssphere PRIVATE ode)

