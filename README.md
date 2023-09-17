
# Perennial V2 #2 contest details

- Join [Sherlock Discord](https://discord.gg/MABEWyASkp)
- Submit findings using the issue page in your private contest repo (label issues as med or high)
- [Read for more details](https://docs.sherlock.xyz/audits/watsons)

# Q&A

### Q: On what chains are the smart contracts going to be deployed?
One or all of the following: Ethereum L2, Arbitrum, Optimism, Base

___

### Q: Which ERC20 tokens do you expect will interact with the smart contracts? 
DSU and USDC (USDC.e on Arbitrum, native USDC on Base)
___

### Q: Which ERC721 tokens do you expect will interact with the smart contracts? 
None
___

### Q: Which ERC777 tokens do you expect will interact with the smart contracts? 
None
___

### Q: Are there any FEE-ON-TRANSFER tokens interacting with the smart contracts?

No
___

### Q: Are there any REBASING tokens interacting with the smart contracts?

No
___

### Q: Are the admins of the protocols your contracts integrate with (if any) TRUSTED or RESTRICTED?
TRUSTED
___

### Q: Is the admin/owner of the protocol/contracts TRUSTED or RESTRICTED?
Protocol admin: TRUSTED

___

### Q: Are there any additional protocol roles? If yes, please explain in detail:
Markets have Owners and Coordinators which can update parameters for that specific market - these coordinators have a large amount of flexibility within their own market but should not be able to adversely affect other markets or the overall protocol.
___

### Q: Is the code/contract expected to comply with any EIPs? Are there specific assumptions around adhering to those EIPs that Watsons should be aware of?
No
___

### Q: Please list any known issues/acceptable risks that should not result in a valid finding.
As stated above - market owners+coordinators can do many things within their markets which could adversely affect user funds within those markets. However, they should not be able to affect other markets

Flywheel being down due to external downtime - sequencer and oracle downtime does not have special case handling. Perennial also does not provide grace periods for users to cure their positions when these systems do come back up
___

### Q: Please provide links to previous audits (if any).
This is a fix review for the original Sherlock audit: https://github.com/sherlock-audit/2023-07-perennial-judging
___

### Q: Are there any off-chain mechanisms or off-chain procedures for the protocol (keeper bots, input validation expectations, etc)?
Yes - there are keepers for oracle updates, liquidations, and order types
___

### Q: In case of external protocol integrations, are the risks of external contracts pausing or executing an emergency withdrawal acceptable? If not, Watsons will submit issues related to these situations that can harm your protocol's functionality.
We want to be aware of issues that might arise from oracle or DSU integrations

___

### Q: Do you expect to use any of the following tokens with non-standard behaviour with the smart contracts?
USDC
___

### Q: Add links to relevant protocol resources
V1 Overview docs: https://docs.perennial.finance/

V2 Mechanism 1-pager: https://docs.google.com/document/d/1f-V_byFYkJdJAHMXxN2NiiDqysYhoqKzZXteee8BuIQ/edit
___



# Audit scope


[root @ d531cf7f0c1d417e9987b706092e177021a89e5d](https://github.com/equilibria-xyz/root/tree/d531cf7f0c1d417e9987b706092e177021a89e5d)
- [root/contracts/accumulator/types/Accumulator6.sol](root/contracts/accumulator/types/Accumulator6.sol)
- [root/contracts/accumulator/types/UAccumulator6.sol](root/contracts/accumulator/types/UAccumulator6.sol)
- [root/contracts/attribute/Factory.sol](root/contracts/attribute/Factory.sol)
- [root/contracts/attribute/Instance.sol](root/contracts/attribute/Instance.sol)
- [root/contracts/attribute/Kept/Kept.sol](root/contracts/attribute/Kept/Kept.sol)
- [root/contracts/attribute/Kept/Kept_Arbitrum.sol](root/contracts/attribute/Kept/Kept_Arbitrum.sol)
- [root/contracts/attribute/Kept/Kept_Optimism.sol](root/contracts/attribute/Kept/Kept_Optimism.sol)
- [root/contracts/attribute/Pausable.sol](root/contracts/attribute/Pausable.sol)
- [root/contracts/number/types/Fixed18.sol](root/contracts/number/types/Fixed18.sol)
- [root/contracts/number/types/Fixed6.sol](root/contracts/number/types/Fixed6.sol)
- [root/contracts/number/types/UFixed18.sol](root/contracts/number/types/UFixed18.sol)
- [root/contracts/number/types/UFixed6.sol](root/contracts/number/types/UFixed6.sol)
- [root/contracts/pid/types/PAccumulator6.sol](root/contracts/pid/types/PAccumulator6.sol)
- [root/contracts/pid/types/PController6.sol](root/contracts/pid/types/PController6.sol)
- [root/contracts/token/types/Token6.sol](root/contracts/token/types/Token6.sol)

[perennial-v2 @ 3e7c37d42a19f2f1c262d4059bbcafe7d37c5796](https://github.com/equilibria-xyz/perennial-v2/tree/3e7c37d42a19f2f1c262d4059bbcafe7d37c5796)
- [perennial-v2/packages/perennial-extensions/contracts/MultiInvoker.sol](perennial-v2/packages/perennial-extensions/contracts/MultiInvoker.sol)
- [perennial-v2/packages/perennial-extensions/contracts/types/TriggerOrder.sol](perennial-v2/packages/perennial-extensions/contracts/types/TriggerOrder.sol)
- [perennial-v2/packages/perennial-oracle/contracts/Oracle.sol](perennial-v2/packages/perennial-oracle/contracts/Oracle.sol)
- [perennial-v2/packages/perennial-oracle/contracts/OracleFactory.sol](perennial-v2/packages/perennial-oracle/contracts/OracleFactory.sol)
- [perennial-v2/packages/perennial-oracle/contracts/pyth/PythFactory.sol](perennial-v2/packages/perennial-oracle/contracts/pyth/PythFactory.sol)
- [perennial-v2/packages/perennial-oracle/contracts/pyth/PythOracle.sol](perennial-v2/packages/perennial-oracle/contracts/pyth/PythOracle.sol)
- [perennial-v2/packages/perennial-oracle/contracts/pyth/PythOracle_Arbitrum.sol](perennial-v2/packages/perennial-oracle/contracts/pyth/PythOracle_Arbitrum.sol)
- [perennial-v2/packages/perennial-oracle/contracts/pyth/PythOracle_Optimism.sol](perennial-v2/packages/perennial-oracle/contracts/pyth/PythOracle_Optimism.sol)
- [perennial-v2/packages/perennial-payoff/contracts/PayoffFactory.sol](perennial-v2/packages/perennial-payoff/contracts/PayoffFactory.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/Giga.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/Giga.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/Kilo.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/Kilo.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/KiloPowerHalf.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/KiloPowerHalf.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/KiloPowerTwo.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/KiloPowerTwo.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/Mega.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/Mega.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/MegaPowerTwo.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/MegaPowerTwo.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/Micro.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/Micro.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/MicroPowerTwo.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/MicroPowerTwo.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/Milli.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/Milli.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/MilliPowerHalf.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/MilliPowerHalf.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/MilliPowerTwo.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/MilliPowerTwo.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/Nano.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/Nano.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/PowerHalf.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/PowerHalf.sol)
- [perennial-v2/packages/perennial-payoff/contracts/payoff/PowerTwo.sol](perennial-v2/packages/perennial-payoff/contracts/payoff/PowerTwo.sol)
- [perennial-v2/packages/perennial-vault/contracts/Vault.sol](perennial-v2/packages/perennial-vault/contracts/Vault.sol)
- [perennial-v2/packages/perennial-vault/contracts/VaultFactory.sol](perennial-v2/packages/perennial-vault/contracts/VaultFactory.sol)
- [perennial-v2/packages/perennial-vault/contracts/lib/StrategyLib.sol](perennial-v2/packages/perennial-vault/contracts/lib/StrategyLib.sol)
- [perennial-v2/packages/perennial-vault/contracts/types/Account.sol](perennial-v2/packages/perennial-vault/contracts/types/Account.sol)
- [perennial-v2/packages/perennial-vault/contracts/types/Checkpoint.sol](perennial-v2/packages/perennial-vault/contracts/types/Checkpoint.sol)
- [perennial-v2/packages/perennial-vault/contracts/types/Mapping.sol](perennial-v2/packages/perennial-vault/contracts/types/Mapping.sol)
- [perennial-v2/packages/perennial-vault/contracts/types/Registration.sol](perennial-v2/packages/perennial-vault/contracts/types/Registration.sol)
- [perennial-v2/packages/perennial-vault/contracts/types/VaultParameter.sol](perennial-v2/packages/perennial-vault/contracts/types/VaultParameter.sol)
- [perennial-v2/packages/perennial/contracts/Market.sol](perennial-v2/packages/perennial/contracts/Market.sol)
- [perennial-v2/packages/perennial/contracts/MarketFactory.sol](perennial-v2/packages/perennial/contracts/MarketFactory.sol)
- [perennial-v2/packages/perennial/contracts/types/Global.sol](perennial-v2/packages/perennial/contracts/types/Global.sol)
- [perennial-v2/packages/perennial/contracts/types/Invalidation.sol](perennial-v2/packages/perennial/contracts/types/Invalidation.sol)
- [perennial-v2/packages/perennial/contracts/types/Local.sol](perennial-v2/packages/perennial/contracts/types/Local.sol)
- [perennial-v2/packages/perennial/contracts/types/MarketParameter.sol](perennial-v2/packages/perennial/contracts/types/MarketParameter.sol)
- [perennial-v2/packages/perennial/contracts/types/OracleVersion.sol](perennial-v2/packages/perennial/contracts/types/OracleVersion.sol)
- [perennial-v2/packages/perennial/contracts/types/Order.sol](perennial-v2/packages/perennial/contracts/types/Order.sol)
- [perennial-v2/packages/perennial/contracts/types/Position.sol](perennial-v2/packages/perennial/contracts/types/Position.sol)
- [perennial-v2/packages/perennial/contracts/types/ProtocolParameter.sol](perennial-v2/packages/perennial/contracts/types/ProtocolParameter.sol)
- [perennial-v2/packages/perennial/contracts/types/RiskParameter.sol](perennial-v2/packages/perennial/contracts/types/RiskParameter.sol)
- [perennial-v2/packages/perennial/contracts/types/Version.sol](perennial-v2/packages/perennial/contracts/types/Version.sol)

