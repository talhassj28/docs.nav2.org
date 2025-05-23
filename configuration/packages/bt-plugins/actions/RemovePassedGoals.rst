.. _bt_remove_passed_goals_action:

RemovePassedGoals
=================

Looks over the input port ``goals`` and removes any point that the robot is in close proximity to or has recently passed.
This is used to cull goal points that have been passed from ``ComputePathThroughPoses`` to enable replanning to only the current task goals.

Input Ports
-----------

:radius:

  ====== =======
  Type   Default
  ------ -------
  double 0.5
  ====== =======

  Description
    The radius (m) in proximity to the viapoint for the BT node to remove from the list as having passed.

:robot_base_frame:

  ====== ===========
  Type   Default
  ------ -----------
  string "base_link"
  ====== ===========

  Description
    Robot base frame.

:input_goals:

  ==================== =======
  Type                 Default
  -------------------- -------
  nav_msgs::msg::Goals   N/A
  ==================== =======

  Description
    A vector of goals to check if it passed any in the current iteration.

:input_waypoint_statuses:

  =========================================== =======
  Type                                        Default
  ------------------------------------------- -------
  std::vector<nav2_msgs::msg::WaypointStatus>   N/A
  =========================================== =======

  Description
    Original waypoint_statuses to mark waypoint status from.

Output Ports
------------

:output_goals:

  ==================== =======
  Type                 Default
  -------------------- -------
  nav_msgs::msg::Goals   N/A
  ==================== =======

  Description
    A vector of goals with goals removed in proximity to the robot

:output_waypoint_statuses:

  =========================================== =======
  Type                                        Default
  ------------------------------------------- -------
  std::vector<nav2_msgs::msg::WaypointStatus>   N/A
  =========================================== =======

  Description
    Waypoint_statuses with passed waypoints marked.

Example
-------

.. code-block:: xml

  <RemovePassedGoals radius="0.6" input_goals="{goals}" output_goals="{goals}" input_waypoint_statuses="{waypoint_statuses}" output_waypoint_statuses="{waypoint_statuses}"/>
