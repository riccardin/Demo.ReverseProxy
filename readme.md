Using YARP

The most obvious use-case for many of you reading this ar- ticle is to use a reverse proxy to provide an API gateway for microservices. A reverse proxy can expose a server that rep- resents a single surface area for requests. The details of how the service is implemented and where the actual service re- sides are made opaque to the actual clients. This is what I call service aggregation. In this case, a reverse proxy is used to accept calls from clients and then pass them off to the under- lying service (or cluster of services). This allows you to change the composition of the microservice without breaking clients.

You can use service aggregation to marry disparate systems without having to rewrite or change the underlying tech- nology. For example, you might have a Java system from an acquisition, a .NET project that’s built in-house, and a Python machine learning project that you have to integrate. By using a reverse proxy, you can create a union of all these services to provide a single API service area for these differ- ent technologies.

Configuring the Reverse Proxy

In YARP, the reverse proxy needs to know what the pattern is that you’re looking for in requests and where to pass the requests to. It uses the term Routes for the request patterns and uses Clusters to represent the computers(s) to forward those requests. This means that you need a way of providing the proxy with a set of Routes and Clusters. 


By calling the LoadFromConfig, the proxy expects a section that conforms to the schema of the proxy configuration. It doesn’t matter what you call the section, as long as it’s a set of Routes and Clusters


https://microsoft.github.io/reverse-proxy/articles/getting-started.html