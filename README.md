# Group an array of objects by key
```
      let cars = [
        {
          'make': 'audi',
          'model': 'r8',
          'year': '2012'
        }, {
          'make': 'audi',
          'model': 'rs5',
          'year': '2013'
        }, {
          'make': 'ford',
          'model': 'mustang',
          'year': '2012'
        }, {
          'make': 'ford',
          'model': 'fusion',
          'year': '2015'
        }, {
          'make': 'kia',
          'model': 'optima',
          'year': '2012'
        }
      ]
      
      let result = cars.reduce((r, a) => {
        r[a.date] = r[a.date] || []
        r[a.date].push(a)
        return r
      }, {})
```
At the result we get
```
{
    'audi': [
        {
            'make': 'audi',
            'model': 'r8',
            'year': '2012'
        }, {
            'make': 'audi',
            'model': 'rs5',
            'year': '2013'
        },
    ],
    'ford': [
        {
            'make': 'ford',
            'model': 'mustang',
            'year': '2012'
        }, {
            'make': 'ford',
            'model': 'fusion',
            'year': '2015'
        }
    ],
    'kia': [
        {
            'make': 'kia',
            'model': 'optima',
            'year': '2012'
        }
    ]
}
```

# Count
```
      let result = cars.reduce((r, a) => {
        r[a.make] = r[a.make] || 0
        r[a.make] += 1
        return r
      }, {})
```
Result
```
{
    'audi': 2,
    'ford': 2,
    'kia': 1
}
