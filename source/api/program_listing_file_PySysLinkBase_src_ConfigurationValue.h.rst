
.. _program_listing_file_PySysLinkBase_src_ConfigurationValue.h:

Program Listing for File ConfigurationValue.h
=============================================

|exhale_lsh| :ref:`Return to documentation for file <file_PySysLinkBase_src_ConfigurationValue.h>` (``PySysLinkBase/src/ConfigurationValue.h``)

.. |exhale_lsh| unicode:: U+021B0 .. UPWARDS ARROW WITH TIP LEFTWARDS

.. code-block:: cpp

   #ifndef SRC_CONFIGURATION_VALUE
   #define SRC_CONFIGURATION_VALUE
   
   #include <string>
   #include <variant>
   #include <vector>
   #include <memory>
   #include <map>
   #include <stdexcept>
   #include <complex>
   
   namespace PySysLinkBase
   {
       using ConfigurationValuePrimitive  = std::variant<
           int,
           double,
           bool,
           std::complex<double>,
           std::string,
           std::vector<int>,
           std::vector<double>,
           std::vector<bool>,
           std::vector<std::complex<double>>,
           std::vector<std::string>>;
       
       using ConfigurationValue = std::variant<
           int,
           double,
           bool,
           std::complex<double>,
           std::string,
           std::vector<int>,
           std::vector<double>,
           std::vector<bool>,
           std::vector<std::complex<double>>,
           std::vector<std::string>,
           ConfigurationValuePrimitive,
           std::vector<ConfigurationValuePrimitive>>;
   
       class ConfigurationValueManager
       {
           public:
           template <typename T> 
           static T TryGetConfigurationValue(std::string keyName, std::map<std::string, ConfigurationValue> configurationValues)
           {
               ConfigurationValue foundValue;
               auto it = configurationValues.find(keyName);
               if (it == configurationValues.end()) {
                   throw std::out_of_range("Key name: " + keyName + " not found in configuration.");
               } else {
                   foundValue = it->second;
               }
               try
               {
                   return std::get<T>(foundValue);
               }
               catch (std::bad_variant_access const& ex)
               {
                   throw std::invalid_argument("Configuration option of key: " + keyName + " was not of expected type: " + ex.what());
               }
           }
       };
   } // namespace PySysLinkBase
   
   
   
   #endif /* SRC_CONFIGURATION_VALUE */
