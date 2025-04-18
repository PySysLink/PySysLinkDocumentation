
.. _program_listing_file_PySysLinkBase_src_ContinuousAndOde_EulerForwardStepSolver.cpp:

Program Listing for File EulerForwardStepSolver.cpp
===================================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_ContinuousAndOde_EulerForwardStepSolver.cpp>` (``PySysLinkBase/src/ContinuousAndOde/EulerForwardStepSolver.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "EulerForwardStepSolver.h"
   #include <spdlog/spdlog.h>
   
   namespace PySysLinkBase
   {
       std::tuple<bool, std::vector<double>, double> EulerForwardStepSolver::SolveStep(std::function<std::vector<double>(std::vector<double>, double)> system, std::vector<double> states_0, double currentTime, double timeStep)
       {
           std::vector<double> gradient = system(states_0, currentTime);
           spdlog::get("default_pysyslink")->debug("Gradient size: {}", gradient.size());
           for (const auto& value: gradient)
           {
               spdlog::get("default_pysyslink")->debug(value);
           }
   
           std::vector<double> newStates(gradient.size(), 0.0);
           for (int i = 0; i < gradient.size(); i++)
           {
               newStates[i] = states_0[i] + gradient[i] * timeStep;
               spdlog::get("default_pysyslink")->debug("New state {}: {}", i, newStates[i]);
   
           }
           return {true, newStates, timeStep};
       }
   
   } // namespace PySysLinkBase
