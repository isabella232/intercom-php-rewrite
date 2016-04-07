## Clients

```php
$client = new IntercomClient(appId, apiKey);
```

## Users

```php
// Create/update a user
$client->users->create([
  'email' => 'test@intercom.io'
]);

// Add companies to a user
$client->users->create([
  'email' => 'test@intercom.io',
  "companies" => [
    [
      "id" => "3"
    ]
  ]
]);

// Find user by email
$client->users->getUsers(['email' => 'bob@intercom.io']);
```

## Events

```php
// Create an event
$client->events->create([
  "event_name" => "testing",
  "created_at" => 1391691571,
  "email" => "test@intercom.io"
]);

// View events for a user
$client->events->getEvents(["email" => "bob@intercom.io"]);
```

## Companies

```php
// Create a company
$client->companies->create([
  "name" => "foocorp", "id" => "3"
]);

// List Companies
$client->companies->getCompanies([])
```

## Messages

```php
// Send a message from an admin to a user
// See more options here: https://developers.intercom.io/reference#conversations
$client->messages->create([
  "message_type" => "inapp",
  "subject" => "Hey",
  "body" => "Ponies, cute small horses or something more sinister?",
  "from" => [
    "type" => "admin",
    "id" => "1234"
  ],
  "to" => [
    "type" => "user",
    "email" => "bob@intercom.io"
  ]
])
```

## conversations

```php
// List conversations for an admin
// See more options here: https://developers.intercom.io/reference#list-conversations
$client->conversations->getConversations([
  "type" => "admin",
  "admin_id" => "25610"
])
```
