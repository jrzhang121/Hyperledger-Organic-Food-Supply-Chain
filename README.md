# Hyperledger-Organic-Food-Supply-Chain

How to test our network?

1. Download the empty-business-network.bna in the repository.

2. In a browser, navigate to the online Bluemix Composer Playground http://composer-playground.mybluemix.net and choose to deploy a new business network.

3. In the new page, upload empty-business-network.bna BNA file into the Playground  and click “deploy” as the following picture shows.
![alt text](https://github.com/jrzhang121/Hyperledger-Organic-Food-Supply-Chain/blob/master/newNet.png)


4. Then create a distributor and manufacturer using the following testing code.

```
{
  "$class": "org.hcsc.network.Distributor",
  "tradeId": "D1",
  "companyName": "Better",
  "address": {
    "$class": "org.hcsc.network.Address"
  }
}

{
  "$class": "org.hcsc.network.Manufacturer",
  "tradeId": "M1",
  "companyName": "FAST",
  "address": {
    "$class": "org.hcsc.network.Address"
  }
}
```


5. Go to “IDRegistery” to issue two new ID, one for the Distributor and the other for the Manufacturer. Then Use the Manufacturer Identity to do the following 3 steps.

![alt text](https://github.com/jrzhang121/Hyperledger-Organic-Food-Supply-Chain/blob/master/IDRegistry.png)

![alt text](https://github.com/jrzhang121/Hyperledger-Organic-Food-Supply-Chain/blob/master/IssueID.png)

![alt text](https://github.com/jrzhang121/Hyperledger-Organic-Food-Supply-Chain/blob/master/UseM1.png)


6. As a manufacturer, create a commodity using the following code.

```
{
  "$class": "org.hcsc.network.Commodity",
  "tradingSymbol": "ts1",
  "name": "Ali",
  "description": "Aliquip.",
  "quantity": 216.3,
  "trace": [],
  "owner": "resource:org.hcsc.network.Manufacturer#M1"
}
```


7. As a manufacturer, transfer the commodity you just created using the following code.
```
{
  "$class": "org.hcsc.network.TransferCommodity",
  "commodity": "resource:org.hcsc.network.Commodity#ts1",
  "issuer": "resource:org.hcsc.network.Manufacturer#M1",
  "newOwner":Cod"resource:org.hcsc.network.Distributor#D1",
  "shipperLocation": {
    "$class": "org.hcsc.network.Address"
  }
}
```


8. Click “View all transactions” on the left bottom to view all transctions.

![alt text](https://github.com/jrzhang121/Hyperledger-Organic-Food-Supply-Chain/blob/master/ViewTran.png)

