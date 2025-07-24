
.. _program_listing_file_PySysLinkBase_src_PortsAndSignalValues_InputPort.cpp:

Program Listing for File InputPort.cpp
======================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortsAndSignalValues_InputPort.cpp>` (``PySysLinkBase/src/PortsAndSignalValues/InputPort.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "InputPort.h"
   
   namespace PySysLinkBase
   {
       InputPort::InputPort(bool hasDirectFeedthrough, std::shared_ptr<UnknownTypeSignalValue> value) : Port(value)
       {
           this->hasDirectFeedthrough = hasDirectFeedthrough;
       }
   
       const bool InputPort::HasDirectFeedthrough() const
       {
           return this->hasDirectFeedthrough;
       }   
   
   } // namespace PySysLinkBase
