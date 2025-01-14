---
# ----------------------------------------------------------------------------
#
#     ***     AUTO GENERATED CODE    ***    Type: MMv1     ***
#
# ----------------------------------------------------------------------------
#
#     This file is automatically generated by Magic Modules and manual
#     changes will be clobbered when the file is regenerated.
#
#     Please read more about how to change this file in
#     .github/CONTRIBUTING.md.
#
# ----------------------------------------------------------------------------
subcategory: "GKEHub"
description: |-
  Namespace represents a namespace across the Fleet.
---

# google\_gke\_hub\_namespace

Namespace represents a namespace across the Fleet.


To get more information about Namespace, see:

* [API documentation](https://cloud.google.com/anthos/fleet-management/docs/reference/rest/v1/projects.locations.scopes.namespaces)
* How-to Guides
    * [Registering a Cluster](https://cloud.google.com/anthos/multicluster-management/connect/registering-a-cluster#register_cluster)

## Example Usage - Gkehub Namespace Basic


```hcl
resource "google_gke_hub_scope" "namespace" {
  scope_id = "tf-test-scope%{random_suffix}"
}


resource "google_gke_hub_namespace" "namespace" { 
  scope_namespace_id = "tf-test-namespace%{random_suffix}"
  scope_id = "tf-test-scope%{random_suffix}"
  scope = "${google_gke_hub_scope.namespace.name}"
  depends_on = [google_gke_hub_scope.namespace]
}
```

## Argument Reference

The following arguments are supported:


* `scope_namespace_id` -
  (Required)
  The client-provided identifier of the namespace.

* `scope` -
  (Required)
  The name of the Scope instance.

* `scope_id` -
  (Required)
  Id of the scope


- - -


* `project` - (Optional) The ID of the project in which the resource belongs.
    If it is not provided, the provider project is used.


## Attributes Reference

In addition to the arguments listed above, the following computed attributes are exported:

* `id` - an identifier for the resource with format `projects/{{project}}/locations/global/scopes/{{scope_id}}/namespaces/{{scope_namespace_id}}`

* `name` -
  The resource name for the namespace

* `uid` -
  Google-generated UUID for this resource.

* `create_time` -
  Time the Namespace was created in UTC.

* `update_time` -
  Time the Namespace was updated in UTC.

* `delete_time` -
  Time the Namespace was deleted in UTC.

* `state` -
  State of the namespace resource.
  Structure is [documented below](#nested_state).


<a name="nested_state"></a>The `state` block contains:

* `code` -
  (Output)
  Code describes the state of a Namespace resource.

## Timeouts

This resource provides the following
[Timeouts](https://developer.hashicorp.com/terraform/plugin/sdkv2/resources/retries-and-customizable-timeouts) configuration options:

- `create` - Default is 20 minutes.
- `delete` - Default is 20 minutes.

## Import


Namespace can be imported using any of these accepted formats:

```
$ terraform import google_gke_hub_namespace.default projects/{{project}}/locations/global/scopes/{{scope_id}}/namespaces/{{scope_namespace_id}}
$ terraform import google_gke_hub_namespace.default {{project}}/{{scope_id}}/{{scope_namespace_id}}
$ terraform import google_gke_hub_namespace.default {{scope_id}}/{{scope_namespace_id}}
```

## User Project Overrides

This resource supports [User Project Overrides](https://registry.terraform.io/providers/hashicorp/google/latest/docs/guides/provider_reference#user_project_override).
