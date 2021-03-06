# Copyright (c) 2012 CNRS
# Author: Florent Lamiraux
#
# This file is part of hpp-corbaserver.
# hpp-corbaserver is free software: you can redistribute it
# and/or modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation, either version
# 3 of the License, or (at your option) any later version.
#
# hpp-corbaserver is distributed in the hope that it will be
# useful, but WITHOUT ANY WARRANTY; without even the implied warranty
# of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# General Lesser Public License for more details.  You should have
# received a copy of the GNU Lesser General Public License along with
# hpp-corbaserver.  If not, see
# <http://www.gnu.org/licenses/>.

# Requires at least CMake 2.6 to configure the package.
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

INCLUDE(cmake/base.cmake)

SET(PROJECT_NAME sot_hpp_msgs)
SET(PROJECT_DESCRIPTION "")
SET(PROJECT_URL "")
SET(PROJECT_VERSION "")

SET(INSTALL_DOCUMENTATION OFF)
SETUP_PROJECT()

find_package(catkin REQUIRED COMPONENTS sensor_msgs geometry_msgs message_generation)

add_service_files(FILES
    SetJointNames.srv
    SetString.srv
    PlugSot.srv
    GetInt.srv
    SetInt.srv
  )

add_message_files(FILES
    PlanningGoal.msg
    ReadSubPath.msg
    ProblemSolved.msg)

generate_messages(DEPENDENCIES std_msgs sensor_msgs geometry_msgs)

catkin_package(DEPENDS message_runtime)

SETUP_PROJECT_FINALIZE()
