# Gato Roboto APWorld Changelog

## v0.2.1

### Bug Fixes
- Fixed deprecated `@property` decorator causing client connection issues > Python 3.11.

## v0.2.0

### Features
- Added Linux support
- Warps that are locked will no longer display in the menu
- Healthkits are now marked as `filler`
- Checks are now held and received only while Kiki is on the ground
- Victory is now tied to the end screen after leaving in the ship

### Bug Fixes
- Fixed unlocked warps not persisting after save & quit
- Fixed Progressive Ventilation 3 button not sending a check
- Fixed Progressive Heater Core 3 not sending a check after entering from Coolant room

### Known Issues
- Can sometimes end up with more than the maximum amount of healthkits during asyncs or crashes
- Rare instance of a crash after defeating the first Hotboy
- Dialog boxes for receiving Repeater and Hopper persist on-screen until room change
- Entering a room and receiving an item at the same time can sometimes lead to Kiki getting stuck in the floor

### Logic Changes
*Please take into account existing region access rules when reading the logic changes listed below, as they are not listed.*
*Multiple logic rules are listed on separate lines.*
*'Default Logic' refers to the vanilla game logic; 'Alternate Logic' is anything else.*

#### Decoder
- Default Logic
  - [`All Prog. Events` & `Spin Jump`]
- Alternate Logic
  - [`Rocket Jumps` & `Precise Tricks` & `Missile` & `Spin Jump`]

#### West Nexus Healthkit
- Default Logic
  - [`Spin Jump` & `Phase`]
- Alternate Logic
  - [`Spin Jump` & `Rocket Jumps`]
  - [`Rocket Jumps` & `Precise Tricks` & `Coolant`]

#### East Aqueducts Healthkit
- Default Logic
  - [`>= 2 Prog. Aqueducts` & `Spin Jump`]
- Alternate Logic
  - [`>= 2 Prog. Aqueducts` & `Rocket Jumps`]
  - [`Rocket Jumps` & `Water Mech`]

#### Starboard Cartridge
- Default Logic
  - [`>= 2 Prog. Aqueducts` & `Spin Jump`]
- Alternate Logic
  - [`>= 2 Prog. Aqueducts` & `Rocket Jumps`]
  - [`Rocket Jumps` & `Water Mech`]

#### Spin Jump
- Default Logic
  - [`All Prog. Aqueducts`]
- Alternate Logic
  - [(`Spin Jump` | `Coolant`) & `Rocket Jumps` & `Water Mech`]

#### Progressive Aqueducts 1
- Default Logic
  - [`== 0 Prog. Aqueducts`]
- Alternate Logic
  - [`>= 1 Prog. Aqueducts` & (`Spin Jump` | `Rocket Jumps`)]

#### Progressive Aqueducts 2
- Default Logic
  - [`>= 1 Prog. Aqueducts`]
- Alternate Logic
  - [`Rocket Jumps` & `Water Mech`]

#### Progressive Aqueducts 3
- Default Logic
  - [`== 2 Prog. Aqueducts`]
- Alternate Logic
  - [`>= 2 Prog. Aqueducts` & `Rocket Jumps`]

#### Coolant
- Default Logic
  - [`>= 2 Prog. Heater Core` & `Phase`]
- Alternate Logic
  - [`>= 1 Prog. Heater Core` & `Phase` & `Rocket Jumps` & `Small Mech`]
  - [`>= 2 Prog. Heater Core` & `Rocket Jumps` & `Small Mech`]
  - [`Phase`]

#### Phase
- Default Logic
  - [`>= 2 Prog. Heater Core`]
- Alternate Logic
  - [`Phase`]

#### Progressive Heater Core 2
- Default Logic
  - [`>= 1 Prog. Heater Core`]
- Alternate Logic
  - [`Phase`]

#### Progressive Heater Core 3
- Default Logic
  - [`>= 2 Prog. Heater Core` & `Phase`]
- Alternate Logic
  - [`Phase`]

#### Ventilation Region Access
- Default Logic
  - [`>= 2 Prog. Heater Core` & `Spin Jump`]
- Alternate Logic
  - [`>= 2 Prog. Heater Core` & `Rocket Jumps`]

## v0.1.0-alpha
- Initial Release
