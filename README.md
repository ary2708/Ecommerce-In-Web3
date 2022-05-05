# Ecommerce-In-Web3

## Overview
Here, I have created a Smart Contract Algorithm for an E-commerce website where a buyer and seller interact with each other via a smart contract.
On abstract level, the seller can register the product he/she wants to sell and the buyer can buy the product of choice,send the money to the smart contract and confirm the status of its delivery after which the smart contract will forward the corresponding amount to the seller.

## How do they work

The contract consists of the following functions:

```registerProduct()```

<p float="left">
  <img src="https://github.com/ary2708/Ecommerce-In-Web3/blob/main/Images/registerProduct.png" />
</p>

Using this , the seller can register the product to be sold. It stores the product in the products array(of type 'Product',created using struct) made earlier.


```buy()```

<p float="left">
  <img src="https://github.com/ary2708/Ecommerce-In-Web3/blob/main/Images/buy.png"  />
</p>

Customer can buy the desired product by transferring the exact price of the product to the contract.

```delivery()```
<p float="left">
  <img src="https://github.com/ary2708/Ecommerce-In-Web3/blob/main/Images/delivery.png"  />
</p>

Once the product is delivered, customer can call this ```delivery``` function after which the contract will transfer the exact price of the product to the seller.

### Counter actions on some unwanted cases:

```destroy()```
<p float="left">
  <img src="https://github.com/ary2708/Ecommerce-In-Web3/blob/main/Images/destroy.png"  />
</p>

This function is created to prevent loss in case someone hacks the smart contract.

Let's assume the smart contract is destroyed and the buyer is unknown of it. He tries to buy a product through the contract. Now, when he transfers the ethers to the contract, they are vanished , as the smart contract does not exist.
To prevent this, I have created a ``modifier:isNotDestroyed``.
We would have faced this issue if we used the commented ```destroy()``` function instead of the one we are using now.

I have also created a ```fallback``` function for this.

## Result ##
An E-commerce smart contract algorithm is successfully created through which buyers and sellers can interact together.
