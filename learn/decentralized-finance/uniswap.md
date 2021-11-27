---
title: How Uniswap Solved the Liquidity Problem on DEXs
description: Uniswap is a decentralised exchange protocol launched with huge success on Ethereum mainnet in November 2018. 
published: true
date: 2021-11-27T22:08:03.799Z
tags: decentralized exchange, decentralized finance, defi, dex, education, finance, liquidity mining, liquidity pool, uniswap
editor: markdown
dateCreated: 2021-10-09T07:04:27.833Z
---

# What is Uniswap?

Uniswap is a decentralised exchange protocol launched on the Ethereum mainnet in November 2018. It was developed by Hayden Adams with funding from a grant from the Ethereum Foundation. Uniswap's simple concept where liquidity for exchange transactions is provided by on-chain liquidity pools. The pool value is calculated by the equal value of both ETH and a single ERC-20 token traded. Trades are executed against these pools, which use an automated market-making strategy to trades without the need for order books or relying  on third party centralized entities. The smart contract design at the time allowed for exceptionally low gas fees compared to other decentralized exchanges. 

Uniswap shocked the DeFi world with its immensely successful launch achieving a cumulative trading volume of $1mil in only two months. This success was only a  foreshadowing of the DeFi bloom just around the corner, and certainly was the source of inspiration for other popular DEXes today such as QuickSwap on Polygon and PancakeSwap on Binance Smart Chain. In 2020 Uniswap reported a total trade volume of $20bn with over 250,000 wallets and 8500 unique tokens traded. 

## UNI Token

## Who are Liquidity Providers?

Trades on Uniswap cause price slippage, with trades that are large relative to total liquidity causing more slippage. So, for Uniswap to function well and allow large trades it also needs large liquidity pools. So who provides this liquidity, and why should they pool their valuable ETH and ERC-20 tokens in a Uniswap exchange? Liquidity providers can be anyone who is able to supply equal values of ETH and an ERC-20 token to a Uniswap exchange contract. In return they are given tokens from the exchange contract which can be used to withdraw their proportion of the liquidity pool at any time. Whenever someone trades on the exchange, the trader pays a 0.3% fee which is added to the liquidity pool. Since no new liquidity tokens are minted, this has the effect of splitting the transaction fee proportionally between all existing liquidity providers.

In fact, not only do liquidity providers receive fees from all trades, but trades are guaranteed to occur when the price in the wider market changes. This is because if the price changes on another exchange, there will be an arbitrage opportunity created by the price differential between that exchange and Uniswap. When an arbitrageur executes the profitable trade that brings the Uniswap exchange back into line with the wider market, liquidity providers benefit from Uniswap exchange fees. Sure enough, on all Uniswap exchanges with significant liquidity, arbitrageurs are hard at work such that prices track closely with the rest of the market.


Understandably, with this apparent promise of income for liquidity providers, people have been quick to pool their assets in Uniswap exchange contracts.

But after a few days with their liquidity in the pool, some liquidity providers are looking at the value of their stake in the liquidity pool and finding it’s worth less than what they put in, when measured in either ETH or the ERC-20 token on the exchange. What’s going on here?


## Why is my liquidity worth less than I put in?
To understand why the value of a liquidity provider’s stake can go down despite income from fees, we need to look a bit more closely at the formula used by Uniswap to govern trading. The formula really is very simple. If we neglect trading fees, we have the following: `eth_liquidity_pool * token_liquidity_pool = constant_product`


In other words, the number of tokens a trader receives for their ETH and vice versa is calculated such that after the trade, the product of the two liquidity pools is the same as it was before the trade. The consequence of this formula is that for trades which are very small in value compared to the size of the liquidity pool we have: `eth_price = token_liquidity_pool / eth_liquidity_pool`


Combining these two equations, we can work out the size of each liquidity pool at any given price, assuming constant total liquidity:
eth_liquidity_pool = sqrt(constant_product / eth_price)
token_liquidity_pool = sqrt(constant_product * eth_price)


So let’s look at the impact of a price change on a liquidity provider. To keep things simple, let’s imagine our liquidity provider supplies 1 ETH and 100 DAI to the Uniswap DAI exchange, giving them 1% of a liquidity pool which contains 100 ETH and 10,000 DAI. This implies a price of 1 ETH = 100 DAI. Still neglecting fees, let’s imagine that after some trading, the price has changed; 1 ETH is now worth 120 DAI. What is the new value of the liquidity provider’s stake? Plugging the numbers into the formulae above, we have:

eth_liquidity_pool = 91.2871
dai_liquidity_pool = 10954.4511

Since our liquidity provider has 1% of the liquidity tokens, this means they can now claim 0.9129 ETH and 109.54 DAI from the liquidity pool. But since DAI is approximately equivalent to USD, we might prefer to convert the entire amount into DAI to understand the overall impact of the price change. At the current price then, our liquidity is worth a total of 219.09 DAI. What if the liquidity provider had just held onto their original 1 ETH and 100 DAI? Well, now we can easily see that, at the new price, the total value would be 220 DAI. So our liquidity provider lost out by 0.91 DAI by providing liquidity to Uniswap instead of just holding onto their initial ETH and DAI.


Of course, if the price were to return to the same value as when the liquidity provider added their liquidity, this loss would disappear. This loss is only realised when the liquidity provider withdraws their liquidity, and is based on the divergence in price between deposit and withdrawal. We can therefore call it divergence loss (previously described as impermanent loss). Using the equations above, we can derive a formula for the size of the divergence loss in terms of the price ratio between when liquidity was supplied and now. We get the following:


`divergence_loss = 2 * sqrt(price_ratio) / (1+price_ratio) — 1`


Which we can plot out to get a general sense of the scale of the divergence loss at different price ratios:

Or to put it another way:

- 1.25x price change results in a 0.6% loss relative to HODL
- 1.50x price change results in a 2.0% loss relative to HODL
- 1.75x price change results in a 3.8% loss relative to HODL
- 2x price change results in a 5.7% loss relative to HODL
- 3x price change results in a 13.4% loss relative to HODL
- 4x price change results in a 20.0% loss relative to HODL
- 5x price change results in a 25.5% loss relative to HODL

N.B. The loss is the same whichever direction the price change occurs in (i.e. a doubling in price results in the same loss as a halving).

## Returns for Liquidity Providers in Practice

So the actual return for liquidity providers is a balance between the divergence loss caused by the price differential and the accumulated fees from trades on the exchange. Since all trades are recorded on the blockchain we can take a look how this has played out since the mainnet launch of Uniswap. Let’s keep looking at the ETH <-> DAI exchange.
The very first liquidity provider on the ETH <-> DAI exchange was account 0xf369af914dBed0aD7afdDdEbc631Ee0FDA1b4891, which provided 30 ETH and 5900 DAI (i.e. at a price of 1 ETH = 196.67 DAI) to initiate the exchange in block 6629139 on 2 November 2018. This account has so far not added or withdrawn any liquidity since this initial transaction and as of block 7047556 still holds 5.6% of the total liquidity tokens on the ETH <-> DAI exchange contract.


On the following chart we have the net position of account 0xf369af914dBed0aD7afdDdEbc631Ee0FDA1b4891 at every point from block 6629139 until block 7047556. Using the formulae above, we also have the divergence loss and the accumulated fees. All figures have been converted into DAI for ease of comparison.

This chart shows that for most of the time since providing liquidity, this account has been in a net negative position (yellow line), compared to just holding the original funds. This is due to the large divergence losses (blue line) created by the ETH price movements (green line) over the period. However, throughout there has been a steady accumulation of fees (red line). With the ETH price recently moving closer to the price at which liquidity was provided, most of the losses have now been reversed.


If the ETH price were to return to exactly the same as it was at block 6629139, this account would have gained the equivalent of 255.60 DAI in fees, which amounts to a return of 2.2% in 70 days, or an annualised rate of about 11.8%. Note however that this rate applies only to the first two months of the exchange’s existence, and we should expect it will change in future.


The return from fees depends on many factors not explored here, and there will always be some loss from price differential to take into account. As shown above, if long term price movements are large, they could result in losses much greater than the return from fees. However, if Uniswap manages to gain enough traction it could be profitable for liquidity providers, dependent on price movements.


All of which is to say, providing liquidity to a Uniswap exchange is an interesting way to discover the emerging world of decentralised finance. Uniswap has the potential to earn a return on your ETH and ERC-20 tokens, without having to entrust your funds to any third party, but comes with its own set of risks and trade-offs.