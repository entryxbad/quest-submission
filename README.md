<h1>Chapter 1</h1>
<h2>Day 1</h2>

**1. Explain what the Blockchain is in your own words.**
	Blockchain is a decentralized database that is stored simultaneously on multiple computers connected to each other on the Internet.

**2. Explain what a Smart Contract is.**
	A smart contract is a computer program that tracks and enforces obligations. Smart contracts codes are executed in the Blockchain.
	
**3. Explain the difference between a script and a transaction.**
	A transaction is a blockchain storage operation that transfers cryptoassets or other information between wallets. The transaction may charge a fee depending on which blockchain you are on. 
	The script is used to browse the data in the blockhain, it does not change it. And unlike a transaction, it doesn't charge any fees because it costs nothing.

<h2>Day 2</h2>

**1. What are the 5 Cadence Programming Language Pillars?**
1. **_Safety and Security:_** Safety is the underlying reliability of any smart contract. Security is the prevention of attacks on the network or smart contracts. Safety and security are critical in smart contracts because of the immutable nature of blockchains, and because they often deal with high-value assets.
2.  **_Clarity:_** Code needs to be easy to read, and its meaning should be as unambiguous as possible. It should also be suited for verification so that tooling can help with ensuring safety and security guarantees. 
3. **_Approachability:_** Writing code and creating programs should be as approachable as possible. Practical tooling, documentation, and examples enable developers to start creating programs quickly and effectively.
4. **_Developer Experience:_** The developer should be supported throughout the entire development lifecycle, from initial application logic to on-chain bugfixes.
5. **_Intuiting Ownership with Resources:_** Resources are a composite data type, similar to a struct, that expresses direct ownership of assets. Cadence’s resources directly tie an asset’s ownership to the account that owns it by saving the resource in the account’s storage.

**2. In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful?**
These 5 pillars allow even more developers to create secure, easy-to-read and accessible smart contracts. In this way, developers themselves will create this ecosystem.

<h1>Chapter 2</h1>
<h2>Day 1</h2>

1. <img src="images\chapter_2\day_1\contract_JT.PNG"></img>
2. <img src="images\chapter_2\day_1\script.PNG"></img>

<h2>Day 2</h2>

1. We don't call _changeGreeting_ in the script because the script only allows you to view the information, but cannot change it.
2. _AuthAccount_ gives access to the data to the account of the user signing the transaction.
3. _prepare_ phase allows you to access the user's account data. What _execute_ phase cannot do, but _execute_ phase can call functions to change data in the blockchain.
4. Added two new things inside contract. 
* Added var _myNumber_ and function _updateMyNumber_.
	<img src="images\chapter_2\day_2\init_myNimber.PNG"></img>
* Added a script that reads _myNumber_.
	<img src="images\chapter_2\day_2\script_myNumber.PNG"></img>
* Added transaction.
	<img src="images\chapter_2\day_2\transaction_number.PNG"></img>
	<img src="images\chapter_2\day_2\enter_newNumber.PNG"></img>
	<img src="images\chapter_2\day_2\answer.PNG"></img>

<h2>Day 3</h2>

1. <img src="images\chapter_2\day_3\people.PNG"></img>
2. <img src="images\chapter_2\day_3\dictionary.PNG"></img>
3. The force unwrap will get the value of the optional if it exists... 
	<img src="images\chapter_2\day_3\succes_unwrap.PNG"></img>
   ...or it will panic and abort if it doesn’t.
	<img src="images\chapter_2\day_3\panic.PNG"></img>
4. **_What the error message means, Why we're getting this error, How to fix it_**
	<img src="images\chapter_2\day_3\error.PNG"></img>

* Type mismatch error, because the expected string was _"String"_, but you got the optional string _"String?"_
* Because the dictionary returns the value we are accessing with an _optional type_.
* This error can be corrected by using the _force-unwrap operator_. Put the _"!"_ operator at the end of the _return_ string to unwrap the optional type and return the actual value.
	<img src="images\chapter_2\day_3\success.PNG"></img>

<h2>Day 4</h2>

1. **Deploy a new contract that has a Struct of your choosing.**
	
	<img src="images\chapter_2\day_4\contract.PNG"></img>

2. **Create a dictionary or array that contains the Struct you defined.**

	<img src="images\chapter_2\day_4\dictionary.PNG"></img>

3. **Create a function to add to that array/dictionary.**

	<img src="images\chapter_2\day_4\function.PNG"></img>

4. **Add a transaction to call that function in step 3.**

	<img src="images\chapter_2\day_4\transaction.PNG"></img>

5. **Add a script to read the Struct you defined.**

	<img src="images\chapter_2\day_4\script.PNG"></img>