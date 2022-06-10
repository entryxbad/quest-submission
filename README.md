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

<h1>Chapter 3</h1>
<h2>Day 1</h2>

1. **List 3 reasons why structs are different from resources.**

* Resources cannot be copied only move
* Resources cannot be overwritten
* Resources can only be created within a contract

2. **Describe a situation where a resource might be better to use than a struct.** 
The resource is best used as an example of the NFT. Because Cadence guarantees that the resource will not be lost or overwritten unless the developer literally wants to delete it.

3. **What is the keyword to make a new resource?** 
Create

4. **Can a resource be created in a script or transaction?**
No. A resource can only be created within a contract.

5. **What is the type of the resource below?**
    	
		pub resource Jacob {

		}

@Jacob

6. **Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them.**

		pub contract Test {

			// Hint: There's nothing wrong here ;)
			pub resource Jacob {
				pub let rocks: Bool
				init() {
					self.rocks = true
				}
			}

			pub fun createJacob(): Jacob { // there is 1 here
				let myJacob = Jacob() // there are 2 here
				return myJacob // there is 1 here
			}
		}
_Bug fixes:_
		
		pub contract Test {

			// Hint: There's nothing wrong here ;)
			pub resource Jacob {
				pub let rocks: Bool
				init() {
					self.rocks = true
				}
			}

			pub fun createJacob(): @Jacob { // there is 1 here
				let myJacob <- create Jacob() // there are 2 here
				return <- myJacob // there is 1 here
			}
		}

<h2>Day 2</h2>

1. <img src="images\chapter_3\day_2\resources.PNG"></img>

<h2>Day 3</h2>

1. <img src="images\chapter_3\day_3\ref_func.PNG"></img>

2. <img src="images\chapter_3\day_3\ref_script.PNG"></img>

3. References are very useful because with them we can get information without moving resources around.

<h2>Day 4</h2>

1. There are 3 kinds of interfaces: resource, structure and contract. You need interfaces to restrict access to parts of the resource and to specify requirements when implementing something.

2. <img src="images\chapter_3\day_4\interface.PNG"></img>

3. **How would we fix this code?**

		pub contract Stuff {

			pub struct interface ITest {
			pub var greeting: String
			pub var favouriteFruit: String
			}

			// ERROR:
			// `structure Stuff.Test does not conform 
			// to structure interface Stuff.ITest`
			pub struct Test: ITest {
			pub var greeting: String

			pub fun changeGreeting(newGreeting: String): String {
				self.greeting = newGreeting
				return self.greeting // returns the new greeting
			}

			init() {
				self.greeting = "Hello!"
			}
		}

			pub fun fixThis() {
			let test: Test{ITest} = Test()
			let newGreeting = test.changeGreeting(newGreeting: "Bonjour!") // ERROR HERE: `member of restricted type is not accessible: changeGreeting`
			log(newGreeting)
			}
		}
_Corrections:_

		pub contract Stuff {

			pub struct interface ITest {
			pub var greeting: String
			pub var favouriteFruit: String
			pub fun changeGreeting(newGreeting: String): String // add function changeGreeting
			}

			pub struct Test: ITest {
			pub var greeting: String
			pub var favouriteFruit: String // add variable favouriteFruit

			pub fun changeGreeting(newGreeting: String): String {
				self.greeting = newGreeting
				return self.greeting 
			}

			init() {
				self.greeting = "Hello!"
				self.favouriteFruit = "Apple" // initialize favouriteFruit
			}
		}

			pub fun fixThis() {
			let test: Test{ITest} =  Test()
			let newGreeting = test.changeGreeting(newGreeting: "Bonjour!")
			log(newGreeting)
			}
		}

<h2>Day 5</h2>

1. 
		access(all) contract SomeContract {
			pub var testStruct: SomeStruct

			pub struct SomeStruct {

				//
				// 4 Variables
				//

				pub(set) var a: String

				pub var b: String

				access(contract) var c: String

				access(self) var d: String

				//
				// 3 Functions
				//

				pub fun publicFunc() {}

				access(contract) fun contractFunc() {}

				access(self) fun privateFunc() {}


				pub fun structFunc() {
					/**************/
					/*** AREA 1 ***/
					/**************/
				}

				init() {
					self.a = "a"
					self.b = "b"
					self.c = "c"
					self.d = "d"
				}
			}

			pub resource SomeResource {
				pub var e: Int

				pub fun resourceFunc() {
					/**************/
					/*** AREA 2 ***/
					/**************/
				}

				init() {
					self.e = 17
				}
			}

			pub fun createSomeResource(): @SomeResource {
				return <- create SomeResource()
			}

			pub fun questsAreFun() {
				/**************/
				/*** AREA 3 ****/
				/**************/
			}

			init() {
				self.testStruct = SomeStruct()
			}
		}
_Answers:_

Area 1: Read/Write - a, b, c, d; Called - publicFunc, ContractFunc, privateFunc.
Area 2: Read - a, b, c; Write - a; Called - publicFunc, ContractFunc.
Area 3: Read - a, b, c; Write - a; Called - publicFunc, ContractFunc.
Area 4: Read - a, b; Write - a; Called - publicFunc.