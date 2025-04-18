
.. _program_listing_file_PySysLinkBase_src_SpdlogManager.cpp:

Program Listing for File SpdlogManager.cpp
==========================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_SpdlogManager.cpp>` (``PySysLinkBase/src/SpdlogManager.cpp``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #include "SpdlogManager.h"
   #include "spdlog/spdlog.h"
   #include "spdlog/sinks/stdout_color_sinks.h"
   
   namespace PySysLinkBase
   {
       void SpdlogManager::ConfigureDefaultLogger()
       {
           auto console = spdlog::stdout_color_mt("default_pysyslink");
       }
   
       void SpdlogManager::SetLogLevel(LogLevel logLevel)
       {
           if (logLevel == LogLevel::debug)
           {
               spdlog::set_level(spdlog::level::debug);
           }
           else if (logLevel == LogLevel::info)
           {
               spdlog::set_level(spdlog::level::info);
           }
           else if (logLevel == LogLevel::warning)
           {
               spdlog::set_level(spdlog::level::warn);
           }
           else if (logLevel == LogLevel::error)
           {
               spdlog::set_level(spdlog::level::err);
           }
           else if (logLevel == LogLevel::critical)
           {
               spdlog::set_level(spdlog::level::critical);
           }
           else if (logLevel == LogLevel::off)
           {
               spdlog::set_level(spdlog::level::off);
           }
       }
   
   
   } // namespace PySysLinkBase
