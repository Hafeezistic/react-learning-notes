# useHistory

```jsx
function ServiceDetail() {
    const {serviceId} = useParams()
    const history = useHistory()
    const thisService = serviceData.find(service => service._id === serviceId)
    
    // Go to a new page
    history.push("/somewhere")
    
    // Go back
    history.goBack()
    // Equals to:
    history.go(-1)
    
    // Replace current page in history array
    history.replace("/somewhere")
}
```