# Ordinal Theory Handbook

Ordinal Theory Handbook

Introduction

This handbook is a guide to ordinal theory. Ordinal theory concerns itself with satoshis, giving them individual identities and allowing them to be tracked, transferred, and imbued with meaning.

Satoshis, not bitcoin, are the atomic, native currency of the Bitcoin network. One bitcoin can be sub-divided into 100,000,000 satoshis, but no further.

Ordinal theory does not require a sidechain or token aside from Bitcoin, and can be used without any changes to the Bitcoin network. It works right now.

Ordinal theory imbues satoshis with numismatic value, allowing them to be collected and traded as curios.

Individual satoshis can be inscribed with arbitrary content, creating unique Bitcoin-native digital artifacts that can be held in Bitcoin wallets and transferred using Bitcoin transactions. Inscriptions are as durable, immutable, secure, and decentralized as Bitcoin itself.

Other, more unusual use-cases are possible: off-chain colored-coins, public key infrastructure with key rotation, a decentralized replacement for the DNS. For now though, such use-cases are speculative, and exist only in the minds of fringe ordinal theorists.

For more details on ordinal theory, see the overview. For more details on inscriptions, see inscriptions.

When you're ready to get your hands dirty, a good place to start is with inscriptions, a curious species of digital artifact enabled by ordinal theory.

Links

GitHub\
BIP\
Discord\
Mainnet Block Explorer Signet Block Explorer

https://docs.ordinals.com/print.html 1/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Videos

Ordinal Theory Explained: Satoshi Serial Numbers and NFTs on Bitcoin Ordinals Workshop with Rodarmor\
Ordinal Art: Mint Your own NFTs on Bitcoin w/ @rodarmor

https://docs.ordinals.com/print.html 2/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Theory Overview

Ordinals are a numbering scheme for satoshis that allows tracking and transferring individual sats. These numbers are called ordinal numbers. Satoshis are numbered in the order in which they're mined, and transferred from transaction inputs to transaction outputs first-in-first-out. Both the numbering scheme and the transfer scheme rely on order, the numbering scheme on the order in which satoshis are mined, and the transfer scheme on the order of transaction inputs and outputs. Thus the name, ordinals.

Technical details are available in the BIP.\
Ordinal theory does not require a separate token, another blockchain, or any changes to

Bitcoin. It works right now.\
Ordinal numbers have a few different representations:

Integer notation: 2099994106992659 The ordinal number, assigned according to the order in which the satoshi was mined.

Decimal notation: 3891094.16797 The first number is the block height in which the satoshi was mined, the second the offset of the satoshi within the block.

Degree notation: 3°111094′214′′16797′′′ . We'll get to that in a moment.\
Percentile notation: 99.99971949060254% . The satoshi's position in Bitcoin's supply,

expressed as a percentage.

Name: satoshi . An encoding of the ordinal number using the characters a through z . Arbitrary assets, such as NFTs, security tokens, accounts, or stablecoins can be attached to

satoshis using ordinal numbers as stable identifiers.

Ordinals is an open-source project, developed on GitHub. The project consists of a BIP describing the ordinal scheme, an index that communicates with a Bitcoin Core node to track the location of all satoshis, a wallet that allows making ordinal-aware transactions, a block explorer for interactive exploration of the blockchain, functionality for inscribing satoshis with digital artifacts, and this manual.

https://docs.ordinals.com/print.html 3/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Rarity

Humans are collectors, and since satoshis can now be tracked and transferred, people will naturally want to collect them. Ordinal theorists can decide for themselves which sats are rare and desirable, but there are some hints...

Bitcoin has periodic events, some frequent, some more uncommon, and these naturally lend themselves to a system of rarity. These periodic events are:

Blocks: A new block is mined approximately every 10 minutes, from now until the end of time.

Difficulty adjustments: Every 2016 blocks, or approximately every two weeks, the Bitcoin network responds to changes in hashrate by adjusting the difficulty target which blocks must meet in order to be accepted.

Halvings: Every 210,000 blocks, or roughly every four years, the amount of new sats created in every block is cut in half.

Cycles: Every six halvings, something magical happens: the halving and the difficulty adjustment coincide. This is called a conjunction, and the time period between conjunctions a cycle. A conjunction occurs roughly every 24 years. The first conjunction should happen some time in 2032.

This gives us the following rarity levels:

: Any sat that is not the first sat of its block : The first sat of each block

: The first sat of each difficulty adjustment period : The first sat of each halving epoch

: The first sat of each cycle mythic : The first sat of the genesis block

Which brings us to degree notation, which unambiguously represents an ordinal number in a way that makes the rarity of a satoshi easy to see at a glance:

Ordinal theorists often use the terms "hour", "minute", "second", and "third" for A, B, C, and D, respectively.

common

uncommon

rare

epic

legendary

A°B′C′′D′′′\
│ │ │ ╰─ Index of sat in the block\
│ │ ╰─── Index of block in difficulty adjustment period │ ╰───── Index of block in halving epoch\
╰─────── Cycle, numbered starting from 0

https://docs.ordinals.com/print.html 4/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Now for some examples. This satoshi is common:

This satoshi is uncommon:

This satoshi is rare:

This satoshi is epic:

This satoshi is legendary:

And this satoshi is mythic:

1°1′1′′1′′′\
│ │ │ ╰─ Not first sat in block\
│ │ ╰─── Not first block in difficutly adjustment period │ ╰───── Not first block in halving epoch\
╰─────── Second cycle

1°1′1′′0′′′\
│ │ │ ╰─ First sat in block\
│ │ ╰─── Not first block in difficutly adjustment period │ ╰───── Not first block in halving epoch\
╰─────── Second cycle

1°1′0′′0′′′\
│ │ │ ╰─ First sat in block\
│ │ ╰─── First block in difficulty adjustment period │ ╰───── Not the first block in halving epoch ╰─────── Second cycle

1°0′1′′0′′′\
│ │ │ ╰─ First sat in block\
│ │ ╰─── Not first block in difficulty adjustment period │ ╰───── First block in halving epoch\
╰─────── Second cycle

1°0′0′′0′′′\
│ │ │ ╰─ First sat in block\
│ │ ╰─── First block in difficulty adjustment period │ ╰───── First block in halving epoch\
╰─────── Second cycle

0°0′0′′0′′′\
│ │ │ ╰─ First sat in block\
│ │ ╰─── First block in difficulty adjustment period │ ╰───── First block in halving epoch\
╰─────── First cycle

https://docs.ordinals.com/print.html 5/46

2/12/23, 12:14 PM Ordinal Theory Handbook

If the block offset is zero, it may be omitted. This is the uncommon satoshi from above:

Rare Satoshi Supply Total Supply

: 2.1 quadrillion : 6,929,999

: 3437 : 32

:5 mythic : 1

Current Supply

: 1.9 quadrillion : 745,855

: 369 :3

:0 mythic : 1

At the moment, even uncommon satoshis are quite rare. As of this writing, 745,855 uncommon satoshis have been mined - one per 25.6 bitcoin in circulation.

Names

Each satoshi has a name, consisting of the letters A through Z, that get shorter the further into the future the satoshi was mined. They could start short and get longer, but then all the good, short names would be trapped in the unspendable genesis block.

```
1°1′1′′
│ │ ╰─ Not first block in difficutly adjustment period
│ ╰─── Not first block in halving epoch
╰───── Second cycle
```

common

uncommon

rare

epic

legendary

common

uncommon

rare

epic

legendary

https://docs.ordinals.com/print.html 6/46

2/12/23, 12:14 PM Ordinal Theory Handbook

As an example, 1905530482684727°'s name is "iaiufjszmoba". The name of the last satoshi to be mined is "a". Every combination of 10 characters or less is out there, or will be out there, some day.

Exotics

Satoshis may be prized for reasons other than their name or rarity. This might be due to a quality of the number itself, like having an integer square or cube root. Or it might be due to a connection to a historical event, such as satoshis from block 477,120, the block in which SegWit activated, 2099999997689999°, the last satoshi that will ever be mined.

Such satoshis are termed "exotic". Which satoshis are exotic and what makes them so is subjective. Ordinal theorists are are encouraged to seek out exotics based on criteria of their own devising.

Inscriptions

Satoshis can be inscribed with arbitrary content, creating Bitcoin-native digital artifacts. Inscribing is done by sending the satoshi to be inscribed in a transaction that reveals the inscription content on-chain. This content is then inextricably linked to that satoshi, turning it into an immutable digital artifact that can be tracked, transferred, hoarded, bought, sold, lost, and rediscovered.

Archaeology

A lively community of archaeologists devoted to cataloging and collecting early NFTs has sprung up. Here's a great summary of historical NFTs by Chainleft.

A commonly accepted cut-off for early NFTs is March 19th, 2018, the date the first ERC-721 contract, SU SQUARES, was deployed on Ethereum.

Whether or not ordinals are of interest to NFT archaeologists is an open question! In one sense, ordinals were created in early 2022, when the Ordinals specification was finalized. In this sense, they are not of historical interest.

In another sense though, ordinals were in fact created by Satoshi Nakamoto in 2009 when he mined the Bitcoin genesis block. In this sense, ordinals, and especially early ordinals, are

https://docs.ordinals.com/print.html 7/46

2/12/23, 12:14 PM Ordinal Theory Handbook

certainly of historical interest.

Many ordinal theorists favor the latter view. This is not least because the ordinals were independently discovered on at least two separate occasions, long before the era of modern NFTs began.

On August 21st, 2012, Charlie Lee posted a proposal to add proof-of-stake to Bitcoin to the Bitocin Talk forum. This wasn't an asset scheme, but did use the ordinal algorithm, and was implemented but never deployed.

On October 8th, 2012, jl2012 posted a scheme to the the same forum which uses decimal notation and has all the important properties of ordinals. The scheme was discussed but never implemented.

These independent inventions of ordinals indicate in some way that ordinals were discovered, or rediscovered, and not invented. The ordinals are an inevitability of the mathematics of Bitcoin, stemming not from their modern documentation, but from their ancient genesis. They are the culmination of a sequence of events set in motion with the mining of the first block, so many years ago.

https://docs.ordinals.com/print.html 8/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Digital Artifacts

Imagine a physical artifact. A rare coin, say, held safe for untold years in the dark, secret clutch of a Viking hoard, now dug from the earth by your grasping hands. It...

...has an owner. You. As long as you keep it safe, nobody can take it from you. ...is complete. It has no missing parts.

...can only be changed by you. If you were a trader, and you made your way to 18th century China, none but you could stamp it with your chop-mark.

...can only be disposed of by you. The sale, trade, or gift is yours to make, to whomever you wish.

What are digital artifacts? Simply put, they are the digital equivalent of physical artifacts. For a digital thing to be a digital artifact, it must be like that coin of yours:

Digital artifacts can have owners. A number is not a digital artifact, because nobody can own it.

Digital artifacts are complete. An NFT that points to off-chain content on IPFS or Arweave is incomplete, and thus not a digital artifacts.

Digital artifacts are permissionless. An NFT which cannot be sold without paying a royalty is not permissionless, and thus not a digital artifact.

Digital artifacts are uncensorable. Perhaps you can change a database entry on a centralized ledger today, but maybe not tomorrow, and thus one cannot be a digital artifact.

Digital artifacts are immutable. An NFT with an upgrade key is not a digital artifact.\
The definition of a digital artifact is intended to reflect what NFTs should be, sometimes are, and

what inscriptions always are, by their very nature.

https://docs.ordinals.com/print.html 9/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Inscriptions

Inscriptions inscribe sats with arbitrary content, creating bitcoin-native digital artifacts, more commonly known as NFTs. Inscriptions do not require a sidechain or separate token.

These inscribed sats can then be transferred using bitcoin transactions, sent to bitcoin addresses, and held in bitcoin UTXOs. These transactions, addresses, and UTXOs are normal bitcoin transactions, addresses, and UTXOS in all respects, with the exception that in order to send individual sats, transactions must control the order and value of inputs and outputs according to ordinal theory.

The inscription content model is that of the web. An inscription consists of a content type, also known as a MIME type, and the content itself, which is a byte string. This allows inscription content to be returned from a web server, and for creating HTML inscriptions that use and remix the content of other inscriptions.

Inscription content is entirely on-chain, stored in taproot script-path spend scripts. Taproot scripts have very few restrictions on their content, and additionally receive the witness discount, making inscription content storage relatively economical.

Since taproot script spends can only be made from existing taproot outputs, inscriptions are made using a two-phase commit/reveal procedure. First, in the commit transaction, a taproot output committing to a script containing the inscription content is created. Second, in the reveal transaction, the output created by the commit transaction is spent, revealing the inscription content on-chain.

Inscription content is serialized using data pushes within unexecuted conditionals, called an "envelopes". Envelopes consist of an OP\_FALSE OP\_IF ... OP\_ENDIF wrapping any number of data pushes. Because envelopes are effectively no-ops, they do not change the semantics of the script in which they are included, and can be combined with any other locking script.

A text inscription containing the string "Hello, world!" is serialized as follows:

```
OP_FALSE
OP_IF
```

```
  OP_PUSH "ord"
  OP_1
  OP_PUSH "text/plain;charset=utf-8"
  OP_0
  OP_PUSH "Hello, world!"
```

OP\_ENDIF

First the string ord is pushed, to disambiguate inscriptions from other uses of envelopes. https://docs.ordinals.com/print.html

10/46

2/12/23, 12:14 PM Ordinal Theory Handbook

OP\_1 indicates that the next push contains the content type, and OP\_0 indicates that subsequent data pushes contain the content itself. Multiple data pushes must be used for large inscriptions, as one of taproot's few restrictions is that individual data pushes may not be larger than 520 bytes.

The inscription content is contained within the input of a reveal transaction, and the inscription is made on the first sat of its first output. This sat can then be tracked using the familiar rules of ordinal theory, allowing it to be transferred, bought, sold, lost to fees, and recovered.

https://docs.ordinals.com/print.html 11/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Theory FAQ What is ordinal theory?

Ordinal theory is is a protocol for assigning serial numbers to satoshis, the smallest subdivision of a bitcoin, and tracking those satoshis as they are spent by transactions.

These serial numbers are large numbers, like this 804766073970493. Every satoshi, which is 1⁄100000000 of a bitcoin, has an ordinal number.

Does ordinal theory require a side chain, a separate token, or changes to Bitcoin?

Nope! Ordinal theory works right now, without a side chain, and the only token needed is bitcoin itself.

What is ordinal theory good for?

Collecting, trading, and scheming. Ordinal theory assigns identities to individual satoshis, allowing them to be individually tracked and traded, as curios and for numismatic value.

Ordinal theory also enables inscriptions, a protocol for attaching arbitrary content to individual satoshis, turning them into bitcoin-native digital artifacts.

How does ordinal theory work?

Ordinal numbers are assigned to satoshis in the order in which they are mined. The first satoshi in the first block has ordinal number 0, the second has ordinal number 1, and the last satoshi of the first block has ordinal number 4,999,999,999.

Satoshis live in outputs, but transactions destroy outputs and create new ones, so ordinal theory uses an algorithm to determine how satoshis hop from the inputs of a transaction to its outputs.

https://docs.ordinals.com/print.html 12/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Fortunately, that algorithm is very simple.

Satoshis transfer in first-in-first-out order. Think of the inputs to a transaction as being a list of satoshis, and the outputs as a list of slots, waiting to receive a satoshi. To assign input satoshis to slots, go through each satoshi in the inputs in order, and assign each to the first available slot in the outputs.

Let's imagine a transaction with three inputs and two outputs. The inputs are on the left of the arrow and the outputs are on the right, all labeled with their values:

```
   [2] [1] [3] → [4] [2]
```

Now let's label the same transaction with the ordinal numbers of the satoshis that each input contains, and question marks for each output slot. Ordinal numbers are large, so let's use letters to represent them:

```
   [a b] [c] [d e f] → [? ? ? ?] [? ?]
```

To figure out which satoshi goes to which output, go through the input satoshis in order and assign each to a question mark:

```
   [a b] [c] [d e f] → [a b c d] [e f]
```

What about fees, you might ask? Good question! Let's imagine the same transaction, this time with a two satoshi fee. Transactions with fees send more satoshis in the inputs than are received by the outputs, so to make our transaction into one that pays fees, we'll remove the second output:

```
   [2] [1] [3] → [4]
```

The satoshis e and f now have nowhere to go in the outputs: \[a b] \[c] \[d e f] → \[a b c d]

So they go to the miner who mined the block as fees. The BIP has the details, but in short, fees paid by transactions are treated as extra inputs to the coinbase transaction, and are ordered how their corresponding transactions are ordered in the block. The coinbase transaction of the block might look like this:

```
   [SUBSIDY] [e f] → [SUBSIDY e f]
```

https://docs.ordinals.com/print.html 13/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Where can I find the nitty-gritty details?

The BIP!

Why are sat inscriptions called "digital artifacts" instead of "NFTs"?

An inscription is an NFT, but the term "digital artifact" is used instead, because it's simple, suggestive, and familiar.

The phrase "digital artifact" is highly suggestive, even to someone who has never heard the term before. In comparison, NFT is an acronym, and doesn't provide any indication of what it means if you haven't heard the term before.

Additionally, "NFT" feels like financial terminology, and the both word "fungible" and sense of the word "token" as used in "NFT" is uncommon outside of financial contexts.

How do sat inscriptions compare to...

Ethereum NFTs?

Inscriptions are always immutable.

There is simply no way to for the creator of an inscription, or the owner of an inscription, to modify it after it has been created.

Ethereum NFTs can be immutable, but many are not, and can be changed or deleted by the NFT contract owner.

In order to make sure that a particular Ethereum NFT is immutable, the contract code must be audited, which requires detailed knowledge of the EVM and Solidity semantics.

It is very hard for a non-technical user to determine whether or not a given Ethereum NFT is mutable or immutable, and Ethereum NFT platforms make no effort to distinguish whether an NFT is mutable or immutable, and whether the contract source code is available and has been audited.

Inscription content is always on-chain.

https://docs.ordinals.com/print.html

14/46

2/12/23, 12:14 PM Ordinal Theory Handbook

There is no way for an inscription to refer to off-chain content. This makes inscriptions more durable, because content cannot be lost, and scarcer, because inscription creators must pay fees proportional to the size of the content.

Some Ethereum NFT content is on-chain, but much is off-chain, and is stored on platforms like IPFS or Arweave, or on traditional, fully centralized web servers. Content on IPFS is not guaranteed to continue to be available, and some NFT content stored on IPFS has already been lost. Platforms like Arweave rely on weak economic assumptions, and will likely fail catastrophically when these economic assumptions are no longer met. Centralized web servers may disappear at any time.

It is very hard for a non-technical user to determine where the content of a given Ethereum NFT is stored.

Inscriptions are much simpler.

Ethereum NFTs depend on the Ethereum network and virtual machine, which are highly complex, constantly changing, and which introduce changes via backwards-incompatible hard forks.

Inscriptions, on the other hand, depend on the Bitcoin blockchain, which is relatively simple and conservative, and which introduces changes via backwards-compatible soft forks.

Inscriptions are more secure.

Inscriptions inherit Bitcoin's transaction model, which allow a user to see exactly which inscriptions are being transferred by a transaction before they sign it. Inscriptions can be offered for sale using partially signed transactions, which don't require allowing a third party, such as an exchange or marketplace, to transfer them on the user's behalf.

By comparison, Ethereum NFTs are plagued with end-user security vulnerabilities. It is commonplace to blind-sign transactions, grant third-party apps unlimited permissions over a user's NFTs, and interact with complex and unpredictable smart contracts. This creates a minefield of hazards for Ethereum NFT users which are simply not a concern for ordinal theorists.

Inscriptions are scarcer.

Inscriptions require bitcoin to mint, transfer, and store. This seems like a downside on the surface, but the raison d'etre of digital artifacts is to be scarce and thus valuable.

Ethereum NFTs, on the other hand, can be minted in virtually unlimited qualities with a single transaction, making them inherently less scarce, and thus, potentially less valuable.

Inscriptions do not pretend to support on-chain royalties.

https://docs.ordinals.com/print.html

15/46

2/12/23, 12:14 PM Ordinal Theory Handbook

On-chain royalties are a good idea in theory but not in practice. Royalty payment cannot be enforced on-chain without complex and invasive restrictions. The Ethereum NFT ecosystem is currently grappling with confusion around royalties, and is collectively coming to grips with the reality that on-chain royalties, which were messaged to artists as an advantage of NFTs, are not possible, while platforms race to the bottom and remove royalty support.

Inscriptions avoid this situation entirely by making no false promises of supporting royalties on- chain, thus avoiding the confusion, chaos, and negativity of the Ethereum NFT situation.

Inscriptions unlock new markets.

Bitcoin's market capitalization and liquidity are greater than Ethereum's by a large margin. Much of this liquidity is not available to Ethereum NFTs, since many Bitcoiners prefer not to interact with the Ethereum ecosystem due to concerns related to simplicity, security, and decentralization.

Such Bitcoiners may be more interested in inscriptions than Ethereum NFTs, unlocking new classes of collector.

Inscriptions have a richer data model.

Inscriptions consist of a content type, also known as a MIME type, and content, which is an arbitrary byte string. This is the same data model used by the web, and allows inscription content to evolve with the web, and come to support any kind of content supported by web browsers, without requiring changes to the underlying protocol.

RGB and Taro assets?

RGB and Taro are both second-layer asset protocols built on Bitcoin. Compared to inscriptions, they are much more complicated, but much more featureful.

Ordinal theory has been designed from the ground up for digital artifacts, whereas the primary use-case of RGB and Taro are fungible tokens, so the user experience for inscriptions is likely to be simpler and more polished than the user experience for RGB and Taro NFTs.

RGB and Taro both store content off-chain, which requires additional infrastructure, and which may be lost. By contrast, inscription content is stored on-chain, and cannot be lost.

Ordinal theory, RGB, and Taro are all very early, so this is speculation, but ordinal theory's focus may give it the edge in terms of features for digital artifacts, including a better content model, and features like globally unique symbols.

https://docs.ordinals.com/print.html 16/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Counterparty assets?

Counterparty has its own token, XCP, which is required for some functionality, which makes most bitcoiners regard it as an altcoin, and not an extension or second layer for bitcoin.

Ordinal theory has been designed from the ground up for digital artifacts, whereas Counterparty was primarily designed for financial token issuance.

Inscriptions for... Artists

Inscriptions are on Bitcoin. Bitcoin is the digital currency with the highest status and greatest chance of long-term survival. If you want to guarantee that your art survives into the future, there is no better way to publish it than as inscriptions.

Cheaper on-chain storage. At $20,000 per BTC and the minimum relay fee of 1 satoshi per vbyte, publishing inscription content costs $50 per 1 million bytes.

Inscriptions are early! Inscriptions are still in development, and have not yet launched on mainnet. This gives you an opportunity to be an early adopter, and explore the medium as it evolves.

Inscriptions are simple. Inscriptions do not require writing or understanding smart contracts. Inscriptions unlock new liquidity. Inscriptions are more accessible and appealing to bitcoin

holders, unlocking an entirely new class of collector.

Inscriptions are designed for digital artifacts. Inscriptions are designed from the ground up to support NFTs, and feature a better data model, and features like globally unique symbols and enhanced provenance.

Inscriptions do not support on-chain royalties. This is negative, but only depending on how you look at it. On-chain royalties have been a boon for creators, but have also created a huge amount of confusion in the Ethereum NFT ecosystem. The ecosystem now grapples with this issue, and is is engaged in a race to the bottom, towards a royalties-optional future. Inscriptions have no support for on-chain royalties, because they are technically infeasible. If you choose to create inscriptions, there are many ways you can work around this limitation: withhold a portion of your inscriptions for future sale, to benefit from future appreciation, or perhaps offer perks for users who respect optional royalties.

https://docs.ordinals.com/print.html 17/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Collectors

Inscriptions are simple, clear, and have no surprises. They are always immutable and on-chain, with no special due diligence required.

Inscriptions are on Bitcoin. You can verify the location and properties of inscriptions easily with Bitcoin full node that you control.

Bitcoiners

Let me begin this section by saying: the most important thing that the Bitcoin network does is decentralize money. All other use-cases are secondary, including ordinal theory. The developers of ordinal theory understand and acknowledge this, and believe that ordinal theory helps, at least in a small way, Bitcoin's primary mission.

Unlike many other things in the altcoin space, digital artifacts have merit. There are, of course, a great deal of NFTs that are ugly, stupid, and fraudulent. However, there are many that are fantastically creative, and creating and collecting art has been a part of the human story since its inception, and predates even trade and money, which are also ancient technologies.

Bitcoin provides an amazing platform for creating and collecting digital artifacts in a secure, decentralized way, that protects users and artists in the same way that it provides an amazing platform for sending and receiving value, and for all the same reasons.

Ordinals and inscriptions increase demand for Bitcoin block space, which increase Bitcoin's security budget, which is vital for safeguarding Bitcoin's transition to a fee-dependent security model, as the block subsidy is halved into insignificance.

Inscription content is stored on-chain, and thus the demand for block space for use in inscriptions is unlimited. This creates a buyer of last resort for all Bitcoin block space. This will help support a robust fee market, which ensures that Bitcoin remains secure.

Inscriptions also counter the narrative that Bitcoin cannot be extended or used for new use- cases. If you follow projects like DLCs, Fedimint, Lightning, Taro, and RGB, you know that this narrative is false, but inscriptions provide a counter argument which is easy to understand, and which targets a popular and proven use case, NFTs, which makes it highly legible.

If inscriptions prove, as the authors hope, to be highly sought after digital artifacts with a rich history, they will serve as a powerful hook for Bitcoin adoption: come for the fun, rich art, stay for the decentralized digital money.

Inscriptions are an extremely benign source of demand for block space. Unlike, for example, stablecoins, which potentially give large stablecoin issuers influence over the future of Bitcoin

https://docs.ordinals.com/print.html

18/46

2/12/23, 12:14 PM Ordinal Theory Handbook

development, or DeFi, which might centralize mining by introducing opportunities for MEV, digital art and collectables on Bitcoin, are unlikely to produce individual entities with enough power to corrupt Bitcoin. Art is decentralized.

Inscription users and service providers are incentivized to run Bitcoin full nodes, to publish and track inscriptions, and thus throw their economic weight behind the honest chain.

Ordinal theory and inscriptions do not meaningfully affect Bitcoin's fungibility. Bitcoin users can ignore both and be unaffected.

We hope that ordinal theory strengthens and enriches bitcoin, and gives it another dimension of appeal and functionality, enabling it more effectively serve its primary use case as humanity's decentralized store of value.

https://docs.ordinals.com/print.html 19/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Contributing to ord Suggested Steps

1. Find an issue you want to work on.
2.  Figure out what would be a good first step towards resolving the issue. This could be in

    the form of code, research, a proposal, or suggesting that it be closed, if it's out of date or

    not a good idea in the first place.
3.  Comment on the issue with an outline of your suggested first step, and asking for

    feedback. Of course, you can dive in and start writing code or tests immediately, but this avoids potentially wasted effort, if the issue is out of date, not clearly specified, blocked on something else, or otherwise not ready to implement.
4. If the issue requires a code change or bugfix, open a draft PR with tests, and ask for feedback. This makes sure that everyone is on the same page about what needs to be done, or what the first step in solving the issue should be. Also, since tests are required, writing the tests first makes it easy to confirm that the change can be tested easily.
5. Mash the keyboard randomly until the tests pass, and refactor until the code is ready to submit.
6. Mark the PR as ready to review.
7. Revise the PR as needed.
8. And finally, mergies!

Start small

Small changes will allow you to make an impact quickly, and if you take the wrong tack, you won't have wasted much time.

Ideas for small issues:

Add a new test or test case that increases test coverage\
Add or improve documentation\
Find an issue that needs more research, and do that research and summarize it in a comment\
Find an out-of-date issue and comment that it can be closed\
Find an issue that shouldn't be done, and provide constrictive feedback detailing why you think that is the case

https://docs.ordinals.com/print.html 20/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Merge early and often

Break up large tasks into multiple smaller steps that individually make progress. If there's a bug, you can open a PR that adds a failing ignored test. This can be merged, and the next step can be to fix the bug and unignore the test. Do research or testing, and report on your results. Break a feature into small sub-features, and implement them one at a time.

Figuring out how to break down a larger PR into smaller PRs where each can be merged is a art form well-worth practicing. The hard part is that each PR must itself be an improvement.

I strive to follow this advice myself, and am always better off when I do.

Small changes are fast to write, review, and merge, which is much more fun than laboring over a single giant PR that takes forever to write, review, and merge. Small changes don't take much time, so if you need to stop working on a small change, you won't have wasted much time as compared to a larger change that represents many hours of work. Getting a PR in quickly improves the project a little bit immediately, instead of having to wait a long time for larger improvement. Small changes are less likely to accumulate merge conflict. As the Athenians said: The fast commit what they will, the slow merge what they must.

Get help

If you're stuck for more than 15 minutes, ask for help, like a Rust Discord, Stack Exchange, or in a project issue or discussion.

Practice hypothesis-driven debugging

Formulate a hypothesis as to what is causing the problem. Figure out how to test that hypothesis. Perform that tests. If it works, great, you fixed the issue or now you know how to fix the issue. If not, repeat with a new hypothesis.

Pay attention to error messages

Read all error messages and don't tolerate warnings.

https://docs.ordinals.com/print.html 21/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Donate

Ordinals is an open-source project by me, Casey Rodarmor, in development since early 2022. I have been assisted by a ragtag band of contributors, bitcoiners, and degenerates, including two paid apprentices. All project costs have been paid out of pocket by me, and I have not raised outside funds, and may never.

If you so desire, consider a donation. Donations of bitcoin are appreciated, but donations of rare, exotic, and inscribed sats are especially treasured.

Donations are not tax-deductible, refundable, or earmarked for any specific purpose. They are personal gifts to me, made out of love, support, encouragement, or in the vain hope that if I get enough bitcoin I'll stop doing all this and go away.

Donations may be sold, lost, given away, or held until death. Donations of bitcoin are likely to be spent on rare and exotic sats and making whole-block inscriptions.

Ordinals and inscriptions are a love letter to Bitcoin, the Internet, programming, and the World Wide Web. Money is nice, but that's not why I'm doing it. Don't worry if you can't donate. Merely using this strange, evolving creation is thanks enough. I love having you along for the ride, wherever it may take us.

I have in my possession 21 opendimes whose addresses are below. Pick one that speaks to you, and send to it what you will.\
Love, Casey

1\. 2. 3. 4. 5. 6. 7. 8. 9.

10.\
11.\
12.\
13.\
14\. 18Ruktk8pJzKyjqdY6FxAEsXvspG9nyyXS

```
13aG4o1cEKVLzuLdwKrmmP65o6WKh8t4L3
```

```
1FrhgVqWF7aSM9945BRsrEqQZFEM3kZXQJ
```

```
17VUfVjYJiaLkmCvwaGFBcBQ3riJMnk1hc
```

```
1PH3WNHvdU9yprpHgymWigJzEsF2L6sX7L
```

```
1Jt7P4Ct1tJsfZshQjubda1qkPF5tNWeEr
```

```
1QSXSyudincb7ioV53zzAfdpAxTUMwtKR
```

```
1MGREYM262PJsYryLnBYsXuzgpdn8hasBV
```

```
1JhEZFSb4URMgPcQtqtfsLpJrxv6AZKjVX
```

```
1Ch9iYY7VD39sLXHud6tWJr37G9s4GYcub
```

```
13N4aVWdPLcwg5g1kbLav3gfqZvh94vcfW
```

```
1DwgGvPJp4znPQ7nWYJ4VibwmtVU2aVnCg
```

```
1M7ePCREnnLQ5PxN3m1JpHQ4rkBqhUtWb5
```

```
1DqSs5biPYXTNHQGcnq7wz2q4aFpLUKUvo
```

https://docs.ordinals.com/print.html

22/46

2/12/23, 12:14 PM

15.\
16.\
17.\
18.\
19.\
20.\
21\. 14RkYZw1d2W3AyfqQge83GmWAaynhPUDtN

Ordinal Theory Handbook

```
1FFfiZZc2GFnumNdQuwgvdHUDVDnWFXu53
```

```
17FCXKzeGswkNG3LyU9eRGx7dcZoXPiYm3
```

```
1FBZwVAU73c6gzAxrmb2WhojUaUutcQpxc
```

```
1LYk7YCnSsVDKV6GdN9qUjNoFzQ5CU8EfP
```

```
1LjKhEw6yRDX4Szk4ahDXq4RMnGPSUBXPA
```

```
1QHhEm7EycvmeGY6qp1M4canXMh7XP4oHv
```

https://docs.ordinals.com/print.html

23/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Theory Guides

See the the table of contents for a list of guides, including a guide to the explorer, a guide for sat hunters, and a guide to inscriptions.

https://docs.ordinals.com/print.html 24/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Explorer

The ord binary includes a block explorer. We host a instance of the block explorer on mainnet at ordinals.com, and on signet at signet.ordinals.com.

Search

The search box accepts a variety of object representations.

Blocks

Blocks can be searched by hash, for example, the genesis block:

000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f

Transactions

Transactions can be searched by hash, for example, the genesis block coinbase transaction:

4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b

Outputs

Transaction outputs can searched by outpoint, for example, the only output of the genesis block coinbase transaction:

4a5e1e4baab89f3a32518a88c31bc87f618f76673e2cc77ab2127b7afdeda33b:0

Sats

Sats can be searched by integer, their position within the entire bitcoin supply:

```
2099994106992659
```

By decimal, their block and offset within that block:

https://docs.ordinals.com/print.html

25/46

2/12/23, 12:14 PM Ordinal Theory Handbook

481824.0

By degree, their cycle, blocks since the last halving, blocks since the last difficulty adjustment, and offset within their block:

1°0′0′′0′′′

By name, their base 26 representation using the letters "a" through "z":

ahistorical

Or by percentile, the percentage of bitcoin's supply that has been or will have been issued when they are mined:

100%

https://docs.ordinals.com/print.html

26/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Inscription Guide

Individual sats can be inscribed with arbitrary content, creating Bitcoin-native digital artifacts that can be held in a Bitcoin wallet and transferred using Bitcoin transactions. Inscriptions are as durable, immutable, secure, and decentralized as Bitcoin itself.

Working with inscriptions requires a Bitcoin full node, to give you a view of the current state of the Bitcoin blockchain, and a wallet that can create inscriptions and perform sat control when constructing transactions to send inscriptions to another wallet.

Bitcoin Core provides both a Bitcoin full node and wallet. However, the Bitcoin Core wallet cannot create inscriptions and does not perform sat control.

This requires ord , the ordinal utility. ord doesn't implement its own wallet, so ord wallet subcommands interact with Bitcoin Core wallets.

This guide covers:

1\. Installing Bitcoin Core\
2\. Syncing the Bitcoin blockchain\
3\. Creating a Bitcoin Core wallet\
4\. Using to receive sats 5. Creating inscriptions with\
6\. Sending inscriptions with\
7\. Receiving inscriptions with

Getting Help

If you get stuck, try asking for help on the Ordinals Discord Server, or checking GitHub for relevant issues and discussions.

Installing Bitcoin Core

Bitcoin Core is available from bitcoincore.org on the download page. Making inscriptions requires Bitcoin Core 24 or newer.

https://docs.ordinals.com/print.html

27/46

```
ord wallet receive
```

```
ord wallet inscribe
```

```
ord wallet send
```

```
ord wallet receive
```

2/12/23, 12:14 PM Ordinal Theory Handbook

This guide does not cover installing Bitcoin Core in detail. Once Bitcoin Core is installed, you should be able to run bitcoind -version successfully from the command line.

Configuring Bitcoin Core

ord requires Bitcoin Core's transaction index.\
To configure your Bitcoin Core node to use maintain a transaction index, add the following to

your bitcoin.conf : txindex=1

Or, run bitcoind with -txindex : bitcoind -txindex

Syncing the Bitcoin Blockchain

To sync the chain, run:

bitcoind -txindex\
...and leave it running until getblockcount :

```
   bitcoin-cli getblockcount
```

agrees with the block count on a block explorer like the mempool.space block explorer. ord interacts with bitcoind , so you should leave bitcoind running in the background when you're using ord .

Installing ord\
The ord utility is written in Rust and can be built from source. Pre-built binaries are available

on the releases page.

You can install the latest pre-built binary from the command line with:

https://docs.ordinals.com/print.html

28/46

2/12/23, 12:14 PM Ordinal Theory Handbook

curl --proto '=https' --tlsv1.2 -fsLS https://ordinals.com/install.sh | bash -s Once ord is installed, you should be able to run:

```
 ord --version
```

Which prints out ord 's version number.

Creating a Bitcoin Core Wallet

ord uses Bitcoin Core to manage private keys, sign transactions, and broadcast transactions to the Bitcoin network.

To create a Bitcoin Core wallet named ord for use with ord , run: ord wallet create

Receiving Sats

Inscriptions are made on individual sats, using normal Bitcoin transactions that pay fees in sats, so your wallet will need some sats.

Get a new address from your ord wallet by running: ord wallet receive

And send it some funds.\
You can see pending transactions with:

```
 ord wallet transactions
```

Once the transaction confirms, you should be able to see the transactions outputs with wallet outputs .

https://docs.ordinals.com/print.html

29/46

ord

2/12/23, 12:14 PM Ordinal Theory Handbook

Creating Inscription Content

Sats can be inscribed with any kind of content, but the ord wallet only supports content types that can be displayed by the ord block explorer.

Additionally, inscriptions are included in transactions, so the larger the content, the higher the fee that the inscription transaction must pay.

Inscription content is included in transaction witnesses, which receive the witness discount. To calculate the approximate fee that in inscribe transaction will pay, divide the content size by four and muliply by the fee rate.

Inscription transactions must be less than 400,000 weight units, or they will not be relayed by Bitcoin Core. One byte of inscription content costs one weight unit. Since an inscription transaction includes not just the inscription content, limit inscription content to less than 400,000 weight units. 390,000 weight units should be safe.

Creating Inscriptions

To create an inscription with the contents of FILE , run: ord wallet inscribe FILE

Ord will output two transactions IDs, one for the commit transaction, and one for the reveal transaction, and the inscription ID. Inscription IDs are of the form TXIDiN , where TXID is the transaction ID of the reveal transaction, and N is the index of the inscription in the reveal transaction.

The commit transaction commits to a tapscript containing the contents of the inscription, and the reveal transaction spends from that tapscript, revealing the contents on chain and inscribing them on the first sat of the first output of the reveal transaction.

Wait for the reveal transaction to be mined. You can check the status of the commit and reveal transactions using the mempool.space block explorer.

Once the reveal transaction has been mined, the inscription ID should be printed when you run:

```
   ord wallet inscriptions
```

And when you visit the ordinals explorer at ordinals.com/inscription/INSCRIPTION\_ID . https://docs.ordinals.com/print.html

30/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Sending Inscriptions

Ask the recipient to generate a new address by running:

```
   ord wallet receive
```

Send the inscription by running:

```
   ord wallet send ADDRESS INSCRIPTION_ID
```

See the pending transaction with:

```
   ord wallet transactions
```

Once the send transaction confirms, the recipient can confirm receipt by running:

```
   ord wallet inscriptions
```

Receiving Inscriptions

Generate a new receive address using:

```
   ord wallet receive
```

The sender can transfer the inscription to your address using:

```
   ord wallet send ADDRESS INSCRIPTION_ID
```

See the pending transaction with:

```
   ord wallet transactions
```

Once the send transaction confirms, you can can confirm receipt by running:

```
   ord wallet inscriptions
```

https://docs.ordinals.com/print.html

31/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Sat Hunting

This guide is out of date. Since it was written, the ord binary was changed to only build the full satoshi index when the flag is supplied. Additionally, ord now has a built-in wallet that wraps a Bitcoin Core wallet. See .

Ordinal hunting is difficult but rewarding. The feeling of owning a wallet full of UTXOs, redolent with the scent of rare and exotic sats, is beyond compare.

Ordinals are numbers for satoshis. Every satoshi has an ordinal number and every ordinal number has a satoshi.

Preparation

There are a few things you'll need before you start.

1.  First, you'll need a synced Bitcoin Core node with a transaction index. To turn on

    transaction indexing, pass -txindex on the command-line: bitcoind -txindex

    Or put the following in your Bitcoin configuration file: txindex=1

    Launch it and wait for it to catch up to the chain tip, at which point the following command should print out the current block height:

    ```
          bitcoin-cli getblockcount
    ```
2.  Second, you'll need a synced ord index. Get a copy of ord from the repo.

    Run RUST\_LOG=info ord index . It should connect to your bitcoin core node and start indexing.

    Wait for it to finish indexing.

```
--index-sats
```

```
ord wallet --help
```

https://docs.ordinals.com/print.html

32/46

2/12/23, 12:14 PM Ordinal Theory Handbook

3\. Third, you'll need a wallet with UTXOs that you want to search.

Searching for Rare Ordinals\
Searching for Rare Ordinals in a Bitcoin Core Wallet

The ord wallet command is just a wrapper around Bitcoin Core's RPC API, so searching for rare ordinals in a Bitcoin Core wallet is Easy. Assuming your wallet is named foo :

1\. Load your wallet:

```
        bitcoin-cli loadwallet foo
```

2\. Display any rare ordinals wallet foo 's UTXOs: ord wallet sats

Searching for Rare Ordinals in a Non-Bitcoin Core Wallet

The ord wallet command is just a wrapper around Bitcoin Core's RPC API, so to search for rare ordinals in a non-Bitcoin Core wallet, you'll need to import your wallet's descriptors into Bitcoin Core.

Descriptors describe the ways that wallets generate private keys and public keys.\
You should only import descriptors into Bitcoin Core for your wallet's public keys, not its private

keys.

If your wallet's public key descriptor is compromised, an attacker will be able to see your wallet's addresses, but your funds will be safe.

If your wallet's private key descriptor is compromised, an attacker can drain your wallet of funds.

1\. Get the wallet descriptor from the wallet whose UTXOs you want to search for rare ordinals. It will look something like this:

https://docs.ordinals.com/print.html

33/46

2/12/23, 12:14 PM Ordinal Theory Handbook

```
wpkh([bf1dd55e/84'/0'/0']xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTHY
nc8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/0/*)#csvefu29
```

2.  Create a watch-only wallet named foo-watch-only : bitcoin-cli createwallet foo-watch-only true true

    Feel free to give it a better name than foo-watch-only !
3.  Load the foo-watch-only wallet:

    ```
       bitcoin-cli loadwallet foo-watch-only
    ```
4. Import your wallet descriptors into foo-watch-only :

```
bitcoin-cli importdescriptors \
```

```
  '[{ "desc":
"wpkh([bf1dd55e/84h/0h/0h]xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/0/*)#tpnxnxax",
"timestamp":0 }]'
```

If you know the Unix timestamp when your wallet first started receive transactions, you may use it for the value of "timestamp" instead of 0 . This will reduce the time it takes for Bitcoin Core to search for your wallet's UTXOs.

5.  Check that everything worked:

    ```
          bitcoin-cli getwalletinfo
    ```
6.  Display your wallet's rare ordinals:

    ```
          ord wallet sats
    ```

Searching for Rare Ordinals in a Wallet that Exports Multi-path Descriptors

Some descriptors describe multiple paths in one descriptor using angle brackets, e.g., <0;1> . Multi-path descriptors are not yet supported by Bitcoin Core, so you'll first need to convert them into multiple descriptors, and then import those multiple descriptors into Bitcoin Core.

https://docs.ordinals.com/print.html

34/46

2/12/23, 12:14 PM Ordinal Theory Handbook

1. First get the multi-path descriptor from your wallet. It will look something like this:
2.  Create a descriptor for the receive address path:

    And the change address path:
3. Get and note the checksum for the receive address descriptor, in this case tpnxnxax :

```
wpkh([bf1dd55e/84h/0h/0h]xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTHY
nc8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/<0;1>/*)#fw76ulgt
```

```
wpkh([bf1dd55e/84'/0'/0']xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTHY
nc8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/0/*)
```

```
wpkh([bf1dd55e/84'/0'/0']xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTHY
nc8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/1/*)
```

```
bitcoin-cli getdescriptorinfo \
```

```
'wpkh([bf1dd55e/84h/0h/0h]xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/0/*)'
```

```
{
  "descriptor":
```

```
"wpkh([bf1dd55e/84'/0'/0']xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/0/*)#csvefu29",
```

```
  "checksum": "tpnxnxax",
  "isrange": true,
  "issolvable": true,
  "hasprivatekeys": false
```

}

And for the change address descriptor, in this case 64k8wnd7 :

```
bitcoin-cli getdescriptorinfo \
```

```
'wpkh([bf1dd55e/84h/0h/0h]xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/1/*)'
```

https://docs.ordinals.com/print.html

35/46

2/12/23, 12:14 PM Ordinal Theory Handbook

```
{
  "descriptor":
```

```
"wpkh([bf1dd55e/84'/0'/0']xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/1/*)#fyfc5f6a",
```

```
  "checksum": "64k8wnd7",
  "isrange": true,
  "issolvable": true,
  "hasprivatekeys": false
```

}

4.  Load the wallet you want to import the descriptors into:

    ```
       bitcoin-cli loadwallet foo-watch-only
    ```
5. Now import the descriptors, with the correct checksums, into Bitcoin Core.

```
bitcoin-cli \
 importdescriptors \
 '[
```

{ "desc":

```
"wpkh([bf1dd55e/84h/0h/0h]xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/0/*)#tpnxnxax"
```

```
     "timestamp":0
   },
```

{ "desc":

```
"wpkh([bf1dd55e/84h/0h/0h]xpub6CcJtWcvFQaMo39ANFi1MyXkEXM8T8ZhnxMtSjQAdPmVSTH
Ync8Hwoc11VpuP8cb8JUTboZB5A7YYGDonYySij4XTawL6iNZvmZwdnSEEep/1/*)#64k8wnd7",
```

```
     "timestamp":0
   }
```

]'

If you know the Unix timestamp when your wallet first started receive transactions, you may use it for the value of the "timestamp" fields instead of 0 . This will reduce the time it takes for Bitcoin Core to search for your wallet's UTXOs.

6\. Check that everything worked:

```
   bitcoin-cli getwalletinfo
```

https://docs.ordinals.com/print.html

36/46

2/12/23, 12:14 PM Ordinal Theory Handbook

7\. Display your wallet's rare ordinals:

```
        ord wallet sats
```

Exporting Descriptors Sparrow Wallet

Navigate to the Settings tab, then to Script Policy , and press the edit button to display the descriptor.

Transferring Ordinals

The ord wallet supports transferring specific satoshis. You can also use bitcoin-cli commands createrawtransaction , signrawtransactionwithwallet , and

sendrawtransaction , how to do so is complex and outside the scope of this guide.

https://docs.ordinals.com/print.html

37/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Collecting

Currently, ord is the only wallet supporting sat-control and sat-selection, which are required to safely store and send rare sats and inscriptions, hereafter ordinals.

The recommended way to send, receive, and store ordinals is with ord , but if you are careful, it is possible to safely store, and in some cases send, ordinals with other wallets.

As a general note, receiving ordinals in an unsupported wallet is not dangerous. Ordinals can be sent to any bitcoin address, and are safe as long as the UTXO that contains them is not spent. However, if that wallet is then used to send bitcoin, it may select the UTXO containing the ordinal as an input, and send the inscription or spend it to fees.

windsok has kindly written a guide to creating an ord -compatible wallet with Sparrow, available on GitHub. Please note that if you follow this guide, you should not use the wallet you create to send BTC, unless you perform manual coin-selection to avoid sending ordinals.

https://docs.ordinals.com/print.html 38/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Moderation

ord includes a block explorer, which you can run locally with ord server .\
The block explorer allows viewing inscriptions. Inscriptions are user-generated content, which

may be objectionable or unlawful.

It is the responsibility of each individual who runs an ordinal block explorer instance to understand their responsibilities with respect to unlawful content, and decide what moderation policy is appropriate for their instance.

In order to prevent particular inscriptions from being displayed on an ord instance, they can be included in a YAML config file, which is loaded with the --config option.

To hide inscriptions, first create a config file, with the inscription ID you want to hide:

The suggested name for ord config files is ord.yaml , but any filename can be used. Then pass the file to --config when starting the server:

ord --config ord.yaml server\
Note that the --config option comes after ord but before the server subcommand.

ord must be restarted in to load changes to the config file.

```
hidden:
- 0000000000000000000000000000000000000000000000000000000000000000i0
```

```
ordinals.com
```

The ordinals.com instances use with a config file located at

To hide an inscription on ordinals.com :

1\. SSH into the server\
2\. Add the inscription ID to 3. Restart the service with 4. Monitor the restart with

to run the ord server service, which is called ord , .

systemd

```
/var/lib/ord/ord.yaml
```

https://docs.ordinals.com/print.html

39/46

```
/var/lib/ord/ord.yaml
```

```
systemctl restart ord
```

```
journalctl -u ord
```

2/12/23, 12:14 PM Ordinal Theory Handbook

Currently, ord is slow to restart, so the site will not come back online immediately.

https://docs.ordinals.com/print.html 40/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Bounty Hunting Hints

The ord wallet can send and receive specific satoshis. Additionally, ordinal theory is extremely simple. A clever hacker should be able to write code from scratch to manipulate satoshis using ordinal theory in no time.

For more information about ordinal theory, check out the FAQ for an overview, the BIP for the technical details, and the ord repo for the ord wallet and block explorer.

Satoshi was the original developer of ordinal theory. However, he knew that others would consider it heretical and dangerous, so he hid his knowledge, and it was lost to the sands of time. This potent theory is only now being rediscovered. You can help by researching rare satoshis.

Good luck and godspeed!

https://docs.ordinals.com/print.html 41/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Bounty 0 Criteria

Send a sat whose ordinal number ends with a zero to the submission address: : 1857578125803250\
: 1857578125803251

The sat must be the first sat of the output you send.

Reward

100,000 sats

Submission Address

Status

Claimed by @count\_null!

https://docs.ordinals.com/print.html

42/46

❌\
✅

```
1PE7u4wbDP2RqfKN6geD1bG57v9Gj9FXm3
```

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Bounty 1 Criteria

The transaction that submits a UTXO containing the oldest sat, i.e., that with the lowest number, amongst all submitted UTXOs will be judged the winner.

The bounty is open for submissions until block 753984—the first block of difficulty adjustment period 374. Submissions included in block 753984 or later will not be considered.

Reward

200,000 sats

Submission Address

```
145Z7PFHyVrwiMWwEcUmDgFbmUbQSU9aap
```

Status

Claimed by @ordinalsindex!

https://docs.ordinals.com/print.html

43/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Bounty 2 Criteria

Send an uncommon sat to the submission address: : 347100000000000\
: 6685000001337

Confirm that the submission address has not received transactions before submitting your entry. Only the first successful submission will be rewarded.

Reward

300,000 sats

Submission Address

Status

Claimed by @utxoset!

https://docs.ordinals.com/print.html

44/46

❌\
✅

```
1Hyr94uypwWq5CQffaXHvwUMEyBPp3TUZH
```

2/12/23, 12:14 PM Ordinal Theory Handbook

Ordinal Bounty 3 Criteria

Ordinal bounty 3 has two parts, both of which are based on ordinal names. Ordinal names are a modified base-26 encoding of ordinal numbers. To avoid locking short names inside the unspendable genesis block coinbase reward, ordinal names get shorter as the ordinal number gets longer. The name of sat 0, the first sat to be mined is nvtdijuwxlp and the name of sat 2,099,999,997,689,999, the last sat to be mined, is a .

The bounty is open for submissions until block 840000—the first block after the fourth halvening. Submissions included in block 840000 or later will not be considered.

Both parts use frequency.tsv, a list of words and the number of times they occur in the Google Books Ngram dataset. filtered to only include the names of sats which will have been mined by the end of the submission period, that appear at least 5000 times in the corpus.

frequency.tsv is a file of tab-separated values. The first column is the word, and the second is the number of times it appears in the corpus. The entries are sorted from least-frequently occurring to most-frequently occurring.

frequency.tsv was compiled using this program.\
To search an ord wallet for sats with a name in frequency.tsv , use the following ord

command:

ord wallet sats --tsv frequency.tsv\
This command requires the sat index, so --index-sats must be passed to ord when first

creating the index.

Part 0

Rare sats pair best with rare words.

The transaction that submits the UTXO containing the sat whose name appears with the lowest number of occurrences in frequency.tsv shall be the winner of part 0.

https://docs.ordinals.com/print.html 45/46

2/12/23, 12:14 PM Ordinal Theory Handbook

Part 1

Popularity is the font of value.

The transaction that submits the UTXO containing the sat whose name appears with the highest number of occurrences in frequency.tsv shall be the winner of part 1.

Tie Breaking

In the case of a tie, where two submissions occur with the same frequency, the earlier submission shall be the winner.

Reward

Part 0: 200,000 sats Part 1: 200,000 sats Total: 400,000 sats

Submission Address

```
   17m5rvMpi78zG8RUpCRd6NWWMJtWmu65kg
```

Status

Unclaimed!

https://docs.ordinals.com/print.html

46/46
