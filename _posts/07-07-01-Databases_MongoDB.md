---
isChild: true
title:   MongoDB
anchor:  databases_mongodb
---

## MongoDB {#databases_mongodb_title}

[MongoDB][1] is a leading NoSQL database that stores data in JSON-like documents, providing flexibility and scalability for various application needs. MongoDB can support multiple data models, making it versatile for different use cases.

### Features of MongoDB

- **Document Model**: Uses a JSON-like format to store data, which is more expressive and flexible.
- **Scalability**: Supports horizontal scaling through sharding.
- **Aggregation Framework**: Powerful querying and data aggregation capabilities.
- **High Performance**: Optimized for read and write operations.
- **Advanced Indexing**: MongoDB offers a comprehensive range of indexing options, including standard compound indexes, text indexes, vector indexes, and geospatial indexes.
- **Multi-Model Support**: MongoDB can support key-value, graph, and time-series data models, providing a comprehensive solution for various data needs.

### MongoDB as a Multi-Model Database

- **Key-Value Data**: MongoDB's flexible schema allows it to efficiently store key-value pairs, making it suitable for caching and session storage.
- **Graph Data**: MongoDB supports graph processing and storage through its rich document model, enabling complex relationships and queries similar to graph databases.
- **Time-Series Data**: MongoDB's native support for time-series data, with features like time-series collections, makes it ideal for IoT, financial data, and other applications requiring efficient time-based data storage and querying.

### MongoDB and PHP

MongoDB provides a robust driver for PHP, enabling developers to interact with MongoDB databases from their PHP applications.

#### Installing the MongoDB PHP Driver

To install the MongoDB PHP driver, you can use the following commands:

```shell
# Install the MongoDB extension for PHP
sudo pecl install mongodb

# Enable the extension in your php.ini file
echo "extension=mongodb.so" >> <YOUR_PHP_INI_PATH>/php.ini
```

#### Using the MongoDB PHP Library
Once the driver is installed, you can use the MongoDB PHP library to connect to your MongoDB database and perform operations. Here's an example:

```php
<?php

require 'vendor/autoload.php'; // include Composer's autoloader

$client = new MongoDB\Client("mongodb://localhost:27017");
$collection = $client->demo->beers;

// Insert a document
$result = $collection->insertOne(['name' => 'Hinterland', 'brewery' => 'Coopers', 'abv' => 5.5]);
echo "Inserted with Object ID '{$result->getInsertedId()}'";

// Query a document
$beer = $collection->findOne(['name' => 'Hinterland']);
echo "Beer: ", $beer['name'], " Brewery: ", $beer['brewery'], " ABV: ", $beer['abv'], "\n";

?>
```


For more information, refer to the official [MongoDB PHP documentation][2].


[1]: https://www.mongodb.com/
[2]: https://www.mongodb.com/docs/drivers/php-drivers/