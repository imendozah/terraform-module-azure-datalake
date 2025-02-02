# Configuration options

* [Required arguments](#required-arguments)
   * [data_lake_name](#data_lake_name)
   * [region](#region)
   * [storage_replication](#storage_replication)
   * [cosmosdb_consistency_level](#cosmosdb_consistency_level)
   * [data_warehouse_dtu](#data_warehouse_dtu)
   * [sql_server_admin_username](#sql_server_admin_username)
   * [sql_server_admin_password](#sql_server_admin_password)
   * [service_principal_end_date](#service_principal_end_date)
* [Optional arguments](#optional-arguments)


## Required arguments

### `data_lake_name`

The name of the data lake. This name will be used in every resource so that you can clearly distinguish which resources were created by this module.

Modifying this value after deployment will result in destroying and deploying the complete data lake.

Type: string\
Example: `"example name"`

### `region`

The primary Azure region in which to deploy the data lake. Further configuration options allow to use secondary regions for fail-over and replication purposes.

Modifying this value after deployment will result in destroying and deploying the complete data lake.

Type: string\
Example: `"eastus2"`

### `storage_replication`

Replication strategy to be used for the data lake storage.\
[Available options](https://docs.microsoft.com/en-us/azure/storage/common/storage-redundancy)

Type: string\
Example: `"ZRS"`

### `cosmosdb_consistency_level`

Default consistency level for the CosmosDB account.\
[Available consistency levels](https://docs.microsoft.com/en-us/azure/cosmos-db/consistency-levels)

Type: string\
Example: `"Session"`

### `data_warehouse_dtu`

The provisioned Data Warehouse Units for the Azure db Analytics instance. We recommend to scale this as you go.\
[Data Warehouse Units](https://docs.microsoft.com/en-us/azure/synapse-analytics/sql-data-warehouse/what-is-a-data-warehouse-unit-dwu-cdwu)

Required unless you disable the Synapse Analytics Instance with `provision_synapse` set to `false`\
Type: string\
Example: `"DW100c"`

### `sql_server_admin_username`

The admin username of the SQL server that hosts the Synapse Analytics instance.

Required unless you disable the Synapse Analytics Instance with `provision_synapse` set to `false`\
Type: string\
Example: `"theboss"`

### `sql_server_admin_password`

The password of the admin account of the SQL server that hosts the Synapse Analytics instance.

Required unless you disable the Synapse Analytics Instance with `provision_synapse` set to `false`\
Type: string\
Example: `"ThisIsA$ecret1"`

### `service_principal_end_date`

This module uses a service principal to allow communication between the different Azure services. The service principal will no longer be valid after this time.

Type: string\
Example: `"2030-01-01T00:00:00Z"`

## Optional arguments

Please see [the Terraform registry page](https://registry.terraform.io/modules/datarootsio/azure-datalake/module/?tab=inputs)
