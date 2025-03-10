---
description: Updates a federated graph on the control plane.
---

# Update

## Usage

```bash
npx wgc federated-graph update <name> [-r, --routing-url <url>] [--label-matcher <labels...>]
```

{% hint style="info" %}
**Update** is an irreversible action. However, the change will only be visible to the routers once the composition has been successful. Until then, the routers will operate with the most recent valid composition. Please use [federated-graph check](check.md) to understand the impact of your change.
{% endhint %}

## Description

The `npx wgc federated-graph update` command allows you to update an existing federated graph on the Cosmo platform's control plane. With this command, you can modify the routing URL of your router and update the labels used to select the subgraphs to be federated.

## Parameters

* `<name>`: The name of the federated graph you want to update. Replace `<name>` with the name of the federated graph you wish to modify.

## Options

```bash
-r <routing-url>, --routing-url <routing-url>
```

The updated routing URL of your router. This URL defines the endpoint where the router will be accessible. The federated graph will be accessible through this updated router URL.

```bash
--label-matcher <labels...>
```

The updated labels used to select the subgraphs to be federated. Labels are passed in the format `<key>=<value> <key>=<value>`, where each `<key>=<value>` pair represents a label key and its corresponding value. The federated graph will include the subgraphs that match the updated labels.

## Examples

```bash
npx wgc federated-graph update production -r http://new-router.example.com/graphql --selector team=B department=Engineering
```

Update the federated graph named "production" with an updated routing URL of "[http://new-router.example.com/graphql](http://new-router.example.com/graphql)" and update the labels to select subgraphs with "team=B" and "department=Engineering".

## Notes

* The `npx wgc federated-graph update` command interacts with the Cosmo platform's control plane to update the specified federated graph. Ensure that you have the necessary permissions to perform this operation.
* If you want to update both the routing URL and labels, you can combine the options in a single command as demonstrated in the examples.
