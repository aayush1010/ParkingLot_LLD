# Parking Lot — Low Level Design

## Problem Statement

Design a parking lot that:
1. Supports multiple vehicle types (Small, Medium, Large) — **Done**
2. Models a parking ticket issued on entry, carrying vehicle + entry time — **Done**
3. Prices each vehicle type differently (Small = 50, Medium = 100, Large = 150) — **Done**
4. Lets a customer pay and exit against their ticket — **In progress**
5. Tracks free/occupied spots per floor — **TODO**
6. Rejects entry when the lot is full — **TODO**

## Design

- **`Vehicle`** — type (`VehicleType` enum) and an auto-generated id.
- **`ParkingTicket`** — issued per vehicle on entry; stamps entry time and computes the fee from `ParkingRate` on exit.
- **`Customer`** — holds a vehicle + ticket and settles payment via `DoPayment()`.
- **`Enums`** — `VehicleType`, `ParkingSpotType`, and `ParkingRate` are kept separate so spot allocation and pricing can evolve independently of the vehicle model.

This is a work in progress — the entity/rate model is in place, but spot allocation, floor-level availability boards, and the entry/exit flow in `Program.cs` aren't wired up yet.

## Tech

C# / .NET Core
