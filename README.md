# SOA App

This is a complete SOA app with main focus on:
  - IoC container usage on the server and on the client (MEF)
  - using of data contracts equality between client and server
  - using of dto contracts for custom entities not saved in the db 
  - using of design factory pattern for creating service managers, repositories, business managers, proxies
  - using of ef code first
      - using of base classes for the entities on the server and on the client
      - entities have base classes that care about security (owned by entity), error handling (on server and client) and state changes
  - using of FluentValidation on the server
  - using of property changed pattern with additional dirty flag
  - WCF 
      - usage of security adapter and SOAPHeader
      - WCF exception handling with a custom pattern (base class)
      - using of service proxies (and taking care of proper disposing)
      - hosting the services (console)
  - web app as customer access to the online shop (MVC with Angular SPA-Silos)
      - added some highlights like rules for client side validation (knockout-like), wrapping of the http services
      - separation of the client, controller, models and contracts in separate assemblies
  - Admin (WPF with MVVM) app
     - admin application that handles products, cart status (approved, shipped)
     - separation of view models in separate assemblies
  - unit tests!
  





  WHAT'S NEXT:
  
  Extending the app (better said: of the ordering process) by adding a transaction and within infrastructure for switching modules and providers (for example: approving order module or shipping cost module) at anytime with no affect on recompiling the main app, only by discovering the modules during the compile time.
  That means: if the first step in chain (chain-of-responsibility pattern) failed (for example shipping cost module throws an error) the next step (for example: sending email notification to the customer) will not be hit at all by the order-pipeline and the complete transaction wiil roll back

  
---------------------------------------------------------------------------------------------------------------------------------------
  
  
Special THX to M. Castro, to the people of knockout, G. Block, S. Smith, B. Balmer - your are awesome
