# Phase 1

## Create "Blockchain Charitable Trustcoin" (virtual currency) and a suite of "Smart Contracts" to be used by various "Entities"
_Note: initially these will be used by governments, banks and agents for charitable causes, such as international humanitarian aid_

Requirements:

### Blockchain Charitable Trustcoin ("BCT") 

Purpose:

* virtual currency used exlusively on a decentralised public ledger
* to hold value across international borders

Usage:

* BCT would be a virtual currency on decentralised public ledger, meaning that no sovereign entity has overall control (i.e. no GCB)
* Non-fungible nature of a BCTs would give an unprecidented transparency to the use of charitable donations and international aid
* LXRs could be controlled by each GCB and reviewed periodically; this would be akin to them setting their GSC's base interest rate
* GCBs could lower the LXR to encourage charitable donations to be made in their territories 
* GCBs could raise the LXR to encourage foreign aid to be sent to their territories
* GCBs could hold a reserve of BCT in the ledger, in the same way that they might hold a reserve of physical assets (e.g. gold)

### Blockchain Unique Identifier ("BUI") 

Purpose:

* unique identifiers allocated to entries created on a decentralised public ledger

Smart Contracts would use BUIs to:

* associate entities with one another (linking)
* record current ownership of assets 
* record current location of assets

### Entities and Smart Contracts 

Purpose 

* to record BCT and Assets held by participants
* to track movement of BCT and Assets between participants e.g. across international borders
 
#### Sovereign (controlling entity)

Purpose:

* to create and control Territories 
* to request and control Currencies that are used as Legal Tender \[in territories that it owns / controls\]
* to request and control Accounts
* to create and control Funds of BCT held in Accounts \[that it controls\]
* to be distribute BCT for charitable causes and international aid
* to register and control Ports that can be used for the safe transfer of Assets

Functionality required:

* must be able to Register and De-register as a Sovereign Entity
* must be able to Register and De-register Locations
* must be able to Request Currencies be Opened and Closed (GSCs)
* must be able to Request Accounts be Opened and Closed 
* must be able to Open and Close Funds and Ports
* must be able to Request Trustcoins (into a single, specified Fund) - to be fullfilled by a Central Bank, or other participant)
* must be able to Deposit and Withdraw Trustcoins from Funds
* must be able to Deposit and Withdraw Assets from Containers
* must be able to Transfer Trustcoins between Funds (source must belong to own account, but destination can be any account)

Mandatory attributes:

* blockchain unique identifier (_BUI_)
* unique name

Optional attributes:

* location (_BUI linked to an active Location_)
* central bank (_BUI linked to an active Central Bank_)

Associated Smart Contracts:

* Register Sovereign (_name_) 

  _Must supply:_
  
    1. a unique name for this Sovereign entity
  
  _Notes:_
  
    1. this registration must be approved by The Blockchain Charitable Trust

* De-register Sovereign (_BUI_)

  _Must supply:_
  
    1. the BUI of an active Sovereign entity (_self_)
  
  _Notes:_ 
  
    1. a Sovereign entity can only be de-registered by itself
    1. a Sovereign entity can only be de-registered if it holds no BCT or other Assets

* Request Currency (_name_) 

  _Supply:_
  
    1. a unique name for the requested Currency \[GSC\]
  
  _Notes:_
  
    1. this request can only be fullfilled by the Central Bank that has been linked to this Sovereign entity

* Request Currency Retirement (_BUI_)

  _Supply:_
  
    1. BUI of an active Currency \[that is to be retired\]
  
  _Notes:_
  
    1. the Currency must be one that is owned by the Sovereign entity submitting the request;
    2. this request can only fullfilled by the Central Bank that is linked to the Sovereign entity_

* Request Account (_name_) 

  _Supply:_
  
    1. a unique name for the requested Account

  _Notes:_
  
    1. this request can only be fullfilled by the Central Bank that is linked to the Sovereign entity_

* Request Account Closure (_BUI_)

  _Must supply:_
  
    1. the BUI of an empty Account \[that is to be closed / made inactive\]
    
  _Notes:_
  
    1. the Account must be owned by this Sovereign entity_
    2. the Account balance must be zero

* Open Account Fund (_name, BUI_)

  _Must supply:_
  
    1. a unique name for the Fund and the BUI of an active Account
 
  _Notes:_
 
    1. the Account must be owned by the Sovereign entity that is opening the Fund
    
* Close Account Fund (BUI)

  _Must supply:_
 
    1. the BUI of an empty fund

  _Notes:_
 
    1. the Fund must belong to an Account that is owned by the Sovereign entity that is closing the Fund

# WIP

* Request Fund Deposit (amount, BUI) - _supply amount of BCT to be created and the BUI of a Fund \[owned by Sovereign entity\] - _request can only be fullfilled by a Central Bank linked to the Sovereign entity_
* Request Fund Withdrawal (amount, BUI) - _supply amount of BCT to withdrawn \[destroyed\] and the BUI of a Fund_
  _Notes: 
    Fund must be owned by this Sovereign entity;
    request can only be fullfilled by a Central Bank linked to the Sovereign entity_

* Own Account Transfer (BUI, amount, BUI) - _supply BUI of source Fund \[in an Account owned by Sovereign entity\], amount of BCT to transfer, BUI of destination Fund \[in an Account owned by Sovereign entity\]

* Request External Transfer (BUI, amount, BUI) - _supply BUI of source Fund \[in an Account owned by Sovereign entity\], amount of BCT to transfer, BUI of destination Fund \[held in an "Active" Account of any participant\] - request can only be fullfilled by a Central Bank linked to the Sovereign entity_

* Register location (name, BUI) - _BUI linked to a single Port or Soverign entity_
* Update Location (link to another Port)

#### Territory (controllable entity)

Mandatory attributes:

* blockchain unique identifier (BUI)
* unique name

Optional attribute:

* location (linked to a single active Location)

Purpose: 

* represents a single geographic area, usually a "real-world" territory controlled by a Sovereign entity 

Associated Smart Contracts: 

* Create Territory (linked to a single [own] Account)
* Transfer Territory (must not be in use - no [active] Ports are linked to this Territory)

#### Currency (linkable entity)

Purpose:

* represents a Government's Sovereign Currency used as Legal Tender in one or more of their territories

Attributes:

* blockchain unique identifier (BUI)
* name
* origin BUI (linked to an active Sovereign entity)
* initial exchange rate (LXR against a single BCT)
* lowest exchange rate (LXR against a single BCT)
* highest exchange rate (LXR against a single BCT)
* current exchange rate (LXR against a single BCT)
* last review date
* next review date

Associated Smart Contracts:

* Register Currency (linked to a Sovereign entity)
* De-register Currency - _the linked Sovereign entity must have at least one other Currency registered_

#### Central Bank (controlling entity)

Purpose:

* to Create and Retire Currencies [GSCs]
* to Create and Close Accounts - _can be owned by other entities_
* to Set the LXR on Currencies [GSCs]
* to Create and Destroy BCT using the prevailing LXR from a source Currency [GSC] - _as requested by their Sovereign entity_
* to Transfer any BCT created into an Fund available to their Sovereign entity

Functionality required:

* must be able to Register and De-register as a Central Bank
* must be able to Create and Retire Currencies (GSCs)
* must be able to Create and Close Accounts - _as requested by other participants_
* must be able to Create and Destroy BCT - _as requested by the linked Sovereign Entity_
* must be able to Set [and Adjust] the LXR [to the GSC] (as used by the linked Sovereign Entity)

Mandatory attributes:

* blockchain unique identifier (BUI)
* name
* sovereign entity (linked to an active Sovereign entity)

Optional attributes:

* location (linked to an active Location)

Associated Smart Contracts:

* Register Central Bank (name, BUI) - _supply a unique name for the Central Bank and the BUI of an active Sovereign entity_
  _Notes: 
    registration must be approved by The Blockchain Charitable Trust;
    central banks must be linked to a single Sovereign entity

* Update Central Bank - _e.g. linking to an active Location_
* De-register Central Bank 
* Adjust Local Exchange Rate (i.e. LXR to BCT on a Currency [GSC]) - _LXRs must not be zero_
* Create Currency - _as requested by a Sovereign entity_
* Retire Currency - _as requested by a Sovereign entity_
* Create BCT (at the prevailing LXR on the source Currency) - _as requested by a Sovereign entity_
* Destroy BCT (at the prevailing LXR on the source Currency) - _as requested by a Sovereign entity_

#### Agent (participating entity)

Functionality required:

* must be able to Register and De-register as an Agent
* must be able to Request the Opening and Closing of Accounts - _to be fullfilled by a Central Bank_
* must be able to Open and Close Funds (within an Account)
* must be able to Request Trustcoins (into a single, specified Fund) - _to be fullfilled by another participant_
* must be able to Deposit and Withdraw Assets from Containers
* must be able to Register and De-register Locations
* must be able to Transfer Containers between Locations

Associated Smart Contracts:

* Register Agent
* De-register Agent (Agent must not have any active Accounts)
* Request Account
* Request Account Closure (Account must be empty)
* Open Fund
* Request Trustcoins (specified Fund)
* Close Fund (must be empty)

#### Account (ownable entity)

Purpose: 

* can hold Funds and Containers
* can Request Trustcoins (into a Fund)
* can receive Assets (into a Container)

Associated Smart Contracts: 

* Request Account
* Request Account Closure (Account must be empty)
* Create Account (empty)
* Close Account (must be empty)

#### Fund (ownable entity)

Purpose:

* can hold Trustcoins

Associated Smart Contracts

* Open Fund (within to a single [owned] Account)
* Close Fund (must be "empty")

#### Trustcoins (ownable / transferrable entity)

Purpose:

* to represent value of funding being held or transferred

Associated Smart Contracts

* Deposit Trustcoins (into a single Fund) 
* Transfer Trustcoins (from one Fund [owned Account] to another \[any Account\])
* Withdraw Trustcoins (from a single [owned] Fund)

* Distribute Trustcoins (one to many Funds - in a single [owned] account)
* Amalgamate Trustcoins (many to one Funds - in a single [owned] account)

#### Port (controllable entity)

Mandatory attributes:

* blockchain unique identifier (BUI)
* location (linked to an active Location)

Purpose: 

* represents a single geographic location, usually a "real-world" Port in territory controlled by a Sovereign entity 

Associated Smart Contracts: 

* Open Port (linked to a single [own] Account)
* Close Port (must not be in use - no [active] locations are linked to this Port)

#### Location (linkable entity)

Purpose:

* can represent a single geographic location, or any form of "real-world" transportation (e.g. a Container Ship or truct)
* used to keep track of Containers
* can be linked to a Port or an Agent

Associated Smart Contracts: 

* Register location (linked to a single Port or Agent) 
* Update Location (link to another Port or Agent)
* De-Register location (must not be in use - i.e. no Containers are currently registered at this location)

#### Containers (ownable entity)

Purpose:

* can hold Assets
* are tokens for "read-world" containers i.e. anything that can be sealed & transported

Associated Smart Contracts: 

* Create Container (within a single [owned] account, registered at a single [active] Location) 
* Transfer Container (from one Location to another) # Note: "real-world" logistics will determine the status of any transfer
* Update Container location (single container, single [active] Location - registers all Assets held within to this Location)
* Retire container (must be empty)

#### Asset (ownable / transferrable entity)

Purpose:

* are tokens for "real-world" Assets i.e. anything that can be purchased, transported and dontated
* can be deposited into a Container
* can be withdrawn from a Container

Mandatory attributes:

* unique identifier (BAT)
* source account (link to an Account)
* source location (link to a Location)
* description
* unit of measure (UOM)
* quantity
* creation date
* current location (link to an active Location)
* current owner (link to an active Account)

Optional attributes:

* intended destination (link to an active Location)
* intended recipient (link to an active Account)
* dimensions
* weight
* expiry date

Associated Smart Contracts:

* Create Asset (single [owned] Account, registered at a single [active] Location)
* Deposit Asset (into a single container at the same Location) 
* Withdraw Asset (from a single container, Asset registered at same Location)
* Transfer Asset (from one [owned] Account to another [any])
* Retire Asset (owned)

* Distribute Assets (from one to many Containers - all at same Location and linked to a single [owned] Account)
* Amalgamate Assets (many to one container - all at same Location and linked to a single [owned] Account)

### _Key_

* _BCT - Blockchain Charitable Trustcoin_
* _BUI - Blockchain Unique Identifier_
* _GCB - Government Central Bank_
* _GSC - Government's Soverign Currency [as used locally for Legal Tender]_
* _LXR - Local exchange rate [i.e. the amount of GSC that is equivalent to a single BCT]_
* _UOM - Unit of Measure_

## Develop website to enable tracking of BCT lifecycle and Asset transfer across a distributed public ledger
