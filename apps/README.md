# Application Packages

This directory contains the Android application packages (APKs) used in the **Strutter Hardening Testing Research** project.

Both applications implement **standard SSL Pinning** using **hardcoded SSL certificate fingerprints**.  
Because of this implementation, the applications may fail to send or receive requests properly if the target server’s SSL certificate has changed since the time of compilation.

The `hardened` version includes additional runtime protections such as **Integrity Verification**, **Anti-Hooking Detection**, and **Root Detection**, while the `not_hardened` version serves as the baseline implementation with **SSL Pinning only**.

If SSL handshake or connection errors occur during testing, they are likely caused by updated certificates on the target endpoint. Rebuilding the applications with updated SSL fingerprints will restore normal communication.
