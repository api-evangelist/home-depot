# Home Depot GraphQL Schema

## Overview

This conceptual GraphQL schema represents the Home Depot retail API domain, modeling the product catalog, pricing, inventory, store information, project services, and loyalty programs available through the Home Depot platform. The schema is derived from the capabilities exposed via the Home Depot REST API at https://developer.homedepot.com/ and the broader public-facing retail experience.

## Provider

- **Name:** Home Depot
- **API Base:** https://api.homedepot.com
- **Developer Portal:** https://developer.homedepot.com/
- **Industry:** Home Improvement Retail, E-Commerce

## Schema Design

The schema is organized around the following primary domains:

### Product Catalog
Types covering the full product hierarchy — departments, sections, aisles, bays, categories — down to individual SKUs, UPCs, model numbers, and manufacturer data. Product details include dimensions, weight, images, and rich descriptive content.

### Pricing
Multiple price tiers are modeled explicitly: online price, in-store price, Pro pricing, discounted/sale price, and bulk pricing. This reflects the reality that Home Depot surfaces different prices to different customer segments and channels.

### Availability and Inventory
Online availability and per-store inventory are separate concerns. Fulfillment modes — Buy Online Pick Up In Store (BOPIS), Buy Online Deliver From Store (BODFS), in-store only, and online only — are each represented as distinct types.

### Store
Store details include location, hours, services offered (Pro Desk, Tool Rental Center), and store map references. Each store carries its own inventory records linked to products.

### Delivery and Fulfillment
Dedicated types for standard delivery, appliance delivery, furniture delivery, large-item delivery, and truck rental reflect Home Depot's broad fulfillment surface.

### Pro Services
Pro Account, ProXtra loyalty, Pro Credit, and the Pro Desk at stores are modeled to support the contractor and professional customer segment.

### Project and Installation Services
Project guides, installation services, and local ad services represent the content and service layer Home Depot offers beyond simple product transactions.

### Reviews and Q&A
Customer reviews with ratings and seller responses, plus a question-and-answer system, are modeled to reflect the product engagement layer.

### Authentication
API key and token types support the developer-facing authentication model described in the Home Depot developer portal.

## File

- `home-depot-schema.graphql` — Full GraphQL SDL with 60+ named types

## Usage

This schema is conceptual. It is intended for use in API design discussions, mock server generation, client code generation experiments, and documentation tooling. It is not an officially published GraphQL API from Home Depot.
