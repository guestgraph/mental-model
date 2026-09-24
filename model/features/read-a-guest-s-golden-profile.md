---
source: Local
products:
  - GuestGraph Engine
concepts:
  - Golden profile
  - Guest
  - Source record
---

# Read a guest's golden profile

> One profile per guest, with the source records behind it, found by guest id or by any identifier the guest carries.

## Description

A guest is read as one golden profile, computed from its records field by field, together with the records themselves. A caller holding only an email or a phone can find the guest by it. It is read only: a profile is never edited, and a correction enters as a record.
