Deleting a document is similar, in process, to reading an item. You need the id and the value of the partition key path.

```csharp
string id = "027D0B9A-F9D9-4C96-8213-C8546C4AAE71";
string categoryId = "26C74104-40BC-4541-8EF5-9892F7F03D72";
PartitionKey partitionKey = new (categoryId);
```

Once you have both of those values, you invoke the asynchronous **DeleteItemAsync\<\>** method in a manner similar to the **ReadItemAsync\<\>** method.

```csharp
await container.DeleteItemAsync<Product>(id, partitionKey);
```

Azure Cosmos DB also supports deleting all documents contained within a single value for a partition key.

```csharp
string categoryId = "26C74104-40BC-4541-8EF5-9892F7F03D72";
PartitionKey partitionKey = new (categoryId);
```

With the partition key value, you invoke the asynchronous **DeleteAllItemsByPartitionKeyStreamAsync\<\>** method.

```csharp
await container.DeleteAllItemsByPartitionKeyStreamAsync<(partitionKey);
```
