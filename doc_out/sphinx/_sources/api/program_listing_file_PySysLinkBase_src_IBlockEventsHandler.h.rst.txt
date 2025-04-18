
.. _program_listing_file_PySysLinkBase_src_IBlockEventsHandler.h:

Program Listing for File IBlockEventsHandler.h
==============================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_IBlockEventsHandler.h>` (``PySysLinkBase/src/IBlockEventsHandler.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_IBLOCK_EVENTS_HANDLER
   #define SRC_IBLOCK_EVENTS_HANDLER
   
   #include "BlockEvents/BlockEvent.h"
   #include "BlockEvents/ValueUpdateBlockEvent.h"
   #include <memory>
   #include <functional>
   
   namespace PySysLinkBase
   {
       class IBlockEventsHandler
       {
           public:
           virtual ~IBlockEventsHandler() = default;
           
           virtual void BlockEventCallback(const std::shared_ptr<BlockEvent> blockEvent) const = 0;
           virtual void RegisterValueUpdateBlockEventCallback(std::function<void (std::shared_ptr<ValueUpdateBlockEvent>)> callback) = 0;
   
       };
   } // namespace PySysLinkBase
   
   
   
   #endif /* SRC_IBLOCK_EVENTS_HANDLER */
