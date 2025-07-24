
.. _program_listing_file_PySysLinkBase_src_BlockTypeSupportPluginLoader.h:

Program Listing for File BlockTypeSupportPluginLoader.h
=======================================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_BlockTypeSupportPluginLoader.h>` (``PySysLinkBase/src/BlockTypeSupportPluginLoader.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_PY_SYS_LINK_BASE_BLOCK_TYPE_SUPPORT_PLUGING_LOADER
   #define SRC_PY_SYS_LINK_BASE_BLOCK_TYPE_SUPPORT_PLUGING_LOADER
   
   #include <map>
   #include <memory>
   #include <string>
   #include <dlfcn.h> // For Linux/macOS dynamic linking. Use `windows.h` for Windows.
   
   #include "IBlockFactory.h"
   
   namespace PySysLinkBase {
   
   class BlockTypeSupportPluginLoader {
   public:
       std::map<std::string, std::shared_ptr<IBlockFactory>> LoadPlugins(const std::string& pluginDirectory, std::map<std::string, PySysLinkBase::ConfigurationValue> pluginConfiguration);
   
   private:
       std::vector<std::string> FindSharedLibraries(const std::string& pluginDirectory);
       bool StringEndsWith(const std::string& str, const std::string& suffix);
   };
   
   } // namespace PySysLinkBase
   
   #endif /* SRC_PY_SYS_LINK_BASE_BLOCK_TYPE_SUPPORT_PLUGING_LOADER */
