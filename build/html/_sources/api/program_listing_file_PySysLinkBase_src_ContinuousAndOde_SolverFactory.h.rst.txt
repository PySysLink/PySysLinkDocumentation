
.. _program_listing_file_PySysLinkBase_src_ContinuousAndOde_SolverFactory.h:

Program Listing for File SolverFactory.h
========================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_ContinuousAndOde_SolverFactory.h>` (``PySysLinkBase/src/ContinuousAndOde/SolverFactory.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_CONTINUOUS_AND_ODE_SOLVER_FACTORY
   #define SRC_CONTINUOUS_AND_ODE_SOLVER_FACTORY
   
   #include <memory>
   #include "IOdeStepSolver.h"
   #include <map>
   #include "../ConfigurationValue.h"
   
   namespace PySysLinkBase
   {
       class SolverFactory
       {
           public:
               static std::shared_ptr<IOdeStepSolver> CreateOdeStepSolver(std::map<std::string, ConfigurationValue> solverConfiguration);
       };
   } // namespace PySysLinkBase
   
   
   #endif /* SRC_CONTINUOUS_AND_ODE_SOLVER_FACTORY */
