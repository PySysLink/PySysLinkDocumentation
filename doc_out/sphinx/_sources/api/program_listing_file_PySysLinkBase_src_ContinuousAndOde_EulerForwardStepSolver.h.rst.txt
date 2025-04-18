
.. _program_listing_file_PySysLinkBase_src_ContinuousAndOde_EulerForwardStepSolver.h:

Program Listing for File EulerForwardStepSolver.h
=================================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_ContinuousAndOde_EulerForwardStepSolver.h>` (``PySysLinkBase/src/ContinuousAndOde/EulerForwardStepSolver.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_EULER_FORWARD_STEP_SOLVER
   #define SRC_EULER_FORWARD_STEP_SOLVER
   
   
   #include <tuple>
   #include <vector>
   #include <functional>
   #include "IOdeStepSolver.h"
   
   namespace PySysLinkBase
   {
       class EulerForwardStepSolver : public IOdeStepSolver
       {
           public:
               virtual std::tuple<bool, std::vector<double>, double> SolveStep(std::function<std::vector<double>(std::vector<double>, double)> system, 
                                                                       std::vector<double> states_0, double currentTime, double timeStep);
               virtual bool IsJacobianNeeded() const 
               {
                   return false;
               }
               virtual std::tuple<bool, std::vector<double>, double> SolveStep(std::function<std::vector<double>(std::vector<double>, double)> systemDerivatives,
                                                                       std::function<std::vector<std::vector<double>>(std::vector<double>, double)> systemJacobian, 
                                                                       std::vector<double> states_0, double currentTime, double timeStep)
               {
                   throw std::runtime_error("Jacobian not needed");
               }
       };
   } // namespace PySysLinkBase
   
   #endif /* SRC_EULER_FORWARD_STEP_SOLVER */
