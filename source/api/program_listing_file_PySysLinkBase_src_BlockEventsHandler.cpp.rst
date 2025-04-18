
.. _program_listing_file_PySysLinkBase_src_BlockEventsHandler.cpp:

Program Listing for File BlockEventsHandler.cpp
===============================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_BlockEventsHandler.cpp>` (``PySysLinkBase/src/BlockEventsHandler.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "BlockEventsHandler.h"
   #include "BlockEvents/ValueUpdateBlockEvent.h"
   #include "spdlog/spdlog.h"
   #include <sstream>
   
   namespace PySysLinkBase
   {
       BlockEventsHandler::BlockEventsHandler()
       {
           this->valueUpdateBlockEventCallbacks = {};
       }
   
       void BlockEventsHandler::BlockEventCallback(const std::shared_ptr<BlockEvent> blockEvent) const
       {
           if (blockEvent->eventTypeId == "ValueUpdate")
           {            
               std::shared_ptr<ValueUpdateBlockEvent> displayUpdateBlockEvent = std::dynamic_pointer_cast<ValueUpdateBlockEvent>(blockEvent);
                   
               if (!displayUpdateBlockEvent) throw std::bad_cast();
   
               try
               {
                   spdlog::get("default_pysyslink")->info("Value {}, {:03.2f} s : {}", displayUpdateBlockEvent->valueId, displayUpdateBlockEvent->simulationTime, std::get<double>(displayUpdateBlockEvent->value));
               }
               catch(const std::exception& e)
               {
                   std::ostringstream oss;
                   oss << std::get<std::complex<double>>(displayUpdateBlockEvent->value);
                   std::string complexNumber = oss.str();
                   spdlog::get("default_pysyslink")->info("Value {}, {:03.2f} s : {}", displayUpdateBlockEvent->valueId, displayUpdateBlockEvent->simulationTime, complexNumber);
               }
   
               for (const auto& callback : this->valueUpdateBlockEventCallbacks)
               {
                   callback(displayUpdateBlockEvent);
               }
               
           }
       }
   
       void BlockEventsHandler::RegisterValueUpdateBlockEventCallback(std::function<void (std::shared_ptr<ValueUpdateBlockEvent>)> callback)
       {
           this->valueUpdateBlockEventCallbacks.push_back(callback);
       }
   
   } // namespace PySysLinkBase
