
.. _program_listing_file_PySysLinkBase_src_SpdlogManager.h:

Program Listing for File SpdlogManager.h
========================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_SpdlogManager.h>` (``PySysLinkBase/src/SpdlogManager.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_SPDLOG_MANAGER
   #define SRC_SPDLOG_MANAGER
   
   namespace PySysLinkBase
   {
       enum LogLevel
       {
           off,
           debug,
           info,
           warning,
           error,
           critical
       };
   
       class SpdlogManager
       {
           public:
           static void ConfigureDefaultLogger();
           static void SetLogLevel(LogLevel logLevel);
       };
   } // namespace PySysLinkBase
   
   
   #endif /* SRC_SPDLOG_MANAGER */
