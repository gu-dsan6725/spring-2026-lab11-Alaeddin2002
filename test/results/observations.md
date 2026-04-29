# observations.md

## A2A Messages 

"Sending message to Flight Booking Agent: I need to book flight ID 1. Please reserve 2 seats, confirm the reservation, and process the payment..."
These lines show that the Travel Assistant sent an request to another service, which returned a successful 200 response. This indicates that an A2A-style request was attempted.

## How
"Successfully fetched agent card data from http://127.0.0.1:10002/.well-known/agent-card.json"


## JSON:

{
  "jsonrpc": "2.0",
  "method": "message/send",
  "params": {
    "message": {
      "role": "user",
      "parts": [
        {
          "kind": "text",
          "text": "I need to book flight ID 1. Please reserve 2 seats, confirm the reservation, and process the payment."
        }
      ],
      "messageId": "82ebc9ddd9b243cba4eb5203045f03d8"
    }
  }
}

## Agent Card:

'name': 'Flight Booking Agent'
'description': 'Flight booking and reservation management agent'
'preferredTransport': 'JSONRPC'
'protocolVersion': '0.3.0'
'url': 'http://127.0.0.1:10002/'

This information was used to identify that the agent supports flight booking tasks and determine how to communicate to send the request to the correct endpoint


The bennifts is that agents can discover each other dynamically instead of hardcoding, also you can have parallel agent handling specific tasks

However, the system depends on the availability of the external agent and if the agent is unreachable, the request fails
