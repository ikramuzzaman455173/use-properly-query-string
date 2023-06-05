<h1 align="center">How to use query string step by step</h1>

### Step-1

```jsx
npm install query-string
```

### step-2

```jsx
const navigate = useNavigate()
  const [params, setParams] = useSearchParams()
  const value = params.get('category')

  const handleClick = () => {
    let currentQuery = {}
    if (params) {
      currentQuery=qs.parse(params.toString())
    }
    const updatedQuery = {
      ...currentQuery,category:label
    }
    const url = qs.stringifyUrl({
      url: '/',
      query:updatedQuery
    }, { skipNull: true })
    navigate(url)
  }
```
