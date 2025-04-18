
.. _program_listing_file_PySysLinkBase_src_PortLink.cpp:

Program Listing for File PortLink.cpp
=====================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortLink.cpp>` (``PySysLinkBase/src/PortLink.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "PortLink.h"
   
   namespace PySysLinkBase
   {
       PortLink PortLink::ParseFromConfig(std::map<std::string, ConfigurationValue> linkConfiguration, const std::vector<std::shared_ptr<ISimulationBlock>>& blocks)
       {
           std::string sourceBlockId = ConfigurationValueManager::TryGetConfigurationValue<std::string>("SourceBlockId", linkConfiguration);
           int sourcePortIdx = ConfigurationValueManager::TryGetConfigurationValue<int>("SourcePortIdx", linkConfiguration);
           std::string destinationBlockId = ConfigurationValueManager::TryGetConfigurationValue<std::string>("DestinationBlockId", linkConfiguration);
           int destinationPortIdx = ConfigurationValueManager::TryGetConfigurationValue<int>("DestinationPortIdx", linkConfiguration);
   
           std::shared_ptr<ISimulationBlock> sourceBlock = ISimulationBlock::FindBlockById(sourceBlockId, blocks);
           std::shared_ptr<ISimulationBlock> destinationBlock = ISimulationBlock::FindBlockById(destinationBlockId, blocks);
   
           return PortLink(sourceBlock, destinationBlock, sourcePortIdx, destinationPortIdx);
       }
   } // namespace PySysLinkBase
