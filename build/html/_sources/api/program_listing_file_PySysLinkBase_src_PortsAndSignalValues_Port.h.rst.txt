
.. _program_listing_file_PySysLinkBase_src_PortsAndSignalValues_Port.h:

Program Listing for File Port.h
===============================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortsAndSignalValues_Port.h>` (``PySysLinkBase/src/PortsAndSignalValues/Port.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PORTS_AND_SIGNAL_VALUES_PORT
   #define SRC_PORTS_AND_SIGNAL_VALUES_PORT
   
   #include <string>
   #include "UnknownTypeSignalValue.h"
   #include <memory>
   #include <functional>
   
   
   namespace PySysLinkBase
   {
       class ISimulationBlock;
   
       class Port {
       protected:
           std::shared_ptr<UnknownTypeSignalValue> value;
           
       public:
           Port(std::shared_ptr<UnknownTypeSignalValue> value);
   
           void TryCopyValueToPort(Port& otherPort) const;
   
           void SetValue(std::shared_ptr<UnknownTypeSignalValue> value);
           std::shared_ptr<UnknownTypeSignalValue> GetValue() const;
   
           bool operator==(const Port& rhs) const
           {
               return this == &rhs;
           }
       };
   }
   
   #endif /* SRC_PORTS_AND_SIGNAL_VALUES_PORT */
