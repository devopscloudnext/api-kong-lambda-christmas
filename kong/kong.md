
# Kong configuration

## Services and routes
We need to configure the different services, routes and plugins to make the link between API calls and aws-lambda functions execution.
In the kong configuration logic, services are the upstream service that you want to target and routes are the way the consumers are calling kong to reach the services.
Then, different plugins, such as security, traffic control or serverless call can be set up either at the services or at the routes level.

When calling aws lambda functions, there is no upstreams service that are called. However we still need to set up services.
One choice is to implement logical services and configure one route per lambda function.

In our case, we well setup a products service with the differents route for GET /products, POST /products, GET /products/{product_id}, PUT /products/{product_id} and DELETE /products/{product_id}, and a deliveries service with only one route POST /deliveries

## Plugins


