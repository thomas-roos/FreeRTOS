cmake_minimum_required(VERSION 3.16)
project(MbedTLS)
set(PROJECT_NAME MbedTLS)

################################################################################
# Source groups
################################################################################
set(no_group_source_files
    "mbedtls_config_v3.5.1.h"
    "mbedtls_freertos_port.c"
    "mbedtls_freertos_port.h"
    "threading_alt.h"
)
source_group("" FILES ${no_group_source_files})

set(MbedTLS_Headers__mbedtls
    "../../ThirdParty/mbedtls/include/mbedtls/aes.h"
    "../../ThirdParty/mbedtls/include/mbedtls/aria.h"
    "../../ThirdParty/mbedtls/include/mbedtls/asn1.h"
    "../../ThirdParty/mbedtls/include/mbedtls/asn1write.h"
    "../../ThirdParty/mbedtls/include/mbedtls/base64.h"
    "../../ThirdParty/mbedtls/include/mbedtls/bignum.h"
    "../../ThirdParty/mbedtls/include/mbedtls/build_info.h"
    "../../ThirdParty/mbedtls/include/mbedtls/camellia.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ccm.h"
    "../../ThirdParty/mbedtls/include/mbedtls/chacha20.h"
    "../../ThirdParty/mbedtls/include/mbedtls/chachapoly.h"
    "../../ThirdParty/mbedtls/include/mbedtls/check_config.h"
    "../../ThirdParty/mbedtls/include/mbedtls/cipher.h"
    "../../ThirdParty/mbedtls/include/mbedtls/cmac.h"
    "../../ThirdParty/mbedtls/include/mbedtls/compat-2.x.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_adjust_legacy_crypto.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_adjust_legacy_from_psa.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_adjust_psa_from_legacy.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_adjust_psa_superset_legacy.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_adjust_ssl.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_adjust_x509.h"
    "../../ThirdParty/mbedtls/include/mbedtls/config_psa.h"
    "../../ThirdParty/mbedtls/include/mbedtls/constant_time.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ctr_drbg.h"
    "../../ThirdParty/mbedtls/include/mbedtls/debug.h"
    "../../ThirdParty/mbedtls/include/mbedtls/des.h"
    "../../ThirdParty/mbedtls/include/mbedtls/dhm.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ecdh.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ecdsa.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ecjpake.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ecp.h"
    "../../ThirdParty/mbedtls/include/mbedtls/entropy.h"
    "../../ThirdParty/mbedtls/include/mbedtls/error.h"
    "../../ThirdParty/mbedtls/include/mbedtls/gcm.h"
    "../../ThirdParty/mbedtls/include/mbedtls/hkdf.h"
    "../../ThirdParty/mbedtls/include/mbedtls/hmac_drbg.h"
    "../../ThirdParty/mbedtls/include/mbedtls/lms.h"
    "../../ThirdParty/mbedtls/include/mbedtls/mbedtls_config.h"
    "../../ThirdParty/mbedtls/include/mbedtls/md.h"
    "../../ThirdParty/mbedtls/include/mbedtls/md5.h"
    "../../ThirdParty/mbedtls/include/mbedtls/memory_buffer_alloc.h"
    "../../ThirdParty/mbedtls/include/mbedtls/net_sockets.h"
    "../../ThirdParty/mbedtls/include/mbedtls/nist_kw.h"
    "../../ThirdParty/mbedtls/include/mbedtls/oid.h"
    "../../ThirdParty/mbedtls/include/mbedtls/pem.h"
    "../../ThirdParty/mbedtls/include/mbedtls/pk.h"
    "../../ThirdParty/mbedtls/include/mbedtls/pkcs12.h"
    "../../ThirdParty/mbedtls/include/mbedtls/pkcs5.h"
    "../../ThirdParty/mbedtls/include/mbedtls/pkcs7.h"
    "../../ThirdParty/mbedtls/include/mbedtls/platform.h"
    "../../ThirdParty/mbedtls/include/mbedtls/platform_time.h"
    "../../ThirdParty/mbedtls/include/mbedtls/platform_util.h"
    "../../ThirdParty/mbedtls/include/mbedtls/poly1305.h"
    "../../ThirdParty/mbedtls/include/mbedtls/private_access.h"
    "../../ThirdParty/mbedtls/include/mbedtls/psa_util.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ripemd160.h"
    "../../ThirdParty/mbedtls/include/mbedtls/rsa.h"
    "../../ThirdParty/mbedtls/include/mbedtls/sha1.h"
    "../../ThirdParty/mbedtls/include/mbedtls/sha256.h"
    "../../ThirdParty/mbedtls/include/mbedtls/sha3.h"
    "../../ThirdParty/mbedtls/include/mbedtls/sha512.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ssl.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ssl_cache.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ssl_ciphersuites.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ssl_cookie.h"
    "../../ThirdParty/mbedtls/include/mbedtls/ssl_ticket.h"
    "../../ThirdParty/mbedtls/include/mbedtls/threading.h"
    "../../ThirdParty/mbedtls/include/mbedtls/timing.h"
    "../../ThirdParty/mbedtls/include/mbedtls/version.h"
    "../../ThirdParty/mbedtls/include/mbedtls/x509.h"
    "../../ThirdParty/mbedtls/include/mbedtls/x509_crl.h"
    "../../ThirdParty/mbedtls/include/mbedtls/x509_crt.h"
    "../../ThirdParty/mbedtls/include/mbedtls/x509_csr.h"
)
source_group("MbedTLS Headers\\mbedtls" FILES ${MbedTLS_Headers__mbedtls})

set(MbedTLS_Headers__psa
    "../../ThirdParty/mbedtls/include/psa/build_info.h"
    "../../ThirdParty/mbedtls/include/psa/crypto.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_adjust_auto_enabled.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_adjust_config_key_pair_types.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_adjust_config_synonyms.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_builtin_composites.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_builtin_key_derivation.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_builtin_primitives.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_compat.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_config.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_driver_common.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_driver_contexts_composites.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_driver_contexts_key_derivation.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_driver_contexts_primitives.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_extra.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_legacy.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_platform.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_se_driver.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_sizes.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_struct.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_types.h"
    "../../ThirdParty/mbedtls/include/psa/crypto_values.h"
)
source_group("MbedTLS Headers\\psa" FILES ${MbedTLS_Headers__psa})

set(MbedTLS_Source
    "../../ThirdParty/mbedtls/library/aes.c"
    "../../ThirdParty/mbedtls/library/aesce.c"
    "../../ThirdParty/mbedtls/library/aesce.h"
    "../../ThirdParty/mbedtls/library/aesni.c"
    "../../ThirdParty/mbedtls/library/aesni.h"
    "../../ThirdParty/mbedtls/library/alignment.h"
    "../../ThirdParty/mbedtls/library/aria.c"
    "../../ThirdParty/mbedtls/library/asn1parse.c"
    "../../ThirdParty/mbedtls/library/asn1write.c"
    "../../ThirdParty/mbedtls/library/base64.c"
    "../../ThirdParty/mbedtls/library/base64_internal.h"
    "../../ThirdParty/mbedtls/library/bignum.c"
    "../../ThirdParty/mbedtls/library/bignum_core.c"
    "../../ThirdParty/mbedtls/library/bignum_core.h"
    "../../ThirdParty/mbedtls/library/bignum_mod.c"
    "../../ThirdParty/mbedtls/library/bignum_mod.h"
    "../../ThirdParty/mbedtls/library/bignum_mod_raw.c"
    "../../ThirdParty/mbedtls/library/bignum_mod_raw.h"
    "../../ThirdParty/mbedtls/library/bignum_mod_raw_invasive.h"
    "../../ThirdParty/mbedtls/library/bn_mul.h"
    "../../ThirdParty/mbedtls/library/camellia.c"
    "../../ThirdParty/mbedtls/library/ccm.c"
    "../../ThirdParty/mbedtls/library/chacha20.c"
    "../../ThirdParty/mbedtls/library/chachapoly.c"
    "../../ThirdParty/mbedtls/library/check_crypto_config.h"
    "../../ThirdParty/mbedtls/library/cipher.c"
    "../../ThirdParty/mbedtls/library/cipher_wrap.c"
    "../../ThirdParty/mbedtls/library/cipher_wrap.h"
    "../../ThirdParty/mbedtls/library/cmac.c"
    "../../ThirdParty/mbedtls/library/common.h"
    "../../ThirdParty/mbedtls/library/constant_time.c"
    "../../ThirdParty/mbedtls/library/constant_time_impl.h"
    "../../ThirdParty/mbedtls/library/constant_time_internal.h"
    "../../ThirdParty/mbedtls/library/ctr_drbg.c"
    "../../ThirdParty/mbedtls/library/debug.c"
    "../../ThirdParty/mbedtls/library/des.c"
    "../../ThirdParty/mbedtls/library/dhm.c"
    "../../ThirdParty/mbedtls/library/ecdh.c"
    "../../ThirdParty/mbedtls/library/ecdsa.c"
    "../../ThirdParty/mbedtls/library/ecjpake.c"
    "../../ThirdParty/mbedtls/library/ecp.c"
    "../../ThirdParty/mbedtls/library/ecp_curves.c"
    "../../ThirdParty/mbedtls/library/ecp_curves_new.c"
    "../../ThirdParty/mbedtls/library/ecp_internal_alt.h"
    "../../ThirdParty/mbedtls/library/ecp_invasive.h"
    "../../ThirdParty/mbedtls/library/entropy.c"
    "../../ThirdParty/mbedtls/library/entropy_poll.c"
    "../../ThirdParty/mbedtls/library/entropy_poll.h"
    "../../ThirdParty/mbedtls/library/error.c"
    "../../ThirdParty/mbedtls/library/gcm.c"
    "../../ThirdParty/mbedtls/library/hkdf.c"
    "../../ThirdParty/mbedtls/library/hmac_drbg.c"
    "../../ThirdParty/mbedtls/library/lmots.c"
    "../../ThirdParty/mbedtls/library/lmots.h"
    "../../ThirdParty/mbedtls/library/lms.c"
    "../../ThirdParty/mbedtls/library/md.c"
    "../../ThirdParty/mbedtls/library/md5.c"
    "../../ThirdParty/mbedtls/library/md_psa.h"
    "../../ThirdParty/mbedtls/library/md_wrap.h"
    "../../ThirdParty/mbedtls/library/memory_buffer_alloc.c"
    "../../ThirdParty/mbedtls/library/mps_common.h"
    "../../ThirdParty/mbedtls/library/mps_error.h"
    "../../ThirdParty/mbedtls/library/mps_reader.c"
    "../../ThirdParty/mbedtls/library/mps_reader.h"
    "../../ThirdParty/mbedtls/library/mps_trace.c"
    "../../ThirdParty/mbedtls/library/mps_trace.h"
    "../../ThirdParty/mbedtls/library/net_sockets.c"
    "../../ThirdParty/mbedtls/library/nist_kw.c"
    "../../ThirdParty/mbedtls/library/oid.c"
    "../../ThirdParty/mbedtls/library/padlock.c"
    "../../ThirdParty/mbedtls/library/padlock.h"
    "../../ThirdParty/mbedtls/library/pem.c"
    "../../ThirdParty/mbedtls/library/pk.c"
    "../../ThirdParty/mbedtls/library/pk_internal.h"
    "../../ThirdParty/mbedtls/library/pk_wrap.c"
    "../../ThirdParty/mbedtls/library/pk_wrap.h"
    "../../ThirdParty/mbedtls/library/pkcs12.c"
    "../../ThirdParty/mbedtls/library/pkcs5.c"
    "../../ThirdParty/mbedtls/library/pkcs7.c"
    "../../ThirdParty/mbedtls/library/pkparse.c"
    "../../ThirdParty/mbedtls/library/pkwrite.c"
    "../../ThirdParty/mbedtls/library/pkwrite.h"
    "../../ThirdParty/mbedtls/library/platform.c"
    "../../ThirdParty/mbedtls/library/platform_util.c"
    "../../ThirdParty/mbedtls/library/poly1305.c"
    "../../ThirdParty/mbedtls/library/psa_crypto.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_aead.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_aead.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_cipher.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_cipher.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_client.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_core.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_core_common.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_driver_wrappers.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_driver_wrappers_no_static.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_driver_wrappers_no_static.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_ecp.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_ecp.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_ffdh.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_ffdh.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_hash.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_hash.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_invasive.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_its.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_mac.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_mac.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_pake.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_pake.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_random_impl.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_rsa.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_rsa.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_se.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_se.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_slot_management.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_slot_management.h"
    "../../ThirdParty/mbedtls/library/psa_crypto_storage.c"
    "../../ThirdParty/mbedtls/library/psa_crypto_storage.h"
    "../../ThirdParty/mbedtls/library/psa_its_file.c"
    "../../ThirdParty/mbedtls/library/psa_util.c"
    "../../ThirdParty/mbedtls/library/psa_util_internal.h"
    "../../ThirdParty/mbedtls/library/ripemd160.c"
    "../../ThirdParty/mbedtls/library/rsa.c"
    "../../ThirdParty/mbedtls/library/rsa_alt_helpers.c"
    "../../ThirdParty/mbedtls/library/rsa_alt_helpers.h"
    "../../ThirdParty/mbedtls/library/sha1.c"
    "../../ThirdParty/mbedtls/library/sha256.c"
    "../../ThirdParty/mbedtls/library/sha3.c"
    "../../ThirdParty/mbedtls/library/sha512.c"
    "../../ThirdParty/mbedtls/library/ssl_cache.c"
    "../../ThirdParty/mbedtls/library/ssl_ciphersuites.c"
    "../../ThirdParty/mbedtls/library/ssl_client.c"
    "../../ThirdParty/mbedtls/library/ssl_client.h"
    "../../ThirdParty/mbedtls/library/ssl_cookie.c"
    "../../ThirdParty/mbedtls/library/ssl_debug_helpers.h"
    "../../ThirdParty/mbedtls/library/ssl_debug_helpers_generated.c"
    "../../ThirdParty/mbedtls/library/ssl_misc.h"
    "../../ThirdParty/mbedtls/library/ssl_msg.c"
    "../../ThirdParty/mbedtls/library/ssl_ticket.c"
    "../../ThirdParty/mbedtls/library/ssl_tls.c"
    "../../ThirdParty/mbedtls/library/ssl_tls12_client.c"
    "../../ThirdParty/mbedtls/library/ssl_tls12_server.c"
    "../../ThirdParty/mbedtls/library/ssl_tls13_client.c"
    "../../ThirdParty/mbedtls/library/ssl_tls13_generic.c"
    "../../ThirdParty/mbedtls/library/ssl_tls13_invasive.h"
    "../../ThirdParty/mbedtls/library/ssl_tls13_keys.c"
    "../../ThirdParty/mbedtls/library/ssl_tls13_keys.h"
    "../../ThirdParty/mbedtls/library/ssl_tls13_server.c"
    "../../ThirdParty/mbedtls/library/threading.c"
    "../../ThirdParty/mbedtls/library/timing.c"
    "../../ThirdParty/mbedtls/library/version.c"
    "../../ThirdParty/mbedtls/library/version_features.c"
    "../../ThirdParty/mbedtls/library/x509.c"
    "../../ThirdParty/mbedtls/library/x509_create.c"
    "../../ThirdParty/mbedtls/library/x509_crl.c"
    "../../ThirdParty/mbedtls/library/x509_crt.c"
    "../../ThirdParty/mbedtls/library/x509_csr.c"
    "../../ThirdParty/mbedtls/library/x509write.c"
    "../../ThirdParty/mbedtls/library/x509write_crt.c"
    "../../ThirdParty/mbedtls/library/x509write_csr.c"
)
source_group("MbedTLS Source" FILES ${MbedTLS_Source})

set(ALL_FILES
    ${no_group_source_files}
    ${MbedTLS_Headers__mbedtls}
    ${MbedTLS_Headers__psa}
    ${MbedTLS_Source}
)

################################################################################
# Target
################################################################################
add_library(${PROJECT_NAME} STATIC ${ALL_FILES})

# use_props(${PROJECT_NAME} "${CMAKE_CONFIGURATION_TYPES}" "${DEFAULT_CXX_PROPS}")
set(ROOT_NAMESPACE MbedTLS)

set_target_properties(${PROJECT_NAME} PROPERTIES
    VS_GLOBAL_KEYWORD "Win32Proj"
)
################################################################################
# Output directory
################################################################################
set_target_properties(${PROJECT_NAME} PROPERTIES
    OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/build/${PROJECT_NAME}/${CMAKE_VS_PLATFORM_NAME}/$<CONFIG>/"
)
################################################################################
# Include directories
################################################################################
target_include_directories(${PROJECT_NAME} PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/.;"
    "${CMAKE_CURRENT_SOURCE_DIR}/../../ThirdParty/mbedtls/library;"
    "${CMAKE_CURRENT_SOURCE_DIR}/../../ThirdParty/mbedtls/include"
    "${CMAKE_CURRENT_SOURCE_DIR}/../../Demo/FreeRTOS_Plus_TCP_MQTT_Posix"
    "${CMAKE_CURRENT_SOURCE_DIR}/../../../FreeRTOS/Source/portable/ThirdParty/GCC/Posix"
#    "${CMAKE_CURRENT_SOURCE_DIR}/../../Demo/FreeRTOS_Plus_TCP_MQTT_Posix/Trace_Recorder_Configuration/"
#    "${CMAKE_CURRENT_SOURCE_DIR}/../../Source/FreeRTOS-Plus-Trace/include"
#    "${CMAKE_CURRENT_SOURCE_DIR}/../../Source/FreeRTOS-Plus-Trace/config"
    "${CMAKE_CURRENT_SOURCE_DIR}/../../../FreeRTOS/Source/include/"
)

################################################################################
# Compile definitions
################################################################################
target_compile_definitions(${PROJECT_NAME} PRIVATE
    "WIN32;"
    "WIN32_LEAN_AND_MEAN;"
    "MBEDTLS_CONFIG_FILE=\"mbedtls_config_v3.5.1.h\";"
    "_DEBUG;"
    "_CONSOLE;"
    "UNICODE;"
    "_UNICODE;"
    "projCOVERAGE_TEST=0"
)

################################################################################
# Compile and link options
################################################################################
if(MSVC)
    target_compile_options(${PROJECT_NAME} PRIVATE
        /permissive-;
        /MP;
        /sdl;
        /W3;
        ${DEFAULT_CXX_DEBUG_INFORMATION_FORMAT};
        ${DEFAULT_CXX_EXCEPTION_HANDLING}
    )
    target_link_options(${PROJECT_NAME} PRIVATE
        /SUBSYSTEM:CONSOLE
    )
endif()

################################################################################
# Dependencies
################################################################################
# Link with other targets.
target_link_libraries(${PROJECT_NAME} PUBLIC
    FreeRTOS-Kernel
)
