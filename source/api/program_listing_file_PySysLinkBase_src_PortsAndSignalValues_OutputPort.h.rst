
.. _program_listing_file_PySysLinkBase_src_PortsAndSignalValues_OutputPort.h:

Program Listing for File OutputPort.h
=====================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortsAndSignalValues_OutputPort.h>` (``PySysLinkBase/src/PortsAndSignalValues/OutputPort.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PORTS_AND_SIGNAL_VALUES_OUTPUT_PORT
   #define SRC_PORTS_AND_SIGNAL_VALUES_OUTPUT_PORT
   
   
   #include "Port.h"
   
   namespace PySysLinkBase
   {
       class OutputPort : public Port {
           public:
               OutputPort(std::shared_ptr<UnknownTypeSignalValue> value);
       };
   }
   
   #endif /* SRC_PORTS_AND_SIGNAL_VALUES_OUTPUT_PORT */
