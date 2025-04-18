
.. _program_listing_file_PySysLinkBase_src_ModelParser.h:

Program Listing for File ModelParser.h
======================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_ModelParser.h>` (``PySysLinkBase/src/ModelParser.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PY_SYS_LINK_BASE_MODEL_PARSER
   #define SRC_PY_SYS_LINK_BASE_MODEL_PARSER
   
   #include "SimulationModel.h"
   #include <string>
   #include "ConfigurationValue.h"
   #include <yaml-cpp/yaml.h>
   #include <map>
   #include "IBlockFactory.h"
   
   namespace PySysLinkBase
   {
       class ModelParser
       {
           private:
               static ConfigurationValue YamlToConfigurationValue(const YAML::Node& node);
               static std::vector<std::shared_ptr<PortLink>> ParseLinks(std::vector<std::map<std::string, ConfigurationValue>> linksConfigurations, const std::vector<std::shared_ptr<ISimulationBlock>>& blocks);
               static std::vector<std::shared_ptr<ISimulationBlock>> ParseBlocks(std::vector<std::map<std::string, ConfigurationValue>> blocksConfigurations, const std::map<std::string, std::shared_ptr<IBlockFactory>>& blockFactories, std::shared_ptr<IBlockEventsHandler> blockEventsHandler);
               static std::complex<double> ParseComplex(const std::string& str);
   
           public:
               static std::shared_ptr<SimulationModel> ParseFromYaml(std::string filename, const std::map<std::string, std::shared_ptr<IBlockFactory>>& blockFactories, std::shared_ptr<IBlockEventsHandler> blockEventsHandler);
       };
   } // namespace PySysLinkBase
   
   
   #endif /* SRC_PY_SYS_LINK_BASE_MODEL_PARSER */
