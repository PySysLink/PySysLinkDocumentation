
.. _program_listing_file_PySysLinkBase_src_PortsAndSignalValues_OutputPort.cpp:

Program Listing for File OutputPort.cpp
=======================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortsAndSignalValues_OutputPort.cpp>` (``PySysLinkBase/src/PortsAndSignalValues/OutputPort.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "OutputPort.h"
   
   namespace PySysLinkBase
   {
       OutputPort::OutputPort(std::shared_ptr<UnknownTypeSignalValue> value) : Port(value)
       {
   
       }
   } // namespace PySysLinkBase
