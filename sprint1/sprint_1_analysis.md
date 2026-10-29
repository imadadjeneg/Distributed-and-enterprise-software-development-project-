
## Enterprise summary
A food marketplace where producers list products and customers order from one or
several producers in a single checkout. The platform takes 5% commission.
External services: payment, organic certification verification, delivery or
collection, notifications.

## Actors
Customer, Producer, Marketplace Platform (including admin), Payment Service,
Certification Verification Service, Delivery/Collection, Notification Service.

## Process responsibilities
| Process | Owner | Others involved |
|---|---|---|
| Producer registration and onboarding | Platform admin | Producer |
| Product listing and inventory | Producer | Platform (validation), Verification Service |
| Browse, search and basket | Customer | Platform |
| Checkout, order and payment | Platform | Customer, Payment Service, Producer |
| Order fulfilment | Producer | Platform, Delivery/Collection |
| Food quality incident and traceability | Platform admin | Customer, Producer, Notification Service |
| Commission and payouts | Platform (finance) | Producer, Payment Service |

## Process relationships
- Onboarding must happen before a producer can list products.
- Listed products appear in browsing.
- A confirmed order reduces stock; zero stock makes a product unavailable.
- A confirmed incident suspends the product; order data identifies affected customers.
- Confirmed payment triggers commission calculation and producer payouts.

## Proposed major functionalities (pending module team agreement)
1. **Use Case 1: Producer product listing and inventory management.**
   Substantial because it has user tasks (producer submits and corrects data),
   automated decisions (validation, stock rules, seasonal availability), an
   external service (organic verification), and exception paths (service
   unavailable, validation failure).
2. **Use Case 2: Customer multi-vendor order, checkout and payment.**
   Substantial because it spans several actors, splits one order into
   producer-specific parts, calls an external payment service, calculates 5%
   commission, and has retry and decline paths.

The two connect through stock: orders reduce the inventory managed by Use Case 1.