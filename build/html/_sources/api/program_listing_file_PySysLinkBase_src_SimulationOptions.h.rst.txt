
.. _program_listing_file_PySysLinkBase_src_SimulationOptions.h:

Program Listing for File SimulationOptions.h
============================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_SimulationOptions.h>` (``PySysLinkBase/src/SimulationOptions.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_SIMULATION_OPTIONS
   #define SRC_SIMULATION_OPTIONS
   
   #include <vector>
   #include <utility>
   #include <string>
   #include <tuple>
   #include "ConfigurationValue.h"
   
   namespace PySysLinkBase
   {
       class SimulationOptions
       {
           public:
           SimulationOptions() = default;
   
           double startTime;
           double stopTime;
   
           bool runInNaturalTime = false;
           double naturalTimeSpeedMultiplier = 1.0;
   
           std::vector<std::tuple<std::string, std::string, int>> blockIdsInputOrOutputAndIndexesToLog = {};
   
           std::map<std::string, std::map<std::string, ConfigurationValue>> solversConfiguration;
       };
   } // namespace PySysLinkBase
   
   
   #endif /* SRC_SIMULATION_OPTIONS */
