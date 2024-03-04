
# Telcoin Platform Audit Update contest details

- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)

# Q&A

### Q: On what chains are the smart contracts going to be deployed?
Ethereum and Polygon
___

### Q: Which ERC20 tokens do you expect will interact with the smart contracts? 
Any
___

### Q: Which ERC721 tokens do you expect will interact with the smart contracts? 
None
___

### Q: Do you plan to support ERC1155?
There is no ERC1155 support.
___

### Q: Which ERC777 tokens do you expect will interact with the smart contracts? 
None
___

### Q: Are there any FEE-ON-TRANSFER tokens interacting with the smart contracts?

There are no Fee-On-Transfer tokens, however swaps and aggregators will receive fees for their services by way of swap results.
___

### Q: Are there any REBASING tokens interacting with the smart contracts?

NO
___

### Q: Are the admins of the protocols your contracts integrate with (if any) TRUSTED or RESTRICTED?
TRUSTED for all
___

### Q: Is the admin/owner of the protocol/contracts TRUSTED or RESTRICTED?
TRUSTED for all
___

### Q: Are there any additional protocol roles? If yes, please explain in detail:
There are a number of roles (MINTER_ROLE, BURNER_ROLE, SUPPORT_ROLE, etc) all of which provide access to certain functions. The holders of these roles are trusted. Input into these functions from these trusted role can be assumed to be working in the best interest in Telcoin. Accidental parameters that put the contract/transaction in an adverse state would be a valid issue, however centralization or for example, infinite minting, issues are not valid however. 
___

### Q: Is the code/contract expected to comply with any EIPs? Are there specific assumptions around adhering to those EIPs that Watsons should be aware of?
All tokens are expected to be ERC20s, for storage both ERC1967 and EIP7201 for proxy safe contracts.
___

### Q: Please list any known issues/acceptable risks that should not result in a valid finding.
N/A
___

### Q: Please provide links to previous audits (if any).
https://audits.sherlock.xyz/contests/49
___

### Q: Are there any off-chain mechanisms or off-chain procedures for the protocol (keeper bots, input validation expectations, etc)?
The stablecoin in the repo will be minted/burned to keep the current supply equal to that of the backing currency off chain. Rates and conversion between different stablecoins are provided by off-chain FX rates services and are trusted. The same goes for erc20 trades through off chain aggregators. 
___

### Q: In case of external protocol integrations, are the risks of external contracts pausing or executing an emergency withdrawal acceptable? If not, Watsons will submit issues related to these situations that can harm your protocol's functionality.
If actions such as pausing will cause issues with the platform operating then yes, these issues should be submitted. However this should only be included if a protocol prevents issues greater than the service they provide. For example, if all aggregators were to stop providing service then it is known that swapping may no be available, however this should not affect any other aspect of the platform other than swapping. 
___

### Q: Do you expect to use any of the following tokens with non-standard behaviour with the smart contracts?
Blacklisting on the stablecoin contract.
___

### Q: Add links to relevant protocol resources
https://docs.1inch.io
https://0x.org/docs/
___



# Audit scope


[telcoin-contracts @ 817aff2da48312414a32f3723f2791f52491ae8d](https://github.com/telcoin/telcoin-contracts/tree/817aff2da48312414a32f3723f2791f52491ae8d)
- [telcoin-contracts/contracts/bridge/BridgeRelay.sol](telcoin-contracts/contracts/bridge/BridgeRelay.sol)
- [telcoin-contracts/contracts/external/openzeppelin/ClonableBeaconProxy.sol](telcoin-contracts/contracts/external/openzeppelin/ClonableBeaconProxy.sol)
- [telcoin-contracts/contracts/factories/ProxyFactory.sol](telcoin-contracts/contracts/factories/ProxyFactory.sol)
- [telcoin-contracts/contracts/factories/library/FactoryStorage.sol](telcoin-contracts/contracts/factories/library/FactoryStorage.sol)
- [telcoin-contracts/contracts/stablecoin/Stablecoin.sol](telcoin-contracts/contracts/stablecoin/Stablecoin.sol)
- [telcoin-contracts/contracts/stablecoin/StablecoinHandler.sol](telcoin-contracts/contracts/stablecoin/StablecoinHandler.sol)
- [telcoin-contracts/contracts/util/abstract/Blacklist.sol](telcoin-contracts/contracts/util/abstract/Blacklist.sol)
- [telcoin-contracts/contracts/swap/AmirX.sol](telcoin-contracts/contracts/swap/AmirX.sol)


