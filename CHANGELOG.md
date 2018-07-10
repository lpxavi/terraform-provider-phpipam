## 0.3.0

Upgrade Terraform version at 0.11.8.

## 0.2.1-pre

Bumped version for dev.

## 0.2.0

New version with some breaking changes regarding custom fields:

 * Custom field searches are not done via the `custom_field_filter` attribute in
   both the `phpipam_address` and `phpipam_subnet` data sources. This parameter
   is a map that takes custom field names, and regular expressions to search for
   against. A field does not match if any of the search criteria keys are
   missing or do not match.

Also have added two new data sources:

 * `phpipam_addresses` will search addresses for a `description`  or `hostname`
   exact match or a `custom_field_filter` match, much like the singular-form
   `phpipam_address` data source. A list of IP address IDs are returned, which
   can then be used to look up addresses with the `phpipam_address` data source.
   This will work better in Terraform v0.9.x, or higher, which has support for a
   computed `count` in data sources now.
 * `phpipam_subnets` has been added in the same way. This one can search on
   `description`, `description_match`, and `custom_field_filter`, in the same
   way the singular-form `phpipam_address` data source can.

## 0.1.2

Added custom field support - this plugin now supports custom fields in
addresses, subnets, and VLANs, as long as those fields are optional. Data source
searching supports addresses and subnets only, due to limitations in VLAN
searching capabilities.

## 0.1.1

Bumping release so that I have a consistent snapshot, and also so that I can
correct some tests on the compat branch.

## 0.1.0

First release!
