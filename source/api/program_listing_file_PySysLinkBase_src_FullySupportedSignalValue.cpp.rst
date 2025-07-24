
.. _program_listing_file_PySysLinkBase_src_FullySupportedSignalValue.cpp:

Program Listing for File FullySupportedSignalValue.cpp
======================================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_FullySupportedSignalValue.cpp>` (``PySysLinkBase/src/FullySupportedSignalValue.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "FullySupportedSignalValue.h"
   
   namespace PySysLinkBase
   {
       FullySupportedSignalValue ConvertToFullySupportedSignalValue(const std::shared_ptr<UnknownTypeSignalValue>& unknownValue)
       {
           try {
               if (auto intValue = unknownValue->TryCastToTyped<int>()) {
                   return FullySupportedSignalValue(intValue->GetPayload());
               }
           } catch (const std::bad_cast&) {}
   
           try {
               if (auto doubleValue = unknownValue->TryCastToTyped<double>()) {
                   return FullySupportedSignalValue(doubleValue->GetPayload());
               }
           } catch (const std::bad_cast&) {}
   
           try {
               if (auto boolValue = unknownValue->TryCastToTyped<bool>()) {
                   return FullySupportedSignalValue(boolValue->GetPayload());
               }
           } catch (const std::bad_cast&) {}
   
           try {
               if (auto complexValue = unknownValue->TryCastToTyped<std::complex<double>>()) {
                   return FullySupportedSignalValue(complexValue->GetPayload());
               }
           } catch (const std::bad_cast&) {}
   
           try {
               if (auto stringValue = unknownValue->TryCastToTyped<std::string>()) {
                   return FullySupportedSignalValue(stringValue->GetPayload());
               }
           } catch (const std::bad_cast&) {}
   
           throw std::runtime_error("UnknownTypeSignalValue cannot be converted to FullySupportedSignalValue");
       }
   } // namespace PySysLinkBase
