
.. _program_listing_file_PySysLinkBase_src_FullySupportedSignalValue.h:

Program Listing for File FullySupportedSignalValue.h
====================================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_FullySupportedSignalValue.h>` (``PySysLinkBase/src/FullySupportedSignalValue.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_FULLY_SUPPORTED_SIGNAL_VALUE
   #define SRC_FULLY_SUPPORTED_SIGNAL_VALUE
   
   
   #include <string>
   #include <variant>
   #include <vector>
   #include <memory>
   #include <map>
   #include <stdexcept>
   #include <complex>
   
   #include "PortsAndSignalValues/UnknownTypeSignalValue.h"
   #include "PortsAndSignalValues/SignalValue.h"
   
   namespace PySysLinkBase
   {    
       using FullySupportedSignalValue = std::variant<
       int,
       double,
       bool,
       std::complex<double>,
       std::string
   >;
   
   FullySupportedSignalValue ConvertToFullySupportedSignalValue(const std::shared_ptr<UnknownTypeSignalValue>& unknownValue);
   
   } // namespace PySysLinkBase
   
   
   
   #endif /* SRC_FULLY_SUPPORTED_SIGNAL_VALUE */
