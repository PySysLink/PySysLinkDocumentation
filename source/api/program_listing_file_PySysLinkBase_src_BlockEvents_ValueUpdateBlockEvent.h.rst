
.. _program_listing_file_PySysLinkBase_src_BlockEvents_ValueUpdateBlockEvent.h:

Program Listing for File ValueUpdateBlockEvent.h
================================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_BlockEvents_ValueUpdateBlockEvent.h>` (``PySysLinkBase/src/BlockEvents/ValueUpdateBlockEvent.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_BLOCK_EVENTS_VALUE_UPDATE_BLOCK_EVENT
   #define SRC_BLOCK_EVENTS_VALUE_UPDATE_BLOCK_EVENT
   
   #include <string>
   #include "../FullySupportedSignalValue.h"
   #include "BlockEvent.h"
   
   namespace PySysLinkBase
   {
       class ValueUpdateBlockEvent : public BlockEvent
       {
           public:
           double simulationTime;
           std::string valueId;
           FullySupportedSignalValue value;
           ValueUpdateBlockEvent(double simulationTime, std::string valueId, FullySupportedSignalValue value) : simulationTime(simulationTime), valueId(valueId), value(value), BlockEvent("ValueUpdate") {}
   
           ~ValueUpdateBlockEvent() = default;
       };
   } // namespace PySysLinkBase
   #endif /* SRC_BLOCK_EVENTS_VALUE_UPDATE_BLOCK_EVENT */
