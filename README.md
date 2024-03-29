# Cookie-Enabled Chromium.

This is a helper directory for Chromium build with network cookies support.
You can skip build-from-source and download a cookie-enabled Chromium image.

## Build from source
Follow the standard Chromium instructions to download, sync, and build. Then apply these patches and rebuild (use the shared_libraries flag for faster builds during development). 
I feel that forking straight from chromium might break the multiple repos and
build, so I just list the necessary patches here for cookie support instead of 
maintaining my own branches.

### Chromium Patches (apply from chromium/src)

0001-Add-network-cookies-to-HTTP-CONNECT-for-http-proxied.patch
0002-Add-network-cookie-support-for-HTTPS-requests.patch

(Forked from chromium source at 9bd6368468d43c5eb586a108233a2cf4ab50c9ce)

### Boring SSL patches (apply from chromium/src/third_party/boringssl/src)

0001-Add-support-for-network-cookie-extension.patch

(Forked from boringssl at 209b2562235f7dab66b8260624e7b3c5b00d14a6

## Download cookie-enabled Chromium.

### Ubuntu (tested with 12.04 and 14.04)
[Download](http://anylink.stanford.edu)

## Try it

(optionally) unzip and run!
```
tar xvfz cookie_chromium.tar.gz
cd Release
./chrome --disable-setuid-sandbox
```


