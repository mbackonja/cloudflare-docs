---
_build:
  publishResources: false
  render: never
  list: never
---

1. In [Zero Trust](https://one.dash.cloudflare.com/), go to **Gateway** > **Resolver policies**.
2. Select **Add a policy**.
3. Create an expression for your desired traffic. For example, you can resolve a hostname for an internal service:

    | Selector | Operator | Value                  |
    | -------- | -------- | ---------------------- |
    | Host     | in       | `internal.example.com` |

4. In **Select DNS resolver**, choose _Configure custom DNS resolvers_.
5. Enter the IP addresses of your custom DNS resolver.
6. In **Network**, choose whether to route queries publicly (to the Internet) or privately (to a private network service).
7. (Optional) Enter a custom port for each IP address.
8. Select **Create policy**.

Custom resolvers are saved to your account for future use. When users first connect to Zero Trust, Gateway will send a query to all resolvers listed, returning and caching the first response for use in subsequent queries. Resolver priority is cached on a per user basis for each data center.
