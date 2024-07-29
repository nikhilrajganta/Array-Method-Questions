Task 1: High-Value Transactions in 2023
Description: Given an array of transactions, identify transactions that are above $5000, occurred in 2023, and belong to the 'Business' category. Transform this filtered array into an array of strings formatted as "Transaction [id]: $[amount] on [date]".

```js
const highValueTransactions = transactions
  .filter(
    (transaction) =>
      transaction.amount > 5000 &&
      transaction.date.startsWith("2023") &&
      transaction.category === "Business"
  )
  .map(
    (transaction) =>
      `Transaction ${transaction.id}: $${transaction.amount} on ${transaction.date}`
  );

console.log(highValueTransactions);
// Output: ["Transaction T2: $6500 on 2023-02-20"]
```

Task 2: Departmental Salary Expenditure
Description: Calculate the total salary expenditure for each department from an array of departments, each with an array of employees.

```js
const departmentSalaries = departments.map((department) => {
  const totalSalary = department.employees.reduce(
    (sum, employee) => sum + employee.salary,
    0
  );
  return { [department.name]: totalSalary };
});

console.log(departmentSalaries);
// Output: [{ "Engineering": 170000 }, { "Marketing": 125000 }]
```

Task 3: Weather Data Sorting and Structuring
Description: Sort an array of weather data objects in descending order of temperature and restructure the data into an object with dates as keys and temperatures as values.

```js
const sortedWeatherData = weatherData.sort(
  (a, b) => b.temperature - a.temperature
);
const weatherObject = sortedWeatherData.reduce((acc, data) => {
  acc[data.date] = data.temperature;
  return acc;
}, {});

console.log(weatherObject);
// Output: { "2023-03-02": 20, "2023-03-03": 18, "2023-03-01": 16 }
```

Task 4: Analyzing Electronics Products
Description: From an array of products, find products in the 'Electronics' category with more than 50 reviews and a rating of at least 4.0. Calculate the average price of these products.

```js
const filteredProducts = products.filter(
  (product) =>
    product.category === "Electronics" &&
    product.reviews > 50 &&
    product.rating >= 4.0
);
const averagePrice =
  filteredProducts.reduce((sum, product) => sum + product.price, 0) /
  filteredProducts.length;

console.log(averagePrice);
// Output: 199.99 // Assuming only one product meets the criteria
```

Task 5: Merging User and Order Data
Description: Merge two arrays of objects based on a common key (userId) to create a new array of objects that includes each user's name and their corresponding order details.

```js
const mergedData = users.map((user) => {
  const userOrder = orders.find((order) => order.userId === user.userId);
  return {
    name: user.name,
    orderDetails: userOrder ? userOrder.orderDetails : "No order details",
  };
});

console.log(mergedData);
// Output:
// [
//   { name: 'Alice', orderDetails: 'Order 1 Details' },
//   { name: 'Bob', orderDetails: 'Order 2 Details' }
// ]
```
