# OGFN-Matchmaker
Works for Reload Backend, RebootGS, and should work for any backend or GS tbh.
# GS SIDED CODE: 
#include <iostream>
#include <curl/curl.h>

void mm(const std::string& status) {
    const std::string base_url = "http://IP:PORT/";
    const std::string url = base_url + status;

    CURL* curl = curl_easy_init();
    if (!curl) {
        throw std::runtime_error("Failed to initialize CURL.");
    }

    curl_easy_setopt(curl, CURLOPT_URL, url.c_str());
    curl_easy_setopt(curl, CURLOPT_FOLLOWLOCATION, 1L);
    curl_easy_setopt(curl, CURLOPT_TIMEOUT, 10L);

    CURLcode res = curl_easy_perform(curl);

    curl_easy_cleanup(curl);
}

then just use it with this:
mm("start");

Put ts in api.h:

void mm(const std::string& status);


# Roadmap:
Better how to use ✅
