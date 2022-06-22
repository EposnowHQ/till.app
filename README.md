# Transaction Data model

```typescript
class Product {
    ProductID: number;
    Quantity: number;
    ItemPrice: number;
    IsTaxExempt: boolean;
    constructor(productId: number, quantity?: number, productPrice?: number, taxExempted?: boolean);
}

class MiscItem {
    Name: string;
    Price: number;
    MiscProductID?: number;
    TaxRateID?: number;
    TaxGroupID?: number;
    constructor(name: string, price: number, miscProductId?: number, taxRateId?: number, taxGroupdId?: number);
}

class TransactionDetail {
    Name: string;
    Details: string;
    constructor(name: string, details: string);
}

class Tender {
    TypeID: number;
    Amount: number;
    constructor(typeId: number, amount: number);
}

class Discount {
    reasonId: number;
    amount?: number;
    percentage?: number;
    constructor(reasonId: number, amount?: number, percentage?: number);
}

class Transaction {
    CustomerId?: number;
    MiscItems: Array<MiscItem>;
    Products: Array<Product>;
    Tenders: Array<Tender>;
    TransactionDetails: Array<string>;
    Discount?: Discount;
    constructor(customerId?: number);
}

class TransactionPublisher {
    static window: any;
    static register(window: any): void;
    static publish(transactionData: Transaction): void;
}
```