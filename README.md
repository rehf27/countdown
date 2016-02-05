# Countdown

## Countdown Web UI



## Countdown API

### /events
GET returns list of events sorted descending from the most popular (i.e., most subscriptions) event

### /events/:name
GET = return countdown event
POST = create countdown event

### /subscriptions/:name
GET return list of subscriptions to the event, specified by name
POST create a subscription to the event

### /subscriptions/:subcriptionid
GET return list of subscriptions to the event
DELETE remove the specified subscription

### /users/:username
GET returns information on the user
POST creates a user
DELETE removes a user and all associated events and subscriptions

### Event Object
```
{
  eventid: internal unique identifier
  name:  string that conforms to twitter hashtag
  description: string that describes the event that is being counted down to
  when: timestamp for the event
  where: geo location data for event location
  owner: userid of person creating the event
  created-on: timestamp for creation of this record
}
```

### Subscription Object
```
{
  subcriptionid: unique identifier for this subscription document
  eventName: name of the event subscribed to
  subscriber: userid of the person subscribing to the event; cannot be the owner of the event
}
```

### User Object
```
{
  userid: unique internal identifier
  username: unique user name (use Twitter handle)
  email: email address of the user
  oauthToken: access token for Twitter
}
```
