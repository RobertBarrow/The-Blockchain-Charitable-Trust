## Phase 1

### Create "Blockchain Charitable Trustcoin" (virtual currency) and a suite of "Smart Contracts" 
_Note: initially these will be used exclusively by governments for charitable causes, such as international humanitarian aid_

#### Blockchain Charitable Trustcoin ("BTC")

* BTC would be a virtual currency on decentralised public ledger, meaning that no sovereign entity has overall control (i.e. no GCB)
* Non-fungible nature of a BTCs would give an unprecidented transparency to the use of charitable donations and international aid
* LXRs could be controlled by each GCB and reviewed periodically; this would be akin to them setting their GSC's base interest rate
* GCBs could lower the LXR to encourage charitable donations to be made in their territories 
* GCBs could raise the LXR to encourage foreign aid to be sent to their territories
* GCBs could hold a reserve of BCT in the ledger, in the same way that they might hold a reserve of physical assets (e.g. gold)

#### Entities and Smart Contracts 

##### Sovereign (controlling entity)

Functionality required

* must be able to Register and De-register as a Sovereign Entity 
* must be able to Open and Close Accounts, Funds and Ports
* must be able to Request Trustcoins (into a single, specified Fund) - to be fullfilled by another party
* must be able to Deposit and Withdraw Trustcoins from Funds and Containers, respectively)
* must be able to Deposit and Withdraw Trustcoins and Assets (from Funds and Containers, respectively)
* must be able to Transfer Trustcoins between Funds (source must belong to own account, but destination can be any account)

Associated Smart Contracts

* Register as a Sovereign Entity
* De-register as a Sovereign Entity (must not hold any BTC or Assets)

##### Central Bank (controlling entity)

Functionality required

* must be able to Register and De-register as a Central Bank
* must be able to Create and Close Accounts (as requested by another party)
* must be able to Create and Destroy BTC (using LCG at the prevailing LXR, as requested by the linked Sovereign Entity)

Associated Smart Contracts

* Register as a Central Bank (linked to a Sovereign Entity)
* De-register as a Central Bank (must not have any "Active" accounts)
* Create BTC (as requested by a Sovereign Entity)
* Destroy BTC (as requested by a Sovereign Entity)

##### Agent (participating entity)

Functionality required

* must be able to Register and De-register as an Agent
* must be able to Request the Opening and Closing of Accounts
* must be able to Open and Close Funds (within an Account)
* must be able to Request Trustcoins (into a single, specified Fund) - to be fullfilled by another party
* must be able to Register and De-register Locations
* must be able to Transfer Containers between Locations

Associated Smart Contracts

* Register as an Agent
* De-register as an Agent (Agent must not have any active Accounts)
* Request an Account
* Request Account Closure (Account must be empty)
* Open Fund
* Request Trustcoins (specified Fund)
* Close Fund (must be empty)

##### Account (ownable entity)

Purpose 

* can hold Funds and Containers
* can Request Trustcoins (into a Fund)
* can receive Assets (into a Container)

Associated Smart Contracts 

* Request an Account
* Create Account (empty)
* Close Account (must be empty)
* Request Account Closure (Account must be empty)

##### Fund (ownable entity)

Purpose

* can hold Trustcoins

Associated Smart Contracts

* Open Fund (within to a single [owned] Account)
* Close Fund (must be "empty")

##### Trustcoins (ownable / transferrable entity)

Purpose

* to represent value of funding being held or transferred

Associated Smart Contracts

* Deposit Trustcoins (into a single Fund) 
* Transfer Trustcoins (from one Fund [owned Account] to another \[any Account\])
* Withdraw Trustcoins (from a single [owned] Fund)

* Distribute coins (one to many Funds - single [owned] account)
* Amalgamate coins (many to one Funds - single [owned] account)

##### Port (ownable entity)

Purpose 

* represents single geographic (i.e. "real-world") location, usually owned by a Sovereign Entity 

Associated Smart Contracts 

* Open Port (linked to a single [own] Account)
* Close Port (must not be in use - no [active] locations are linked to this Port)

##### Location (linkable entity)

Purpose

* can represent a single geographic location, or any form of "real-world" transportation (e.g. a Container Ship or truct)
* used to keep track of Containers
* can be linked to a Port or an Agent

Associated Smart Contracts 

* Register location (linked to a single Port or Agent) 
* Update Location (link to another Port or Agent)
* De-Register location (must not be in use - i.e. no Containers are currently registered at this location)

##### Containers (ownable entity)

Purpose

* can hold Assets
* are tokens for "read-world" containers i.e. anything that can be sealed & transported

Associated Smart Contracts 

* Create Container (within a single [owned] account, registered at a single [active] Location) 
* Transfer Container (from one Location to another) # Note: "real-world" logistics will determine the status of any transfer
* Update Container location (single container, single [active] Location - registers all Assets held within to this Location)
* Retire container (must be empty)

##### Asset (ownable / transferrable entity)

Purpose

* are tokens for "real-world" Assets i.e. anything that can be purchased, transported and dontated
* can be deposited into a Container
* can be withdrawn from a Container

Associated Smart Contracts 

* Create Asset (single [owned] Account, registered at a single [active] Location)
* Deposit Asset (into a single container at the same Location) 
* Withdraw Asset (from a single container, Asset registered at same Location)
* Transfer Asset (from one [owned] Account to another [any])
* Retire Asset (owned)

* Distribute Assets (from one to many Containers - all at same Location and linked to a single [owned] Account)
* Amalgamate Assets (many to one container - all at same Location and linked to a single [owned] Account)

#### _Key_

* _BTC - Blockchain Charitable Trustcoin_
* _GCB - Government Central Bank_
* _GSC - Government's Soverign Currency [as used locally for Legal Tender]_
* _LXR - Local exchange rate [i.e. the amount of GSC that is equivalent to a single BTC]_

### Develop website to enable tracking of BTC lifecycle and Asset transfer across a distributed public ledger
