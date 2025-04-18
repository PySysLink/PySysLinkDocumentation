
.. _program_listing_file_PySysLinkBase_src_BlockEvents_BlockEvent.h:

Program Listing for File BlockEvent.h
=====================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_BlockEvents_BlockEvent.h>` (``PySysLinkBase/src/BlockEvents/BlockEvent.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_BLOCK_EVENTS_BLOCK_EVENT
   #define SRC_BLOCK_EVENTS_BLOCK_EVENT
   
   #include <string>
   
   namespace PySysLinkBase
   {
       class BlockEvent
       {
           public:
           std::string eventTypeId;
   
           BlockEvent(std::string eventTypeId) : eventTypeId(eventTypeId) {}
   
           virtual ~BlockEvent() = default; // Ensures the class is polymorphic
       };
   } // namespace PySysLinkBase
   
   
   #endif /* SRC_BLOCK_EVENTS_BLOCK_EVENT */
