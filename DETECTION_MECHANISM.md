## Overview
This document describes the detection mechanisms implemented in the **hardened version** of the Flutter-based Android application.

A **native Kotlin plugin** is integrated into the application to provide runtime protection through three primary detection components:

- Integrity Verification  
- Anti-Hooking Detection  
- Root Detection

If any detection is triggered, the application will immediately terminate to prevent execution under a potentially compromised environment.

---

## Integrity Verification
**Purpose:** detect APK repackaging or unauthorized modification.

**Mechanism (general):**
- The Kotlin-based plugin validates the application's signing certificate at runtime.  
- The obtained signing certificate is compared against the original build-time signature embedded within the app.  
- If the signatures do not match, the plugin interprets it as a modified or repackaged APK and forces the app to quit.

---

## Anti-Hooking Detection
**Purpose:** detect runtime instrumentation or hooking frameworks (e.g., Frida, Xposed) that may alter or inspect app behavior.

The plugin performs multiple heuristic checks, and if any are positive, the app terminates immediately:

1. Check for Frida-related files.  
2. Check for Frida server ports.  
3. Check for Frida processes.  
4. Check memory maps for Frida libraries.  
5. Check file descriptors and named pipes.  
6. Check thread names.  
7. Check environment variables.  
8. Check for Frida-related apps.  
9. Check native libraries.  
10. Check system properties.

---

## Root Detection
**Purpose:** identify devices with root access or modified environments that may compromise app integrity.

The plugin performs layered root checks. If any indicator is detected, the app terminates:

1. Check for root-related files (e.g., `su`, Magisk paths).  
2. Check for potentially dangerous or root management apps.  
3. Check for root cloaking apps.  
4. Check build tags (e.g., `test-keys`).  
5. Try executing the `su` command.  
6. Check for root via shell commands.  
7. Check Xposed/LSPosed framework presence.  
8. Check system properties.  
9. Check native libraries and hooks.  
10. Check SELinux status.  
11. Check mount points.  
12. Check developer options & USB debugging.
