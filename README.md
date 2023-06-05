<h1 align="center">How to use query string step by step</h1>

### Step-1

```jsx
npm install query-string
```

### step-2

```jsx
const navigate = useNavigate()
  const [params, setParams] = useSearchParams()
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

### setpe-3 last step:)

```
  const [params, setParams] = useSearchParams()
  const category = params.get('category')
  const [rooms, setRooms] = useState([])
  const [loading, setLoading] = useState(false)
  useEffect(() => {
    setLoading(true)
    fetch(`/Rooms.json`)
      .then(response => response.json())
      .then(data => {
        if (category) {
          const filtered = data.filter(room => room.category === category)
          setRooms(filtered)
        }
        else {
          setRooms(data)
        }
        setLoading(false)
      }).catch(error => console.log(`404 page not found ${error}`))
  }, [category])
  ```
