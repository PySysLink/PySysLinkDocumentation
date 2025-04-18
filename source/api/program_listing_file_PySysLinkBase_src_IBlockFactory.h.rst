
.. _program_listing_file_PySysLinkBase_src_IBlockFactory.h:

Program Listing for File IBlockFactory.h
========================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_IBlockFactory.h>` (``PySysLinkBase/src/IBlockFactory.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PY_SYS_LINK_BASE_IBLOCK_FACTORY
   #define SRC_PY_SYS_LINK_BASE_IBLOCK_FACTORY
   
   #include "ISimulationBlock.h"
   #include <vector>
   #include "ConfigurationValue.h"
   #include <map>
   #include <memory>
   #include <string>
   #include "IBlockEventsHandler.h"
   
   namespace PySysLinkBase
   {
      class IBlockFactory {
         public:
            virtual ~IBlockFactory() = default;
            virtual std::shared_ptr<ISimulationBlock> CreateBlock(std::map<std::string, ConfigurationValue> blockConfiguration, std::shared_ptr<IBlockEventsHandler> blockEventsHandler) = 0;
      };
   }
   
   #endif /* SRC_PY_SYS_LINK_BASE_IBLOCK_FACTORY */
