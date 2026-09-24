---
source: Local
products:
  - Apaleo Connector
concepts:
  - Source object
  - Connection
  - Source system
---

# Bring reservations and bookings into the graph

> The guests on a hotel's reservations and the bookers on its bookings reach the graph as their PMS changes, without anyone exporting anything.

## Description

For each connection the connector subscribes to the PMS's events, fetches the reservation or booking an event names and submits one observation per person on that version, and only when a person on it changed. A periodic reconciliation and a full sync when needed cover what the events miss, and a delivery that fails is kept and retried rather than dropped. It holds the guest id each person resolved to and re-reads those ids when merges retire them. It writes nothing back into the PMS, and it never chooses among several current guests.
