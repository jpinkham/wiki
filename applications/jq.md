# jq

```text
curl -q < url > | jq '.results[].name'
```

JSON being parsed:

```text
{
  "results": [
      {
        "name": "ItalianRestaurantLmnop.com",
        "availability": "available"
      },
      {
        "name": "ItalianCuisineLmnop.com",
        "availability": "available"
      },
      {
        "name": "ItalianRestaurantLmnopOnline.com",
        "availability": "available"
      }
  ]
}
```

