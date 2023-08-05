# Use Case Diagram for the ATM System
Let’s build the use case diagram of the ATM and understand the relationship between its different components.

First, we’ll define the different elements of our ATM design, followed by the complete use case diagram of the system.

## System
Our system is an "ATM."

## Actors
Let’s define the main actors of our ATM system.

### Primary actors
Cardholder: This is the primary actor of the ATM who inserts or removes the ATM card, performs or cancels the transaction, and changes the PIN.


### Secondary actors
- Card issuer: This actor verifies the cardholder's identity, checks for sufficient funds, checks the cardholder's account transaction limit, and blocks/unblocks the cardholder's account.

- System: This actor checks for sufficient funds in the ATM, checks the ATM’s transaction limit, and verifies the cardholder's identity. This actor also returns the card and dispenses the amount and receipts.

- Operator: The operator is responsible for starting and shutting down the system. It can refill printer receipts and cash dispensers.

## Use Cases
In this section, we will define the use cases for the ATM. We have listed the use cases according to their respective interactions with a particular actor.

### Cardholder
- Insert card: To insert an ATM card into ATM

- Transaction: To perform an operation—balance inquiry, deposit, fund transfer, or cash withdrawal

- Change pin: To change the PIN of the ATM card

- Cancel transaction: To cancel a transaction

### Card issuer
- Verifying the cardholder's identity: To validate the card and cardholder's bank account details

- Check sufficient funds in account: To check if the cardholder's bank account has more or equal funds than the fund being withdrawn or transferred

- Check account transaction limits: To check if the transaction limits of the cardholder's bank account are more or equal to the funds being withdrawn or transferred

- Block/Unblock account: To block or unblock the cardholder's bank account

### System
- Verifying the cardholder's identity: To validate the card and cardholder's bank account details

- Check sufficient funds in ATM: To check if the ATM has more or equal funds than the fund being withdrawn or transferred

- Check ATM withdrawal limits: To check if the transaction limits of the ATM are more or equal to the funds being withdrawn or transferred

- Return card: To return the card after completing or canceling the transaction

- Dispense money: To dispense cash in case of cash withdrawal from an ATM

- Dispense receipt: To dispense cash after completing the transaction

### Operator
- System startup/shutdown: To start and shutdown the ATM session

- Refill printer receipts: To refill the paper in the printer

- Refill cash dispenser: To refill the cash in the dispenser

## Relationships
This section describes the relationships between and among actors as well as their use cases.

GeneralizationThe “Transaction” use case has a generalization relationship with the “Balance Inquiry,” “Deposit,” “Transfer,” and “Cash withdrawal,” because a cardholder can use any of these options to perform a transaction.

### Associations
The table below shows the association relationship between actors and their use cases.
```
Cardholder                    Card issuer                                      System                                      Operator

Change PIN                    Check for sufficient funds in account            verifying the cardholder's identity         System startup/ shutdown

Insert card                   Check cardholder account transection limits      Check ATM withdraw limits                   Refill printer receipts

Cancel transaction            Block/Unblock account                            Check for sufficient funds in ATM           Refill cash dispenser

Transaction                   Verify the cardholder's identity                 Return card

                                                                               Dispense money

                                                                               Dispense receipt
```
### Extend
The “Transaction” use case has an extend relationship with the “Dispense receipt” use case because we have the option to get a receipt in the case of transactions.


### Include
- When the cardholder inserts the card into the ATM, both the bank and card issuer verify the card and the cardholder's account. Therefore, the “Insert card” use case has an include relationship with the “Verifying the cardholder's identity” use case.

- When the cardholder performs a fund transfer from an ATM, the card issuer verifies two things—if the cardholder's bank account has sufficient funds and if the amount being transferred is within its account's transaction limits. Therefore, the “Transfer” use case has an include relationship with both “Check sufficient funds in account” and “Check account transaction limits.”

- When the cardholder withdraws cash from an ATM, the card issuer verifies two things—if the cardholder's bank account has sufficient funds and if the amount being withdrawn is within its account's transaction limits. The bank also verifies two things—if the ATM has sufficient funds and if the amount being withdrawn is within ATM's withdrawal limits. Therefore, the “Cash withdrawal” use case has an include relationship with “Check sufficient funds in the account,” “Check account transaction limits,” “Check sufficient funds in ATM,” and “Check ATM withdrawal limits.”

- The last cash withdrawal process is the system depositing the money. Therefore, the “Cash Withdrawal” use case has an include relationship with the “Dispense money’ use case.

- When a transaction is performed or canceled, the ATM card is ejected by the ATM. Therefore, both the “Transaction” use case and the “Cancel Transaction” use case have an include relationship with the “Return card” use case.

## Use case diagram

[The use case diagram of the ATM system](./atm.png)
