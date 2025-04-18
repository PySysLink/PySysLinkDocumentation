
.. _program_listing_file_PySysLinkBase_src_PortLink.h:

Program Listing for File PortLink.h
===================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_PortLink.h>` (``PySysLinkBase/src/PortLink.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PY_SYS_LINK_BASE_PORT_LINK
   #define SRC_PY_SYS_LINK_BASE_PORT_LINK
   
   #include "ISimulationBlock.h"
   #include "PortsAndSignalValues/InputPort.h"
   #include "PortsAndSignalValues/OutputPort.h"
   #include <algorithm>
   #include <map>
   #include "ConfigurationValue.h"
   
   namespace PySysLinkBase
   {
       class PortLink
       {
       public:
           PortLink(std::shared_ptr<ISimulationBlock> originBlock, 
                   std::shared_ptr<ISimulationBlock> sinkBlock, 
                   int originBlockPortIndex, 
                   int sinkBlockPortIndex) : originBlock(originBlock), sinkBlock(sinkBlock), 
                                             originBlockPortIndex(originBlockPortIndex), sinkBlockPortIndex(sinkBlockPortIndex) {}
   
           std::shared_ptr<ISimulationBlock> originBlock;
           std::shared_ptr<ISimulationBlock> sinkBlock;
           int originBlockPortIndex;
           int sinkBlockPortIndex;
   
           static PortLink ParseFromConfig(std::map<std::string, ConfigurationValue> linkConfiguration, const std::vector<std::shared_ptr<ISimulationBlock>>& blocks);
       };
   }
   
   #endif /* SRC_PY_SYS_LINK_BASE_PORT_LINK */
