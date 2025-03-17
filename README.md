# Chromium Cipher Suite Customizer
This repository houses scripts for toggling TLS 1.3 cipher suite preferences in Chromium. 

## Motivation 
Check the [Chromium Bug](https://bugs.chromium.org/p/chromium/issues/detail?id=1502090) I have reported.

## Customising the Cipher Preference

### File Descriptions
|File Name       				             |Functionality                                                        |
|------------------------------------|---------------------------------------------------------------------|
|`tls_aes_128_gcm_sha256.cc	`  		   |Makes **AES_128_GCM_SHA256** the most preferred TLS 1.3. cipher      |
|`tls_aes_256_gcm_sha384.cc`   		   |Makes **AES_256_GCM_SHA384** the most preferred TLS 1.3. cipher      |
|`tls_chacha20_poly1305_sha256.cc `  |Makes **CHACHA20_POLY1305_SHA256** the most preferred TLS 1.3 cipher.|

### Steps to Follow
1. Install [depot_tools](https://chromium.googlesource.com/chromium/src/+/main/docs/mac_build_instructions.md#install) and get the [Chromium code](https://www.chromium.org/developers/how-tos/get-the-code/).
2. Go to `chromium -> src -> third_party -> boringssl -> src -> ssl -> handshake_client.cc`.
3. Replace the code in `handshake_client.cc` with the code in file with your most preferred cipher suite's name. 
_For example, if you want your browser's most preferred cipher suite to be `TLS_CHACHA20_POLY1305_SHA256`, replace `handshake_client.cc`'s code with `tls_chacha20_poly1305_sha256.cc`'s code in this repo._
5. [Build and run](https://chromium.googlesource.com/chromium/src/+/main/docs/mac_build_instructions.md#build-chromium).

## Disclaimer
Please note that this script has only been specifically tested with Chromium version `121.0.6128.0`. Additionally, the modification of BoringSSL code suggests compatibility with other programs using BoringSSL, but variations may exist. Use at your own discretion.

## For questions or suggestions, contact:

- **Nimesha Wickramasinghe** - [*n.wickramasinghe@unsw.edu.au*](mailto\:n.wickramasinghe@unsw.edu.au)
- **Arash Shaghaghi** - [*a.shaghaghi@unsw.edu.au*](mailto\:a.shaghaghi@unsw.edu.au)
