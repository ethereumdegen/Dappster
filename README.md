# Dappster
Like Napster... but with the Blockchain



## Tech Doc

### The Premise

  Traditional filesharing platforms have failed and been censored because they are centralized.  Now, with the network of trust and value called Ethereum, the community can come together and build a decentralized premium file sharing service that rewards seeders using micropayments.  This would ideally use some form of payment channels.
  
  This specificaion calls for a native software application (probably in Electron so as to be simple and cross-platform) that has an integrated light Ethereum wallet (eth-lightwallet) and integrated torrenting system similar to Transmission.  There will be an integrated browser that will allow the user to search (by name) through a list of 'magnet links' that had been stored to a Solidity Smart Contract by other members of the community.  We can refer to these as 'Magnet Listings.'
  
### The Magnet Listing 

A magnet listing will be an information store on the Ethereum blockchain that contains:
1. The Magnet Link for the file
2. The hash of the file
3. A name for the file
4. A description for the file (optional)
5. A comma separated list of searchable keywords for the file 
6. The filesize of the file in kilobytes, rounded up
7. A public address for donations (optional..to eventually make up for gas costs associated with posting)

### The Smart Contract

1. Has a function for storing a new Magnet Listing (will cost a small amount of ether to cover gas)
2. Has a function for donating to a Magnet Listing and will save a small record of this (acts as a simple reputation system) 
3. Has a function for leaving comments on a Magnet Listing (optional)
4. May have some other functions ? 

### Dappster Native Software Application

 Written in Electron (or built on top of Parity if parity becomes more sophisticated), this software will have different tabs and an integrated Eth-lightwallet so currency can be loaded into it.  
 
 1. The 'Magnet Listing Post' tab will allow a user to post a magnet listing by selecting a file from their harddrive, giving the file a name and description, and adding a public address for donations.  The longer the name and description, the higher the gas costs may be.  This will interact with the smart contract to store this record on the blockchain.
 2. The 'Magnet Listing Browse' tab will allow users to search the blockchain for posted Magnet Listings.  The users will be able to read the names and descriptions.  They will also be able to see how much currency was donated to this Magnet Listing via the smart contract.  
 3. The 'Seeding/Leeching' tab shows which files are being seeded or leeched to other users.  Seeders can publicly display their public address so that leechers can donate to them if they want to.   Optional functionality could be added in that makes seeders upload faster to recipients who have donated more to them.  Seeders could also choose to ONLY upload to leechers who have donated to them.  
 
 
 ### Other Thoughts
 This would need to be a native software application so that it can be censorship resistant.  All state-data would be saved on the blockchain and the code would be open source so the data and code would both be impervious to attack.  Please feel free to expand upon these ideas. 
 
 If uploading viruses becomes prevalent, the donation and commenting system would be used more to promote the good listings and to flag the bad listings.  
 
 Anonimity could be added by integrating ZKSnarks and a VPN service such as Mysterium.  
