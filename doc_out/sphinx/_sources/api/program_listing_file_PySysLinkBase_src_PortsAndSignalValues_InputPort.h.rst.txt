
.. _program_listing_file_PySysLinkBase_src_PortsAndSignalValues_InputPort.h:

Program Listing for File InputPort.h
====================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortsAndSignalValues_InputPort.h>` (``PySysLinkBase/src/PortsAndSignalValues/InputPort.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PORTS_AND_SIGNAL_VALUES_INPUT_PORT
   #define SRC_PORTS_AND_SIGNAL_VALUES_INPUT_PORT
   
   #include "Port.h"
   
   namespace PySysLinkBase
   {
       class InputPort : public Port {
       private:
           bool hasDirectFeedthrough;
       public:
           InputPort(bool hasDirectFeedthrough, std::shared_ptr<UnknownTypeSignalValue> value);
           const bool HasDirectFeedthrough() const;    
       };
   }
   
   #endif /* SRC_PORTS_AND_SIGNAL_VALUES_INPUT_PORT */
