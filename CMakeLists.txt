# Note: Copra's Python bindings use the same CMake options as other projects but we don't need them
AddProject(copra
  GITHUB jrl-umi3218/copra
  GIT_TAG master
  CMAKE_ARGS -DPYTHON_BINDING:BOOL=OFF
  DEPENDS eigen-quadprog
)

AddProject(mc_state_observation
  GITHUB jrl-umi3218/mc_state_observation
  GIT_TAG main
  DEPENDS mc_rtc
)

AddCatkinProject(mc_plugin_footstep_plan_msgs
  GITHUB isri-aist/mc_plugin_footstep_plan_msgs
  GIT_TAG master
  WORKSPACE mc_rtc_ws
)

AddProject(lipm_walking_controller
  GITHUB arntanguy/lipm_walking_controller
  GIT_TAG rebase_stabilizer_ana
  DEPENDS copra mc_state_observation mc_plugin_footstep_plan_msgs
)
