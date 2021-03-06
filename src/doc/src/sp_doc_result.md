# dhw_self

| Property | Value |
| --- | --- |
| SQL Server Version | 15.0.4083.2 |
| Compatibility Level | 150 |
| Collation | Latin1_General_CI_AS |
----

## Tables

<details><summary>Click to expand</summary>

* [dbo.__RefactorLog](#dbo__refactorlog)
* [dbo.sysdiagrams](#dbosysdiagrams)
* [graph.ProcedureInstance](#graphprocedureinstance)
* [graph.ReferencedObject](#graphreferencedobject)
* [graph.ReferencedObjectColumn](#graphreferencedobjectcolumn)
* [graph.ReferencedProcedureInstance](#graphreferencedprocedureinstance)
* [graph.ReferencingObject](#graphreferencingobject)
* [graph.ReferencingObjectColumn](#graphreferencingobjectcolumn)
* [graph.ReferencingProcedureInstance](#graphreferencingprocedureinstance)
* [graph.RepoObject](#graphrepoobject)
* [graph.RepoObjectColumn](#graphrepoobjectcolumn)
* [repo.dbeaver_DataSources](#repodbeaver_datasources)
* [repo.ExecutionLog](#repoexecutionlog)
* [repo.ForeignKey_virtual](#repoforeignkey_virtual)
* [repo.GeneratorUsp](#repogeneratorusp)
* [repo.GeneratorUspParameter](#repogeneratoruspparameter)
* [repo.GeneratorUspStep](#repogeneratoruspstep)
* [repo.Index_Settings](#repoindex_settings)
* [repo.Index_virtual](#repoindex_virtual)
* [repo.IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T](#repoindexcolumn_referencedreferencing_hasfullcolumnsinreferencing_t)
* [repo.IndexColumn_virtual](#repoindexcolumn_virtual)
* [repo.Parameter](#repoparameter)
* [repo.ProcedureInstance](#repoprocedureinstance)
* [repo.ProcedureInstanceDependency](#repoprocedureinstancedependency)
* [repo.RepoObject](#reporepoobject)
* [repo.RepoObject_Inheritance_temp](#reporepoobject_inheritance_temp)
* [repo.RepoObject_persistence](#reporepoobject_persistence)
* [repo.RepoObject_QueryPlan](#reporepoobject_queryplan)
* [repo.RepoObject_SqlModules](#reporepoobject_sqlmodules)
* [repo.RepoObject_SqlModules_41_from_T](#reporepoobject_sqlmodules_41_from_t)
* [repo.RepoObject_SqlModules_61_SelectIdentifier_Union_T](#reporepoobject_sqlmodules_61_selectidentifier_union_t)
* [repo.RepoObjectColumn](#reporepoobjectcolumn)
* [repo.RepoObjectColumn_Inheritance_temp](#reporepoobjectcolumn_inheritance_temp)
* [repo.RepoObjectColumnProperty](#reporepoobjectcolumnproperty)
* [repo.RepoObjectProperty](#reporepoobjectproperty)
* [repo.RepoObjectSource_FirstResultSet](#reporepoobjectsource_firstresultset)
* [repo.RepoObjectSource_QueryPlan](#reporepoobjectsource_queryplan)
* [repo.spt_values](#repospt_values)
* [repo.Workflow](#repoworkflow)
* [repo.WorkflowStep](#repoworkflowstep)

### dbo.__RefactorLog

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **OperationKey** | UNIQUEIDENTIFIER | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK____Refact__D3AEFFDB3C1358E2** | clustered | [OperationKey] |  |  |

[Back to top](#dhw_self)

### dbo.sysdiagrams

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| name | SYSNAME(128) | no |  |  |  |
| principal_id | INT | no |  |  |  |
| **diagram_id** | INT | no |  |  |  |
| version | INT | yes |  |  |  |
| definition | VARBINARY(MAX) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK__sysdiagr__C2B05B610C172C5D** | clustered | [diagram_id] |  |  |
| UK_principal_name | nonclustered | [principal_id], [name] |  |  |

[Back to top](#dhw_self)

### graph.ProcedureInstance

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_3091B0F8FDFD4CCBAA8FF240634B29BA | BIGINT | no |  |  |  |
| $node_id_3FC7AA841B564294B72482DE078E7EB2 | NVARCHAR(1000) | no |  |  |  |
| Procedure_RepoObject_guid | UNIQUEIDENTIFIER | no |  |  |  |
| Instance | VARCHAR(500) | no |  |  |  |
| Procedure_fullname | NVARCHAR(261) | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| UK_ProcedureInstance | nonclustered | [Procedure_RepoObject_guid], [Instance] |  |  |
| ix_graphid | nonclustered | [graph_id_3091B0F8FDFD4CCBAA8FF240634B29BA] |  |  |

[Back to top](#dhw_self)

### graph.ReferencedObject

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_85ECDD019A4C46AF80CFD8DDFA08F479 | BIGINT | no |  |  |  |
| $edge_id_25B0DD35E10A49DE8B49228E6802F3EB | NVARCHAR(1000) | no |  |  |  |
| from_obj_id_A00C6316716D4F9DABE96A189F3A214A | INT | no |  |  |  |
| from_id_7F3CEF660D794A2A81530928BC4B36F1 | BIGINT | no |  |  |  |
| $from_id_7B1BEB60463741CAA681054A489A2714 | NVARCHAR(1000) | yes |  |  |  |
| to_obj_id_F1F1771130674EE9A9DAE06330740E13 | INT | no |  |  |  |
| to_id_45A2D6271B224A08B66CA0CF6A200A54 | BIGINT | no |  |  |  |
| $to_id_26820C41BE034B00BCBC470518101233 | NVARCHAR(1000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| ix_toid | nonclustered | [to_obj_id_F1F1771130674EE9A9DAE06330740E13], [to_id_45A2D6271B224A08B66CA0CF6A200A54], [from_obj_id_A00C6316716D4F9DABE96A189F3A214A], [from_id_7F3CEF660D794A2A81530928BC4B36F1] |  |  |
| ix_graphid | nonclustered | [graph_id_85ECDD019A4C46AF80CFD8DDFA08F479] |  |  |
| ix_fromid | nonclustered | [from_obj_id_A00C6316716D4F9DABE96A189F3A214A], [from_id_7F3CEF660D794A2A81530928BC4B36F1], [to_obj_id_F1F1771130674EE9A9DAE06330740E13], [to_id_45A2D6271B224A08B66CA0CF6A200A54] |  |  |

[Back to top](#dhw_self)

### graph.ReferencedObjectColumn

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_E9F774DD8CA2460A924F6173983BE220 | BIGINT | no |  |  |  |
| $edge_id_7C154492F0954C769C843FC0BEA97AFC | NVARCHAR(1000) | no |  |  |  |
| from_obj_id_11EC88C0730D4B5993BF0DBC6FAC2E36 | INT | no |  |  |  |
| from_id_7E00AE91C08D4B1FA35C7A8270AC9E8C | BIGINT | no |  |  |  |
| $from_id_F5982CB6A96041F69453F5D5DBE84FFB | NVARCHAR(1000) | yes |  |  |  |
| to_obj_id_1AB5BC0BD7FD4956AA05F7CB026BC43D | INT | no |  |  |  |
| to_id_085F365914414A0AAB9A494884264043 | BIGINT | no |  |  |  |
| $to_id_9D5378D2AACD4945A48693ABF17CD063 | NVARCHAR(1000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| ix_toid | nonclustered | [to_obj_id_1AB5BC0BD7FD4956AA05F7CB026BC43D], [to_id_085F365914414A0AAB9A494884264043], [from_obj_id_11EC88C0730D4B5993BF0DBC6FAC2E36], [from_id_7E00AE91C08D4B1FA35C7A8270AC9E8C] |  |  |
| ix_graphid | nonclustered | [graph_id_E9F774DD8CA2460A924F6173983BE220] |  |  |
| ix_fromid | nonclustered | [from_obj_id_11EC88C0730D4B5993BF0DBC6FAC2E36], [from_id_7E00AE91C08D4B1FA35C7A8270AC9E8C], [to_obj_id_1AB5BC0BD7FD4956AA05F7CB026BC43D], [to_id_085F365914414A0AAB9A494884264043] |  |  |

[Back to top](#dhw_self)

### graph.ReferencedProcedureInstance

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_3B4F4C8DE4004062A81B80F5771A7B02 | BIGINT | no |  |  |  |
| $edge_id_B521900E7C4346FB8BB29CABEB4D685C | NVARCHAR(1000) | no |  |  |  |
| from_obj_id_40CD653F2A264D648347F31A48C0E8CE | INT | no |  |  |  |
| from_id_5664C7BB1E104901A7EDD5E6403E2878 | BIGINT | no |  |  |  |
| $from_id_1446655ABD294143804D865FA056AC97 | NVARCHAR(1000) | yes |  |  |  |
| to_obj_id_B31D2838ADC24684AC8096F0FB22420E | INT | no |  |  |  |
| to_id_E6180570FCE8459F8C23D8745FB060DE | BIGINT | no |  |  |  |
| $to_id_3E6CC1F8200444C9A5A492A11DC985A8 | NVARCHAR(1000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| ix_graphid | nonclustered | [graph_id_3B4F4C8DE4004062A81B80F5771A7B02] |  |  |

[Back to top](#dhw_self)

### graph.ReferencingObject

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_09F977CF6E984C91A3DCB80DFCA167DF | BIGINT | no |  |  |  |
| $edge_id_21A14F7820EC4E65A2181C77070E4599 | NVARCHAR(1000) | no |  |  |  |
| from_obj_id_841F6E8E64074738851E57246A265384 | INT | no |  |  |  |
| from_id_472B24420B624B14BB7713C2D61A6825 | BIGINT | no |  |  |  |
| $from_id_0076F61972EE4CFBAB773755DA860F3E | NVARCHAR(1000) | yes |  |  |  |
| to_obj_id_E20461DCDFE345938DA61BDA2DFCEDB6 | INT | no |  |  |  |
| to_id_481A7B86C080421583F830CBBB2D1D40 | BIGINT | no |  |  |  |
| $to_id_24A0471B483E40D58582E894797FDBD5 | NVARCHAR(1000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| ix_toid | nonclustered | [to_obj_id_E20461DCDFE345938DA61BDA2DFCEDB6], [to_id_481A7B86C080421583F830CBBB2D1D40], [from_obj_id_841F6E8E64074738851E57246A265384], [from_id_472B24420B624B14BB7713C2D61A6825] |  |  |
| ix_graphid | nonclustered | [graph_id_09F977CF6E984C91A3DCB80DFCA167DF] |  |  |
| ix_fromid | nonclustered | [from_obj_id_841F6E8E64074738851E57246A265384], [from_id_472B24420B624B14BB7713C2D61A6825], [to_obj_id_E20461DCDFE345938DA61BDA2DFCEDB6], [to_id_481A7B86C080421583F830CBBB2D1D40] |  |  |

[Back to top](#dhw_self)

### graph.ReferencingObjectColumn

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_33EABAD1D448423BA763A06B2E100A3D | BIGINT | no |  |  |  |
| $edge_id_DC70EA9971F145D9892721EBFAD6DA3B | NVARCHAR(1000) | no |  |  |  |
| from_obj_id_E30A518916BD429EAA4BC746BAB803B8 | INT | no |  |  |  |
| from_id_AF95740FA51A459CAD5E73CCDA2BB9A1 | BIGINT | no |  |  |  |
| $from_id_E02FBFD790F541C5888A72743EC0C66D | NVARCHAR(1000) | yes |  |  |  |
| to_obj_id_B789CEA675414B248EC7F2E6F9E8738E | INT | no |  |  |  |
| to_id_BC6FD8D77D2B4F3292EFDF7454BE0A57 | BIGINT | no |  |  |  |
| $to_id_82344FE7FA59415C82FF9A4D37C1712A | NVARCHAR(1000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| ix_toid | nonclustered | [to_obj_id_B789CEA675414B248EC7F2E6F9E8738E], [to_id_BC6FD8D77D2B4F3292EFDF7454BE0A57], [from_obj_id_E30A518916BD429EAA4BC746BAB803B8], [from_id_AF95740FA51A459CAD5E73CCDA2BB9A1] |  |  |
| ix_graphid | nonclustered | [graph_id_33EABAD1D448423BA763A06B2E100A3D] |  |  |
| ix_fromid | nonclustered | [from_obj_id_E30A518916BD429EAA4BC746BAB803B8], [from_id_AF95740FA51A459CAD5E73CCDA2BB9A1], [to_obj_id_B789CEA675414B248EC7F2E6F9E8738E], [to_id_BC6FD8D77D2B4F3292EFDF7454BE0A57] |  |  |

[Back to top](#dhw_self)

### graph.ReferencingProcedureInstance

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_3FBBD480757F476A85886E45589A9D62 | BIGINT | no |  |  |  |
| $edge_id_E2A8F9D9A24449B5BAE820B4BB23822F | NVARCHAR(1000) | no |  |  |  |
| from_obj_id_5CEA66987D9E42DBAE22CF16CA1C3747 | INT | no |  |  |  |
| from_id_FD05B9C9B3BA40E49E694BB9BC5A6D74 | BIGINT | no |  |  |  |
| $from_id_386A079B46584E798B0577A575C29FC1 | NVARCHAR(1000) | yes |  |  |  |
| to_obj_id_48A3CDC6D0CC441F944A873BD5D76140 | INT | no |  |  |  |
| to_id_9A496F83379F4B998E2F491BADCA4286 | BIGINT | no |  |  |  |
| $to_id_B0CB742D8F37433F82DB8262698B1A4A | NVARCHAR(1000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| ix_graphid | nonclustered | [graph_id_3FBBD480757F476A85886E45589A9D62] |  |  |

[Back to top](#dhw_self)

### graph.RepoObject

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_60367FDA1A70430CA390F8144C223EC4 | BIGINT | no |  |  |  |
| $node_id_FAC3EF4690DB4CD6A98F097DAF0885CC | NVARCHAR(1000) | no |  |  |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |  |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| RepoObject_type | CHAR(2) | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| UK_RepoObject | nonclustered | [RepoObject_guid] |  |  |
| ix_graphid | nonclustered | [graph_id_60367FDA1A70430CA390F8144C223EC4] |  |  |

[Back to top](#dhw_self)

### graph.RepoObjectColumn

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| graph_id_58E017E29B684D7FBC6E4E880C609245 | BIGINT | no |  |  |  |
| $node_id_347F7C762E2642A98518838371CE6BB1 | NVARCHAR(1000) | no |  |  |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |  |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |  |  |
| RepoObject_type | CHAR(2) | no |  |  |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |  |  |
| RepoObjectColumn_fullname | NVARCHAR(520) | yes |  |  |  |
| RepoObjectColumn_type | NVARCHAR(128) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| UK_RepoObjectColumn | nonclustered | [RepoObjectColumn_guid] |  |  |
| ix_graphid | nonclustered | [graph_id_58E017E29B684D7FBC6E4E880C609245] |  |  |

[Back to top](#dhw_self)

### repo.dbeaver_DataSources

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| BulkColumn | VARCHAR(MAX) | yes |  |  |  |
| is_json | INT | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_dbeaver_DataSources** | clustered | [id] |  |  |

[Back to top](#dhw_self)

### repo.ExecutionLog

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | BIGINT | no |  |  |  |
| parent_execution_log_id | BIGINT | yes |  |  |  |
| created_dt | DATETIME | yes |  |  |  |
| proc_schema_name | NVARCHAR(128) | yes |  |  |  |
| proc_name | NVARCHAR(128) | yes |  |  |  |
| step_id | INT | yes |  |  |  |
| step_name | NVARCHAR(1000) | yes |  |  |  |
| source_object | NVARCHAR(261) | yes |  |  |  |
| target_object | NVARCHAR(261) | yes |  |  |  |
| inserted | INT | yes |  |  |  |
| updated | INT | yes |  |  |  |
| deleted | INT | yes |  |  |  |
| current_execution_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| execution_instance_guid | UNIQUEIDENTIFIER | no |  |  |  |
| ssis_execution_id | BIGINT | yes |  |  |  |
| sub_execution_id | INT | yes |  |  |  |
| proc_id | INT | yes |  |  |  |
| info_01 | SQL_VARIANT | yes |  |  |  |
| info_02 | SQL_VARIANT | yes |  |  |  |
| info_03 | SQL_VARIANT | yes |  |  |  |
| info_04 | SQL_VARIANT | yes |  |  |  |
| info_05 | SQL_VARIANT | yes |  |  |  |
| info_06 | SQL_VARIANT | yes |  |  |  |
| info_07 | SQL_VARIANT | yes |  |  |  |
| info_08 | SQL_VARIANT | yes |  |  |  |
| info_09 | SQL_VARIANT | yes |  |  |  |
| event_info | NVARCHAR(MAX) | yes |  |  |  |
| parameter_01 | SQL_VARIANT | yes |  |  |  |
| parameter_02 | SQL_VARIANT | yes |  |  |  |
| parameter_03 | SQL_VARIANT | yes |  |  |  |
| parameter_04 | SQL_VARIANT | yes |  |  |  |
| parameter_05 | SQL_VARIANT | yes |  |  |  |
| parameter_06 | SQL_VARIANT | yes |  |  |  |
| parameter_07 | SQL_VARIANT | yes |  |  |  |
| parameter_08 | SQL_VARIANT | yes |  |  |  |
| parameter_09 | SQL_VARIANT | yes |  |  |  |
| parameter_10 | SQL_VARIANT | yes |  |  |  |
| parameter_11 | SQL_VARIANT | yes |  |  |  |
| parameter_12 | SQL_VARIANT | yes |  |  |  |
| parameter_13 | SQL_VARIANT | yes |  |  |  |
| parameter_14 | SQL_VARIANT | yes |  |  |  |
| parameter_15 | SQL_VARIANT | yes |  |  |  |
| parameter_16 | SQL_VARIANT | yes |  |  |  |
| parameter_17 | SQL_VARIANT | yes |  |  |  |
| parameter_18 | SQL_VARIANT | yes |  |  |  |
| parameter_19 | SQL_VARIANT | yes |  |  |  |
| parameter_20 | SQL_VARIANT | yes |  |  |  |
| proc_fullname | NVARCHAR(517) | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_ExecutionLog** | clustered | [id] |  |  |

[Back to top](#dhw_self)

### repo.ForeignKey_virtual

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **ForeignKey_guid** | UNIQUEIDENTIFIER | no |  | (newsequentialid()) |  |
| is_ForeignKey_disabled | BIT | no |  | ((0)) |  |
| ForeignKey_name | NVARCHAR(128) | yes |  |  |  |
| referencing_index_guid | UNIQUEIDENTIFIER | yes | [[repo].[Index_Settings].[index_guid]](#repoindex_settings) |  |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes | [[repo].[Index_Settings].[index_guid]](#repoindex_settings) |  |  |
| delete_referential_action | TINYINT | no |  | ((0)) |  |
| update_referential_action | TINYINT | no |  | ((0)) |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_ForeignKey_virtual** | clustered | [ForeignKey_guid] |  |  |

[Back to top](#dhw_self)

### repo.GeneratorUsp

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| usp_schema | NVARCHAR(128) | no |  |  |  |
| usp_name | NVARCHAR(128) | no |  |  |  |
| has_logging | TINYINT | no |  | ((1)) |  |
| usp_Description | NVARCHAR(4000) | yes |  |  |  |
| usp_fullname | NVARCHAR(261) | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_GeneratorUsp** | clustered | [id] |  |  |
| UK_GeneratorUsp_Schema_Name | nonclustered | [usp_schema], [usp_name] |  |  |

[Back to top](#dhw_self)

### repo.GeneratorUspParameter

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| usp_id | INT | no | [[repo].[GeneratorUsp].[id]](#repogeneratorusp) |  |  |
| Number | INT | no |  |  |  |
| Name | NVARCHAR(128) | no |  |  |  |
| UserTypeFullname | NVARCHAR(128) | no |  |  |  |
| is_inactive | TINYINT | no |  | ((0)) |  |
| is_out | TINYINT | no |  | ((0)) |  |
| has_DefaultValue | TINYINT | no |  | ((0)) |  |
| DefaultValue | NVARCHAR(MAX) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_GeneratorUspParameter** | clustered | [id] |  |  |
| UK_GeneratorUspParameter_Number | nonclustered | [usp_id], [Number] |  |  |
| UK_GeneratorUspParameter_name | nonclustered | [usp_id], [Name] |  |  |

[Back to top](#dhw_self)

### repo.GeneratorUspStep

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| usp_id | INT | no | [[repo].[GeneratorUsp].[id]](#repogeneratorusp) |  |  |
| Number | INT | no |  |  |  |
| Parent_Number | INT | yes |  |  |  |
| Name | NVARCHAR(1000) | yes |  |  |  |
| has_logging | TINYINT | no |  | ((1)) |  |
| is_condition | TINYINT | no |  | ((0)) |  |
| is_inactive | TINYINT | no |  | ((0)) |  |
| is_SubProcedure | TINYINT | no |  | ((0)) | use info_01, info_02, ... to define parameters for sub procedure call |
| Statement | NVARCHAR(MAX) | yes |  |  |  |
| log_source_object | NVARCHAR(261) | yes |  |  |  |
| log_target_object | NVARCHAR(261) | yes |  |  |  |
| log_flag_InsertUpdateDelete | CHAR(1) | yes |  |  |  |
| info_01 | NVARCHAR(MAX) | yes |  |  |  |
| info_02 | NVARCHAR(MAX) | yes |  |  |  |
| info_03 | NVARCHAR(MAX) | yes |  |  |  |
| info_04 | NVARCHAR(MAX) | yes |  |  |  |
| info_05 | NVARCHAR(MAX) | yes |  |  |  |
| info_06 | NVARCHAR(MAX) | yes |  |  |  |
| info_07 | NVARCHAR(MAX) | yes |  |  |  |
| info_08 | NVARCHAR(MAX) | yes |  |  |  |
| info_09 | NVARCHAR(MAX) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_GeneratorUspStep** | clustered | [id] |  |  |
| UK_GeneratorUspStep_Number | nonclustered | [usp_id], [Number] |  |  |

[Back to top](#dhw_self)

### repo.Index_Settings

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **index_guid** | UNIQUEIDENTIFIER | no |  |  |  |
| IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |  |  |
| IndexPatternColumnName | NVARCHAR(4000) | yes |  |  |  |
| IndexSemanticGroup | NVARCHAR(512) | yes |  |  |  |
| is_create_constraint | BIT | no |  | ((0)) |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_Index_Settings** | clustered | [index_guid] |  |  |

[Back to top](#dhw_self)

### repo.Index_virtual

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **index_guid** | UNIQUEIDENTIFIER | no |  | (newsequentialid()) |  |
| has_managedName | BIT | no |  | ((1)) |  |
| index_name | NVARCHAR(128) | yes |  |  |  |
| index_type | TINYINT | no |  | ((0)) | Type of index:<br/>0 = Heap<br/>1 = Clustered<br/>2 = Nonclustered<br/>3 = XML<br/>4 = Spatial<br/>5 = Clustered columnstore index. Applies to: SQL Server 2014 (12.x) and later.<br/>6 = Nonclustered columnstore index. Applies to: SQL Server 2012 (11.x) and later.<br/>7 = Nonclustered hash index. Applies to: SQL Server 2014 (12.x) and later. |
| is_index_disabled | BIT | no |  | ((0)) |  |
| is_index_primary_key | BIT | no |  | ((0)) |  |
| is_index_unique | BIT | no |  | ((0)) |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| RowNumberInReferencing | INT | yes |  |  | the same index can be inherited several times into the same referenced object, if a source is used several times<br/>for example<br/>SELECT A_A = A.A, B_A = B.A from source_1 as A LEFT JOIN source_1 as B ON ... <br/>normaly these indexes should have different columns |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_Index_virtual** | clustered | [index_guid] |  |  |

[Back to top](#dhw_self)

### repo.IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| is_descending_key | BIT | yes |  |  |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| index_column_id | INT | no |  |  |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| RowNumberInReferencing | BIGINT | yes |  |  |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |  |  |

[Back to top](#dhw_self)

### repo.IndexColumn_virtual

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **index_guid** | UNIQUEIDENTIFIER | no | [[repo].[Index_virtual].[index_guid]](#repoindex_virtual) |  |  |
| **index_column_id** | INT | no |  |  | consecutive number of the column within the index.<br/>sys.index_columns.index_column_id: "ID of the index column. index_column_id is unique only within index_id."<br/> |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObjectColumn].[RepoObjectColumn_guid]](#reporepoobjectcolumn) |  |  |
| is_descending_key | BIT | no |  | ((0)) |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_IndexColumn_unique** | clustered | [index_guid], [index_column_id] |  |  |

[Back to top](#dhw_self)

### repo.Parameter

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **Parameter_name** | VARCHAR(100) | no |  |  |  |
| **sub_Parameter** | NVARCHAR(128) | no |  | ('') |  |
| Parameter_desciption | NVARCHAR(1000) | yes |  |  |  |
| Parameter_default_value | SQL_VARIANT | yes |  |  |  |
| Parameter_value | SQL_VARIANT | yes |  |  |  |
| Parameter_value__result_nvarchar | NVARCHAR(4000) | yes |  |  |  |
| Parameter_value__result_int | INT | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_Parameter** | clustered | [Parameter_name], [sub_Parameter] |  |  |

[Back to top](#dhw_self)

### repo.ProcedureInstance

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| Procedure_RepoObject_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| Instance | VARCHAR(500) | no |  | ('') |  |
| Description | NVARCHAR(4000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_ProcedureInstance** | clustered | [id] |  |  |
| UK_ProcedureInstance | nonclustered | [Procedure_RepoObject_guid], [Instance] |  |  |

[Back to top](#dhw_self)

### repo.ProcedureInstanceDependency

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| referenced_id | INT | no | [[repo].[ProcedureInstance].[id]](#repoprocedureinstance) |  |  |
| referencing_id | INT | no | [[repo].[ProcedureInstance].[id]](#repoprocedureinstance) |  |  |
| is_active | BIT | no |  | ((1)) |  |
| is_PersistenceDependency | BIT | no |  | ((0)) |  |
| Description | NVARCHAR(4000) | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_ProcedureInstanceDependency** | clustered | [id] |  |  |
| UK_ProcedureInstanceDependency | nonclustered | [referenced_id], [referencing_id] |  |  |

[Back to top](#dhw_self)

### repo.RepoObject

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObject_guid** | UNIQUEIDENTIFIER | no |  | (newsequentialid()) |  |
| has_different_sys_names | BIT | yes |  |  |  |
| has_execution_plan_issue | BIT | yes |  |  |  |
| has_get_referenced_issue | BIT | yes |  |  |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |  |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |  |  |
| InheritanceType | TINYINT | yes |  |  |  |
| is_repo_managed | BIT | yes |  |  |  |
| is_SysObject_missing | BIT | yes |  |  |  |
| modify_dt | DATETIME | no |  | (getdate()) |  |
| pk_index_guid | UNIQUEIDENTIFIER | yes | [[repo].[Index_Settings].[index_guid]](#repoindex_settings) |  |  |
| Repo_history_table_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| Repo_temporal_type | TINYINT | yes |  |  | reference in [repo_sys].[type] |
| RepoObject_name | NVARCHAR(128) | no |  | (newid()) |  |
| RepoObject_Referencing_Count | INT | yes |  |  |  |
| RepoObject_schema_name | NVARCHAR(128) | no |  |  |  |
| RepoObject_type | CHAR(2) | no |  |  | reference in [repo_sys].[type] |
| SysObject_id | INT | yes |  |  |  |
| SysObject_modify_date | DATETIME | yes |  |  |  |
| SysObject_name | NVARCHAR(128) | no |  | (newid()) |  |
| SysObject_parent_object_id | INT | no |  | ((0)) |  |
| SysObject_schema_name | NVARCHAR(128) | no |  |  |  |
| SysObject_type | CHAR(2) | yes |  |  | reference in [repo_sys].[type] |
| is_RepoObject_name_uniqueidentifier | INT | no |  |  |  |
| is_SysObject_name_uniqueidentifier | INT | no |  |  |  |
| node_id | BIGINT | yes |  |  |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| SysObject_fullname | NVARCHAR(261) | no |  |  |  |
| SysObject_query_sql | NVARCHAR(406) | no |  |  |  |
| usp_persistence_name | NVARCHAR(140) | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObject** | clustered | [RepoObject_guid] |  |  |
| UK_RepoObject__SysNames | nonclustered | [SysObject_schema_name], [SysObject_name] |  |  |
| UK_RepoObject__RepoNames | nonclustered | [RepoObject_schema_name], [RepoObject_name] |  |  |

#### Triggers
##### repo.RepoObject__after_delete
###### Definition
<details><summary>Click to expand</summary>


```sql

```

</details>
##### repo.RepoObject__after_update
###### Definition
<details><summary>Click to expand</summary>


```sql

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_Inheritance_temp

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |  |  |
| property_name | NVARCHAR(128) | no |  |  |  |
| property_value | SQL_VARIANT | yes |  |  |  |
| property_value_new | SQL_VARIANT | yes |  |  |  |
| InheritanceType | INT | yes |  |  |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |  |  |
| is_force_inherit_empty_source | INT | no |  |  |  |
| is_StringAggAllSources | INT | no |  |  |  |
| resulting_InheritanceDefinition | NVARCHAR(4000) | yes |  |  |  |
| RowNumberSource | BIGINT | yes |  |  |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| referenced_RepoObject_name | NVARCHAR(128) | no |  |  |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| referencing_RepoObject_name | NVARCHAR(128) | no |  |  |  |

[Back to top](#dhw_self)

### repo.RepoObject_persistence

| Description |
| --- |
| extra table is required to allow FK with<br/>ON UPDATE CASCADE<br/>ON DELETE CASCADE | 

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **target_RepoObject_guid** | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| has_history | BIT | no |  | ((0)) |  |
| has_history_columns | BIT | no |  | ((0)) |  |
| history_schema_name | NVARCHAR(128) | yes |  |  |  |
| history_table_name | NVARCHAR(128) | yes |  |  |  |
| is_persistence_check_duplicate_per_pk | BIT | no |  | ((0)) |  |
| is_persistence_check_for_empty_source | BIT | no |  | ((0)) |  |
| is_persistence_delete_changed | BIT | no |  | ((0)) |  |
| is_persistence_delete_missing | BIT | no |  | ((0)) |  |
| is_persistence_insert | BIT | no |  | ((1)) |  |
| is_persistence_truncate | BIT | no |  | ((1)) |  |
| is_persistence_update_changed | BIT | no |  | ((0)) |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| is_persistence | BIT | yes |  |  |  |
| temporal_type | TINYINT | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObject_persistence** | clustered | [target_RepoObject_guid] |  |  |

[Back to top](#dhw_self)

### repo.RepoObject_QueryPlan

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObject_guid** | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| SysObject_query_executed_dt | DATETIME | yes |  |  |  |
| SysObject_query_plan | XML | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObject_QueryPlan** | clustered | [RepoObject_guid] |  |  |

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObject_guid** | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| sql_modules_dt | DATETIME | no |  | (getdate()) |  |
| sql_modules_formatted | NVARCHAR(MAX) | yes |  |  |  |
| sql_modules_formatted2 | NVARCHAR(MAX) | yes |  |  |  |
| sql_modules_json | NVARCHAR(MAX) | yes |  |  |  |
| is_json_sql_modules_json | INT | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObject_SqlModules** | clustered | [RepoObject_guid] |  |  |

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_41_from_T

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| children | NVARCHAR(MAX) | yes |  |  |  |
| class | NVARCHAR(500) | yes |  |  |  |
| identifier_alias | NVARCHAR(MAX) | yes |  |  |  |
| identifier_name | NVARCHAR(MAX) | yes |  |  |  |
| is_from | INT | no |  |  |  |
| is_group | BIT | yes |  |  |  |
| is_join | INT | no |  |  |  |
| is_keyword | BIT | yes |  |  |  |
| is_whitespace | BIT | yes |  |  |  |
| join_type | VARCHAR(16) | yes |  |  |  |
| json_key | NVARCHAR(4000) | no |  |  |  |
| Min_RowNumber_From | BIGINT | yes |  |  |  |
| Min_RowNumber_GroupBy | BIGINT | yes |  |  |  |
| Min_RowNumber_Where | BIGINT | yes |  |  |  |
| normalized | NVARCHAR(MAX) | yes |  |  |  |
| normalized_PatIndex_Select | BIGINT | yes |  |  |  |
| normalized_wo_nolock | NVARCHAR(MAX) | yes |  |  |  |
| patindex_nolock | BIGINT | yes |  |  |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |  |  |
| RowNumber_per_Object | BIGINT | yes |  |  |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |  |  |

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_61_SelectIdentifier_Union_T

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| alias_QuoteName | NVARCHAR(MAX) | yes |  |  |  |
| class | NVARCHAR(500) | yes |  |  |  |
| normalized | NVARCHAR(MAX) | yes |  |  |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |  |  |
| RowNumber_per_Object | BIGINT | yes |  |  |  |
| source_column_QuoteName | NVARCHAR(MAX) | yes |  |  |  |
| source_table_QuoteName | NVARCHAR(MAX) | yes |  |  |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |  |  |

[Back to top](#dhw_self)

### repo.RepoObjectColumn

| Description |
| --- |
|  | 

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObjectColumn_guid** | UNIQUEIDENTIFIER | no |  | (newsequentialid()) |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |  |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |  |  |
| InheritanceType | TINYINT | yes |  |  |  |
| is_persistence_no_check | BIT | yes |  |  |  |
| is_persistence_no_include | BIT | yes |  |  |  |
| is_persistence_no_update | BIT | yes |  |  |  |
| is_query_plan_expression | BIT | yes |  |  |  |
| is_SysObjectColumn_missing | BIT | yes |  |  |  |
| persistence_source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| Referencing_Count | INT | yes |  |  |  |
| Repo_default_definition | NVARCHAR(MAX) | yes |  |  |  |
| Repo_default_is_system_named | BIT | yes |  |  |  |
| Repo_default_name | NVARCHAR(128) | yes |  |  |  |
| Repo_definition | NVARCHAR(MAX) | yes |  |  |  |
| Repo_generated_always_type | TINYINT | no |  | ((0)) | Applies to: SQL Server 2016 (13.x) and later, SQL Database.<br/>Identifies when the column value is generated (will always be 0 for columns in system tables):<br/>0 = NOT_APPLICABLE<br/>1 = AS_ROW_START<br/>2 = AS_ROW_END<br/>For more information, see Temporal Tables (Relational databases). |
| Repo_graph_type | INT | yes |  |  | https://docs.microsoft.com/en-us/sql/relational-databases/graphs/sql-graph-architecture<br/><br/>The sys.columns view contains additional columns graph_type and graph_type_desc, that indicate the type of the column in node and edge tables.<br/><br/>graph_type<br/>int<br/>Internal column with a set of values. The values are between 1-8 for graph columns and NULL for others.<br/><br/>graph_type_desc<br/>nvarchar(60)<br/>internal column with a set of values<br/><br/>Column Value	Description<br/>1	GRAPH_ID<br/>2	GRAPH_ID_COMPUTED<br/>3	GRAPH_FROM_ID<br/>4	GRAPH_FROM_OBJ_ID<br/>5	GRAPH_FROM_ID_COMPUTED<br/>6	GRAPH_TO_ID<br/>7	GRAPH_TO_OBJ_ID<br/>8	GRAPH_TO_ID_COMPUTED |
| Repo_is_computed | BIT | no |  | ((0)) |  |
| Repo_is_identity | BIT | no |  | ((0)) |  |
| Repo_is_nullable | BIT | yes |  |  |  |
| Repo_is_persisted | BIT | yes |  |  |  |
| Repo_seed_value | SQL_VARIANT | yes |  |  |  |
| Repo_increment_value | SQL_VARIANT | yes |  |  |  |
| Repo_user_type_name | NVARCHAR(128) | yes |  |  |  |
| Repo_user_type_fullname | NVARCHAR(128) | yes |  |  |  |
| Repo_uses_database_collation | BIT | yes |  |  |  |
| RepoObjectColumn_column_id | INT | yes |  |  | ID of the column. Is unique within the object.<br/>Column IDs might not be sequential. |
| RepoObjectColumn_name | NVARCHAR(128) | no |  | (newid()) | Name of the column. Is unique within the object. |
| RepoObject_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| SysObjectColumn_column_id | INT | yes |  |  | ID of the column. Is unique within the object.<br/>Column IDs might not be sequential. |
| SysObjectColumn_name | NVARCHAR(128) | no |  | (newid()) | Name of the column. Is unique within the object.<br/>if it not exists in the database, the RepoObject_guid or any other guid is used, because this column should not be empty |
| has_different_sys_names | BIT | yes |  |  |  |
| is_RepoObjectColumn_name_uniqueidentifier | INT | no |  |  |  |
| is_SysObjectColumn_name_uniqueidentifier | INT | no |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObjectColumn** | clustered | [RepoObjectColumn_guid] |  |  |
| UK_RepoObjectColumn__SysNames | nonclustered | [RepoObjectColumn_guid], [SysObjectColumn_name] |  |  |
| UK_RepoObjectColumn__RepoNames | nonclustered | [RepoObject_guid], [RepoObjectColumn_name] |  |  |

[Back to top](#dhw_self)

### repo.RepoObjectColumn_Inheritance_temp

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |  |  |
| property_name | NVARCHAR(128) | no |  |  |  |
| property_value | SQL_VARIANT | yes |  |  |  |
| property_value_new | SQL_VARIANT | yes |  |  |  |
| InheritanceType | INT | yes |  |  |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |  |  |
| is_force_inherit_empty_source | INT | no |  |  |  |
| is_StringAggAllSources | INT | no |  |  |  |
| resulting_InheritanceDefinition | NVARCHAR(4000) | yes |  |  |  |
| RowNumberSource | BIGINT | yes |  |  |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |  |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| referenced_RepoObjectColumn_name | NVARCHAR(128) | no |  |  |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | no |  |  |  |
| referencing_RepoObjectColumn_name | NVARCHAR(128) | no |  |  |  |

[Back to top](#dhw_self)

### repo.RepoObjectColumnProperty

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObjectColumnProperty_id** | INT | no |  |  |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObjectColumn].[RepoObjectColumn_guid]](#reporepoobjectcolumn) |  |  |
| property_name | NVARCHAR(128) | no |  |  |  |
| property_value | SQL_VARIANT | no |  |  |  |
| inheritance | TINYINT | yes |  |  |  |
| property_basetype | SQL_VARIANT | yes |  |  |  |
| property_int | INT | yes |  |  |  |
| property_bigint | BIGINT | yes |  |  |  |
| property_varchar | VARCHAR(8000) | yes |  |  |  |
| property_nvarchar | NVARCHAR(4000) | yes |  |  |  |
| property_real | REAL | yes |  |  |  |
| property_float | FLOAT | yes |  |  |  |
| property_money | MONEY | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObjectColumnProperty** | clustered | [RepoObjectColumnProperty_id] |  |  |
| UK_RepoObjectColumnProperty | nonclustered | [RepoObjectColumn_guid], [property_name] |  |  |

[Back to top](#dhw_self)

### repo.RepoObjectProperty

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObjectProperty_id** | INT | no |  |  |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| property_name | NVARCHAR(128) | no |  |  |  |
| property_value | SQL_VARIANT | yes |  |  |  |
| inheritance | TINYINT | yes |  |  |  |
| property_basetype | SQL_VARIANT | yes |  |  |  |
| property_int | INT | yes |  |  |  |
| property_bigint | BIGINT | yes |  |  |  |
| property_varchar | VARCHAR(8000) | yes |  |  |  |
| property_nvarchar | NVARCHAR(4000) | yes |  |  |  |
| property_real | REAL | yes |  |  |  |
| property_float | FLOAT | yes |  |  |  |
| property_money | MONEY | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObjectProperty** | clustered | [RepoObjectProperty_id] |  |  |
| UK_RepoObjectProperty | nonclustered | [RepoObject_guid], [property_name] |  |  |

[Back to top](#dhw_self)

### repo.RepoObjectSource_FirstResultSet

| Description |
| --- |
| references on column level<br/>target: repo.RepoObjectSource<br/>source: sys.dm_exec_describe_first_result_set | 

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **RepoObject_guid** | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| **column_ordinal** | INT | no |  |  |  |
| target_column_name | NVARCHAR(128) | yes |  |  |  |
| source_server_name | NVARCHAR(128) | yes |  |  |  |
| source_database_name | NVARCHAR(128) | yes |  |  |  |
| source_schema_name | NVARCHAR(128) | yes |  |  |  |
| source_table_name | NVARCHAR(128) | yes |  |  |  |
| source_column_name | NVARCHAR(128) | yes |  |  |  |
| system_type_id | INT | yes |  |  |  |
| system_type_name | NVARCHAR(128) | yes |  |  |  |
| created_dt | DATETIME | no |  |  |  |
| is_hidden | BIT | yes |  |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_RepoObjectSource_FirstResultSet** | clustered | [RepoObject_guid], [column_ordinal] |  |  |

[Back to top](#dhw_self)

### repo.RepoObjectSource_QueryPlan

| Description |
| --- |
| references on column level<br/>target: repo.RepoObjectSource_from_query_plan<br/>source: query plan analysis of the execution of a query like<br/>&#96;Vselect top (1) * into #foo from (SELECT * FROM sss.aaa)&#96;<br/><br/>First update query plan and write them into repo.RepoObject<br/>then analyse the query plans and update results into <br/><br/>EXEC [repo].[usp_RepoObject__update_SysObject_query_plan]<br/>EXEC [repo].[usp_RepoObjectSource_from_query_plan__update]<br/><br/>some query plans can't be extracted, some can be extracted but not analyzed<br/>in this case mark the RepoObject in repo.RepoObject<br/>SET [has_execution_plan_issue] = 1 | 

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no | [[repo].[RepoObject].[RepoObject_guid]](#reporepoobject) |  |  |
| target_column_name | NVARCHAR(128) | yes |  |  |  |
| source_server_name | NVARCHAR(128) | yes |  |  |  |
| source_database_name | NVARCHAR(128) | yes |  |  |  |
| source_schema_name | NVARCHAR(128) | yes |  |  |  |
| source_table_name | NVARCHAR(128) | yes |  |  |  |
| source_column_name | NVARCHAR(128) | yes |  |  |  |
| SysObject_query_executed_dt | DATETIME | yes |  |  |  |
| const_value | NVARCHAR(4000) | yes |  |  |  |
| target_column_info | XML | yes |  |  |  |
| source_column_info | XML | yes |  |  |  |
| const_info | XML | yes |  |  |  |
| is_target_column_name_expression | BIT | yes |  |  |  |
| is_source_column_name_expression | BIT | yes |  |  |  |

[Back to top](#dhw_self)

### repo.spt_values

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| name | NVARCHAR(35) | yes |  |  |  |
| number | INT | no |  |  |  |
| type | NCHAR(3) | no |  |  |  |
| low | INT | yes |  |  |  |
| high | INT | yes |  |  |  |
| status | INT | yes |  |  |  |

[Back to top](#dhw_self)

### repo.Workflow

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| Name | NVARCHAR(500) | no |  |  |  |
| Description | NVARCHAR(4000) | yes |  |  |  |
| is_active | BIT | no |  | ((1)) |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_Workflow** | clustered | [id] |  |  |

[Back to top](#dhw_self)

### repo.WorkflowStep

| Column | Type | Null | Foreign Key | Default | MS_Description |
| --- | --- | --- | --- | --- | --- |
| **id** | INT | no |  |  |  |
| Workflow_id | INT | no | [[repo].[Workflow].[id]](#repoworkflow) |  |  |
| ProcedureInstance_id | INT | no | [[repo].[ProcedureInstance].[id]](#repoprocedureinstance) |  |  |

#### Indexes

| Name | Type | Key Columns | Include Columns | MS_Description |
| --- | --- | --- | --- | --- |
| **PK_WorkflowStep** | clustered | [id] |  |  |
| UK_WorkflowStep | nonclustered | [Workflow_id], [ProcedureInstance_id] |  |  |

[Back to top](#dhw_self)

</details>

## Views

<details><summary>Click to expand</summary>

* [graph.ProcedureInstance_S](#graphprocedureinstance_s)
* [graph.RepoObject_ReferencingReferenced](#graphrepoobject_referencingreferenced)
* [graph.RepoObject_ReferencingReferenced_u_v](#graphrepoobject_referencingreferenced_u_v)
* [graph.RepoObject_S](#graphrepoobject_s)
* [graph.RepoObjectColumn_ReferencingReferenced](#graphrepoobjectcolumn_referencingreferenced)
* [graph.RepoObjectColumn_S](#graphrepoobjectcolumn_s)
* [repo.aaa_test_sql_table_column](#repoaaa_test_sql_table_column)
* [repo.check_IndexColumn_virtual_referenced_setpoint](#repocheck_indexcolumn_virtual_referenced_setpoint)
* [repo.dbeaver_DataSources_connection](#repodbeaver_datasources_connection)
* [repo.dbeaver_DataSources_DbSchemaTable](#repodbeaver_datasources_dbschematable)
* [repo.dbeaver_DataSources_DbSchemaTable_constraint](#repodbeaver_datasources_dbschematable_constraint)
* [repo.dbeaver_DataSources_DbSchemaTable_FK](#repodbeaver_datasources_dbschematable_fk)
* [repo.ExecutionLog_gross](#repoexecutionlog_gross)
* [repo.ExecutionLog_parent](#repoexecutionlog_parent)
* [repo.ExecutionLog_plantUML_Sequence_start_stop](#repoexecutionlog_plantuml_sequence_start_stop)
* [repo.ExtendedProperty_Repo2Sys_level1](#repoextendedproperty_repo2sys_level1)
* [repo.ExtendedProperty_Repo2Sys_level2_RepoObject](#repoextendedproperty_repo2sys_level2_repoobject)
* [repo.ExtendedProperty_Repo2Sys_level2_RepoObjectColumn](#repoextendedproperty_repo2sys_level2_repoobjectcolumn)
* [repo.ExtendedProperty_Repo2Sys_level2_Union](#repoextendedproperty_repo2sys_level2_union)
* [repo.ForeignKey_Index_guid](#repoforeignkey_index_guid)
* [repo.ForeignKey_Index_guid_union](#repoforeignkey_index_guid_union)
* [repo.ForeignKey_IndexPattern](#repoforeignkey_indexpattern)
* [repo.ForeignKey_RelationScript](#repoforeignkey_relationscript)
* [repo.ForeignKey_virtual_Index_guid](#repoforeignkey_virtual_index_guid)
* [repo.GeneratorUsp_filter_persistence](#repogeneratorusp_filter_persistence)
* [repo.GeneratorUsp_ParameterList](#repogeneratorusp_parameterlist)
* [repo.GeneratorUsp_SqlUsp](#repogeneratorusp_sqlusp)
* [repo.GeneratorUsp_StepList](#repogeneratorusp_steplist)
* [repo.GeneratorUspStep_Persistence](#repogeneratoruspstep_persistence)
* [repo.GeneratorUspStep_Persistence_IsInactive_setpoint](#repogeneratoruspstep_persistence_isinactive_setpoint)
* [repo.GeneratorUspStep_Sql](#repogeneratoruspstep_sql)
* [repo.Index_ColumList](#repoindex_columlist)
* [repo.Index_gross](#repoindex_gross)
* [repo.Index_IndexPattern](#repoindex_indexpattern)
* [repo.Index_referencing_IndexPatternColumnGuid](#repoindex_referencing_indexpatterncolumnguid)
* [repo.Index_SqlConstraint_PkUq](#repoindex_sqlconstraint_pkuq)
* [repo.Index_union](#repoindex_union)
* [repo.Index_unique_IndexPatternColumnGuid](#repoindex_unique_indexpatterncolumnguid)
* [repo.Index_virtual_IndexPatternColumnGuid](#repoindex_virtual_indexpatterncolumnguid)
* [repo.Index_virtual_SysObject](#repoindex_virtual_sysobject)
* [repo.IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing](#repoindexcolumn_referencedreferencing_hasfullcolumnsinreferencing)
* [repo.IndexColumn_union](#repoindexcolumn_union)
* [repo.IndexColumn_virtual_gross](#repoindexcolumn_virtual_gross)
* [repo.IndexColumn_virtual_referenced_setpoint](#repoindexcolumn_virtual_referenced_setpoint)
* [repo.IndexReferencedReferencing](#repoindexreferencedreferencing)
* [repo.IndexReferencedReferencing_HasFullColumnsInReferencing](#repoindexreferencedreferencing_hasfullcolumnsinreferencing)
* [repo.InheritanceType](#repoinheritancetype)
* [repo.join_type](#repojoin_type)
* [repo.Match_RepoObject_referenced_UspPersistence](#repomatch_repoobject_referenced_usppersistence)
* [repo.Parameter_default](#repoparameter_default)
* [repo.ProcedureInstanceDependency_gross](#repoprocedureinstancedependency_gross)
* [repo.PropertyName_RepoObject](#repopropertyname_repoobject)
* [repo.PropertyName_RepoObjectColumn](#repopropertyname_repoobjectcolumn)
* [repo.Reference_UspPersistence](#reporeference_usppersistence)
* [repo.RepoObject_ColumnList](#reporepoobject_columnlist)
* [repo.RepoObject_fullname_u_v](#reporepoobject_fullname_u_v)
* [repo.RepoObject_gross](#reporepoobject_gross)
* [repo.RepoObject_InheritanceType_InheritanceDefinition](#reporepoobject_inheritancetype_inheritancedefinition)
* [repo.RepoObject_InheritanceType_resulting_InheritanceDefinition](#reporepoobject_inheritancetype_resulting_inheritancedefinition)
* [repo.RepoObject_persistence_column](#reporepoobject_persistence_column)
* [repo.RepoObject_persistence_ForInput](#reporepoobject_persistence_forinput)
* [repo.RepoObject_persistence_ObjectNames](#reporepoobject_persistence_objectnames)
* [repo.RepoObject_reference_persistence](#reporepoobject_reference_persistence)
* [repo.RepoObject_reference_SqlExpressionDependencies](#reporepoobject_reference_sqlexpressiondependencies)
* [repo.RepoObject_reference_union](#reporepoobject_reference_union)
* [repo.RepoObject_reference_union_node_id](#reporepoobject_reference_union_node_id)
* [repo.RepoObject_ReferenceTree](#reporepoobject_referencetree)
* [repo.RepoObject_RequiredRepoObjectMerge](#reporepoobject_requiredrepoobjectmerge)
* [repo.RepoObject_SqlCreateTable](#reporepoobject_sqlcreatetable)
* [repo.RepoObject_SqlModules_10_statement](#reporepoobject_sqlmodules_10_statement)
* [repo.RepoObject_SqlModules_20_statement_children](#reporepoobject_sqlmodules_20_statement_children)
* [repo.RepoObject_SqlModules_21_statement_children_helper](#reporepoobject_sqlmodules_21_statement_children_helper)
* [repo.RepoObject_SqlModules_22_identifier_alias_AS](#reporepoobject_sqlmodules_22_identifier_alias_as)
* [repo.RepoObject_SqlModules_23_normalized_wo_nolock](#reporepoobject_sqlmodules_23_normalized_wo_nolock)
* [repo.RepoObject_SqlModules_24_IdentifierList_children](#reporepoobject_sqlmodules_24_identifierlist_children)
* [repo.RepoObject_SqlModules_25_IdentifierList_children_IdentifierSplit](#reporepoobject_sqlmodules_25_identifierlist_children_identifiersplit)
* [repo.RepoObject_SqlModules_26_IdentifierList_children_IdentifierSplit_QuoteName](#reporepoobject_sqlmodules_26_identifierlist_children_identifiersplit_quotename)
* [repo.RepoObject_SqlModules_29_1_object_is_union](#reporepoobject_sqlmodules_29_1_object_is_union)
* [repo.RepoObject_SqlModules_29_2_object_is_GroupBy](#reporepoobject_sqlmodules_29_2_object_is_groupby)
* [repo.RepoObject_SqlModules_31_object](#reporepoobject_sqlmodules_31_object)
* [repo.RepoObject_SqlModules_32_ObjectClass](#reporepoobject_sqlmodules_32_objectclass)
* [repo.RepoObject_SqlModules_33_ObjectNormalized](#reporepoobject_sqlmodules_33_objectnormalized)
* [repo.RepoObject_SqlModules_39_object](#reporepoobject_sqlmodules_39_object)
* [repo.RepoObject_SqlModules_41_from](#reporepoobject_sqlmodules_41_from)
* [repo.RepoObject_SqlModules_42_from_Identifier](#reporepoobject_sqlmodules_42_from_identifier)
* [repo.RepoObject_SqlModules_43_from_Identifier](#reporepoobject_sqlmodules_43_from_identifier)
* [repo.RepoObject_SqlModules_44_from_Identifier_QuoteName](#reporepoobject_sqlmodules_44_from_identifier_quotename)
* [repo.RepoObject_SqlModules_51_Identitfier](#reporepoobject_sqlmodules_51_identitfier)
* [repo.RepoObject_SqlModules_52_Identitfier_QuoteName](#reporepoobject_sqlmodules_52_identitfier_quotename)
* [repo.RepoObject_SqlModules_61_SelectIdentifier_Union](#reporepoobject_sqlmodules_61_selectidentifier_union)
* [repo.RepoObject_SqlModules_71_reference_ExpliciteTableAlias](#reporepoobject_sqlmodules_71_reference_explicitetablealias)
* [repo.RepoObject_SqlModules_72_reference_NoTableAlias](#reporepoobject_sqlmodules_72_reference_notablealias)
* [repo.RepoObject_SqlModules_79_reference_union](#reporepoobject_sqlmodules_79_reference_union)
* [repo.RepoObject_SqlModules_Identitfier](#reporepoobject_sqlmodules_identitfier)
* [repo.RepoObject_SqlModules_Repo_Sys](#reporepoobject_sqlmodules_repo_sys)
* [repo.RepoObjectColumn_gross](#reporepoobjectcolumn_gross)
* [repo.RepoObjectColumn_HistValidColums_setpoint](#reporepoobjectcolumn_histvalidcolums_setpoint)
* [repo.RepoObjectColumn_InheritanceType_InheritanceDefinition](#reporepoobjectcolumn_inheritancetype_inheritancedefinition)
* [repo.RepoObjectColumn_InheritanceType_resulting_InheritanceDefinition](#reporepoobjectcolumn_inheritancetype_resulting_inheritancedefinition)
* [repo.RepoObjectColumn_MissingSource_TypeV](#reporepoobjectcolumn_missingsource_typev)
* [repo.RepoObjectColumn_reference_BySamePredecessors](#reporepoobjectcolumn_reference_bysamepredecessors)
* [repo.RepoObjectColumn_reference_FirstResultSet](#reporepoobjectcolumn_reference_firstresultset)
* [repo.RepoObjectColumn_reference_Persistence](#reporepoobjectcolumn_reference_persistence)
* [repo.RepoObjectColumn_reference_QueryPlan](#reporepoobjectcolumn_reference_queryplan)
* [repo.RepoObjectColumn_reference_SqlExpressionDependencies](#reporepoobjectcolumn_reference_sqlexpressiondependencies)
* [repo.RepoObjectColumn_reference_SqlModules](#reporepoobjectcolumn_reference_sqlmodules)
* [repo.RepoObjectColumn_reference_union](#reporepoobjectcolumn_reference_union)
* [repo.RepoObjectColumn_ReferenceTree](#reporepoobjectcolumn_referencetree)
* [repo.RepoObjectColumn_RelationScript](#reporepoobjectcolumn_relationscript)
* [repo.RepoObjectColumnProperty_sys_repo](#reporepoobjectcolumnproperty_sys_repo)
* [repo.RepoObjectProperty_sys_repo](#reporepoobjectproperty_sys_repo)
* [repo.SysColumn_RepoObjectColumn_via_guid](#reposyscolumn_repoobjectcolumn_via_guid)
* [repo.SysColumn_RepoObjectColumn_via_name](#reposyscolumn_repoobjectcolumn_via_name)
* [repo.SysObject_RepoObject_via_guid](#reposysobject_repoobject_via_guid)
* [repo.SysObject_RepoObject_via_name](#reposysobject_repoobject_via_name)
* [repo.SysObjectColumn_QueryPlanExpression](#reposysobjectcolumn_queryplanexpression)
* [repo.type](#repotype)
* [repo.type_level1type_level2type](#repotype_level1type_level2type)
* [repo.visjs_EdgeList_object_test01](#repovisjs_edgelist_object_test01)
* [repo.visjs_nodelist_object_test01](#repovisjs_nodelist_object_test01)
* [repo_sys.ColumnReference](#repo_syscolumnreference)
* [repo_sys.ExtendedProperties](#repo_sysextendedproperties)
* [repo_sys.ExtendedProperties_ParameterForAddUpdateDrop](#repo_sysextendedproperties_parameterforaddupdatedrop)
* [repo_sys.ForeignKey](#repo_sysforeignkey)
* [repo_sys.ForeignKeyColumn](#repo_sysforeignkeycolumn)
* [repo_sys.Index_unique](#repo_sysindex_unique)
* [repo_sys.IndexColumn_unique](#repo_sysindexcolumn_unique)
* [repo_sys.RepoObjectReferenced](#repo_sysrepoobjectreferenced)
* [repo_sys.RepoObjectReferencing](#repo_sysrepoobjectreferencing)
* [repo_sys.sql_expression_dependencies](#repo_syssql_expression_dependencies)
* [repo_sys.SysColumn](#repo_syssyscolumn)
* [repo_sys.SysObject](#repo_syssysobject)
* [sys_self.ExtendedProperties](#sys_selfextendedproperties)
* [sys_self.ExtendedProperties_ParameterForAddUpdateDrop](#sys_selfextendedproperties_parameterforaddupdatedrop)

### graph.ProcedureInstance_S

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Procedure_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| Instance | VARCHAR(500) | no |  |
| Procedure_fullname | NVARCHAR(261) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [graph].[ProcedureInstance_S]
AS
SELECT
 -- 
 [T1].[Procedure_RepoObject_guid]
 , [T1].[Instance]
 , [Procedure_fullname] = [ro].[RepoObject_fullname]
FROM [repo].[ProcedureInstance] AS T1
INNER JOIN [repo].[RepoObject] AS ro
 ON ro.RepoObject_guid = T1.[Procedure_RepoObject_guid]

```

</details>

[Back to top](#dhw_self)

### graph.RepoObject_ReferencingReferenced

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Referencing_fullname | NVARCHAR(261) | yes |  |
| Referencing_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_type | CHAR(2) | yes |  |
| Referenced_fullname | NVARCHAR(261) | yes |  |
| Referenced_guid | UNIQUEIDENTIFIER | yes |  |
| Referenced_type | CHAR(2) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE   View [graph].[RepoObject_ReferencingReferenced]
As
Select
    Object1.[RepoObject_fullname] As Referencing_fullname
  , Object1.[RepoObject_guid]     As Referencing_guid
  , Object1.[RepoObject_type]     As Referencing_type
  , Object2.[RepoObject_fullname] As Referenced_fullname
  , Object2.[RepoObject_guid]     As Referenced_guid
  , Object2.[RepoObject_type]     As Referenced_type
From
    [graph].[RepoObject] As Object1
  , [graph].[ReferencedObject] As referenced
  , [graph].[RepoObject] As Object2
Where MATCH(
    Object1-(referenced)->Object2)


```

</details>

[Back to top](#dhw_self)

### graph.RepoObject_ReferencingReferenced_u_v

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Referencing_fullname | NVARCHAR(261) | yes |  |
| Referencing_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_type | CHAR(2) | yes |  |
| Referenced_fullname | NVARCHAR(261) | yes |  |
| Referenced_guid | UNIQUEIDENTIFIER | yes |  |
| Referenced_type | CHAR(2) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE   View [graph].[RepoObject_ReferencingReferenced_u_v]
As
Select
    Object1.[RepoObject_fullname] As Referencing_fullname
  , Object1.[RepoObject_guid]     As Referencing_guid
  , Object1.[RepoObject_type]     As Referencing_type
  , Object2.[RepoObject_fullname] As Referenced_fullname
  , Object2.[RepoObject_guid]     As Referenced_guid
  , Object2.[RepoObject_type]     As Referenced_type
From
    [graph].[RepoObject] As Object1
  , [graph].[ReferencedObject] As referenced
  , [graph].[RepoObject] As Object2
Where MATCH(
    Object1-(referenced)->Object2)
    And Object1.[RepoObject_type] In ( 'u', 'v' )
    And Object2.[RepoObject_type] In ( 'u', 'v' )

```

</details>

[Back to top](#dhw_self)

### graph.RepoObject_S

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_type | CHAR(2) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [graph].[RepoObject_S]
AS
SELECT
 -- 
 [RepoObject_guid]
 , [RepoObject_fullname]
 , [RepoObject_type]
FROM [repo].[RepoObject]

```

</details>

[Back to top](#dhw_self)

### graph.RepoObjectColumn_ReferencingReferenced

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Referenced_fullname | NVARCHAR(261) | yes |  |
| Referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| Referenced_type | CHAR(2) | yes |  |
| ReferencedColumn_fullname | NVARCHAR(520) | yes |  |
| ReferencedColumn_type | NVARCHAR(128) | yes |  |
| Referenced_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_fullname | NVARCHAR(261) | yes |  |
| Referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_type | CHAR(2) | yes |  |
| ReferencingColumn_fullname | NVARCHAR(520) | yes |  |
| ReferencingColumn_type | NVARCHAR(128) | yes |  |
| Referencing_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [graph].[RepoObjectColumn_ReferencingReferenced]
AS
SELECT
 --
 Object2.[RepoObject_fullname] AS Referenced_fullname
 , Object2.[RepoObject_guid] AS Referenced_RepoObject_guid
 , Object2.[RepoObject_type] AS Referenced_type
 , Object2.[RepoObjectColumn_fullname] AS ReferencedColumn_fullname
 , Object2.[RepoObjectColumn_type] AS ReferencedColumn_type
 , Object2.[RepoObjectColumn_guid] AS Referenced_guid
 , Object1.[RepoObject_fullname] AS Referencing_fullname
 , Object1.[RepoObject_guid] AS Referencing_RepoObject_guid
 , Object1.[RepoObject_type] AS Referencing_type
 , Object1.[RepoObjectColumn_fullname] AS ReferencingColumn_fullname
 , Object1.[RepoObjectColumn_type] AS ReferencingColumn_type
 , Object1.[RepoObjectColumn_guid] AS Referencing_guid
FROM [graph].[RepoObjectColumn] AS Object1
 , [graph].[ReferencedObjectColumn] AS referenced
 , [graph].[RepoObjectColumn] AS Object2
WHERE MATCH(Object1 - (referenced) - > Object2)

```

</details>

[Back to top](#dhw_self)

### graph.RepoObjectColumn_S

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_fullname | NVARCHAR(520) | no |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| RepoObjectColumn_type | NVARCHAR(128) | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_type | CHAR(2) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [graph].[RepoObjectColumn_S]
AS
SELECT
 --
 [RepoObjectColumn_guid]
 , [RepoObjectColumn_fullname]
 , [RepoObjectColumn_name]
 , [Repo_user_type_fullname] AS [RepoObjectColumn_type]
 , [RepoObject_guid]
 , [RepoObject_fullname]
 , [RepoObject_type]
FROM [repo].[RepoObjectColumn_gross]

```

</details>

[Back to top](#dhw_self)

### repo.aaa_test_sql_table_column

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| sql_table_column_common | NVARCHAR(MAX) | no |  |
| sql_table_column_computed | NVARCHAR(MAX) | yes |  |
| sql_table_column_identity | VARCHAR(4) | no |  |
| Repo_is_computed | BIT | no |  |
| Repo_is_persisted | BIT | yes |  |
| Repo_is_identity | BIT | no |  |
| Repo_seed_value | SQL_VARIANT | yes |  |
| Repo_increment_value | SQL_VARIANT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW repo.aaa_test_sql_table_column
AS
--
SELECT [RepoObjectColumn_name]
 , [sql_table_column_common] = CONCAT (
  QUOTENAME([RepoObjectColumn_name])
  --
  , ' '
  , [Repo_user_type_fullname]
  --CONSTRAINT
  --DEFAULT
  , CASE 
   WHEN [Repo_default_name] <> ''
    AND ISNULL([Repo_default_is_system_named], 0) = 0
    THEN CONCAT (
      ' CONSTRAINT '
      , [Repo_default_name]
      )
   END
  --
  , CASE 
   WHEN [Repo_default_definition] <> ''
    THEN CONCAT (
      ' DEFAULT '
      , [Repo_default_definition]
      )
   END
  --temporal table columns
  , CASE [Repo_generated_always_type]
   WHEN 1
    THEN ' GENERATED ALWAYS AS ROW START'
   WHEN 2
    THEN ' GENERATED ALWAYS AS ROW END'
   END
  --identity
  , CASE [Repo_is_identity]
   WHEN 1
    THEN CONCAT (
      ' IDENTITY ('
      , ISNULL(CAST([Repo_seed_value] AS NVARCHAR(MAX)), '1')
      , ', '
      , ISNULL(CAST([Repo_increment_value] AS NVARCHAR(MAX)), '1')
      , ')'
      )
   END
  --[Repo_is_nullable]
  , CASE [Repo_is_nullable]
   WHEN 0
    THEN ' NOT'
   END
  , ' NULL '
  --
  )
 , [sql_table_column_computed] = CASE 
  WHEN [Repo_is_computed] = 1
   THEN CONCAT (
     QUOTENAME([RepoObjectColumn_name])
     , ' AS '
     , [Repo_definition]
     , CASE 
      WHEN [Repo_is_persisted] = 1
       THEN ' PERSISTED'
      END
     --[Repo_is_nullable]
     , CASE [Repo_is_nullable]
      WHEN 0
       THEN ' NOT'
      END
     , ' NULL '
     --
     )
  END
 , [sql_table_column_identity] = 'todo'
 , [Repo_is_computed]
 , [Repo_is_persisted]
 , [Repo_is_identity]
 , [Repo_seed_value]
 , [Repo_increment_value]
FROM [repo].[RepoObjectColumn] AS roc
 ----
 --ORDER BY
 --         [RepoObjectColumn_name]
```

</details>

[Back to top](#dhw_self)

### repo.check_IndexColumn_virtual_referenced_setpoint

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | no |  |
| index_column_id | INT | no |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_fullname_s | NVARCHAR(261) | yes |  |
| SysObject_fullname_t | NVARCHAR(261) | yes |  |
| SysObjectColumn_name_s | NVARCHAR(128) | yes |  |
| SysObjectColumn_name_t | NVARCHAR(128) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObject_guid_s | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObject_guid_t | UNIQUEIDENTIFIER | yes |  |
| RepoObjectColumn_guid_t | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[check_IndexColumn_virtual_referenced_setpoint]
AS
SELECT [T1].[index_guid]
 , [T1].[index_column_id]
 , [T1].[referencing_RepoObjectColumn_guid]
 , [T1].[referenced_index_guid]
 , [T1].[referenced_RepoObjectColumn_guid]
 , [ro_s].[SysObject_fullname] AS [SysObject_fullname_s]
 , [ro_t].[SysObject_fullname] AS [SysObject_fullname_t]
 , [roc_s].[SysObjectColumn_name] AS [SysObjectColumn_name_s]
 , [roc_t].[SysObjectColumn_name] AS [SysObjectColumn_name_t]
 , [T1].[referenced_RepoObject_guid]
 , [roc_s].[RepoObject_guid] AS [RepoObject_guid_s]
 , [T1].[referencing_RepoObject_guid]
 , [roc_t].[RepoObject_guid] AS [RepoObject_guid_t]
 , [roc_t].[RepoObjectColumn_guid] AS [RepoObjectColumn_guid_t]
--    , [roc_s].[RepoObjectColumn_guid] AS [RepoObjectColumn_guid_s]
--, [roc_s].[RepoObjectColumn_name] AS [RepoObjectColumn_name_s]
--, [roc_t].[RepoObjectColumn_name] AS [RepoObjectColumn_name_t]
FROM repo.IndexColumn_virtual_referenced_setpoint AS T1
LEFT OUTER JOIN repo.RepoObjectColumn AS roc_t
 ON T1.referencing_RepoObjectColumn_guid = roc_t.RepoObjectColumn_guid
LEFT OUTER JOIN repo.RepoObjectColumn AS roc_s
 ON T1.referenced_RepoObjectColumn_guid = roc_s.RepoObjectColumn_guid
LEFT OUTER JOIN repo.RepoObject AS ro_t
 ON T1.referencing_RepoObject_guid = ro_t.RepoObject_guid
LEFT OUTER JOIN repo.RepoObject AS ro_s
 ON T1.referenced_RepoObject_guid = ro_s.RepoObject_guid
  --WHERE  [T1].[index_guid] = '9731BB8B-CB50-EB11-84D5-A81E8446D5B0'
```

</details>

[Back to top](#dhw_self)

### repo.dbeaver_DataSources_connection

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | INT | no |  |
| BulkColumn | VARCHAR(MAX) | yes |  |
| is_json | INT | yes |  |
| connections | NVARCHAR(MAX) | yes |  |
| connection_key | NVARCHAR(4000) | no |  |
| connection_json | NVARCHAR(MAX) | yes |  |
| connection_provider | NVARCHAR(100) | yes |  |
| connection_driver | NVARCHAR(100) | yes |  |
| conection_name | NVARCHAR(100) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[dbeaver_DataSources_connections]
AS
SELECT
 --
 j1.*
 , j2.*
 , j3.[key] AS connection_key
 , j3.value AS connection_json
 , J4.*
FROM [repo].[dbeaver_DataSources] j1
CROSS APPLY OPENJSON(BulkColumn) WITH (connections NVARCHAR(MAX) N'$.connections' AS JSON) j2
CROSS APPLY OPENJSON(j2.connections) j3
CROSS APPLY OPENJSON(j3.value) WITH (
  connection_provider NVARCHAR(100) N'$.provider'
  , connection_driver NVARCHAR(100) N'$.driver'
  , conection_name NVARCHAR(100) N'$.name'
  ) j4

```

</details>

[Back to top](#dhw_self)

### repo.dbeaver_DataSources_DbSchemaTable

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | INT | no |  |
| BulkColumn | VARCHAR(MAX) | yes |  |
| is_json | INT | yes |  |
| VirtualModels | NVARCHAR(MAX) | yes |  |
| VirtualModel_key | NVARCHAR(4000) | no |  |
| VirtualModel_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_database | NVARCHAR(4000) | no |  |
| VirtualModel_database_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_schema | NVARCHAR(4000) | no |  |
| VirtualModel_schema_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table | NVARCHAR(500) | yes |  |
| VirtualModel_table_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table_constraints_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table_FK_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table_properties_json | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW repo.dbeaver_DataSources_DbSchemaTable
AS
SELECT
 --
 j1.*
 , j2.*
 , j3.[key] AS VirtualModel_key
 , j3.value AS VirtualModel_json
 , J4.[key] AS VirtualModel_database
 , j4.value AS VirtualModel_database_json
 , j5.[key] AS VirtualModel_schema
 , j5.value AS VirtualModel_schema_json
 , SUBSTRING(j6.[key], 2, 500) AS VirtualModel_table
 , j6.value AS VirtualModel_table_json
 , j7.*
FROM [repo].[dbeaver_DataSources] j1
CROSS APPLY OPENJSON(BulkColumn) WITH (VirtualModels NVARCHAR(MAX) N'$."virtual-models"' AS JSON) j2
CROSS APPLY OPENJSON(j2.VirtualModels) j3
CROSS APPLY OPENJSON(j3.value) j4
CROSS APPLY OPENJSON(j4.value) j5
CROSS APPLY OPENJSON(j5.value) j6
CROSS APPLY OPENJSON(j6.value) WITH (
  VirtualModel_table_constraints_json NVARCHAR(max) N'$.constraints' AS JSON
  , VirtualModel_table_FK_json NVARCHAR(max) N'$."foreign-keys"' AS JSON
  , VirtualModel_table_properties_json NVARCHAR(max) N'$.properties' AS JSON
  ) j7
WHERE [is_json] = 1

```

</details>

[Back to top](#dhw_self)

### repo.dbeaver_DataSources_DbSchemaTable_constraint

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | INT | no |  |
| BulkColumn | VARCHAR(MAX) | yes |  |
| is_json | INT | yes |  |
| VirtualModels | NVARCHAR(MAX) | yes |  |
| VirtualModel_key | NVARCHAR(4000) | no |  |
| VirtualModel_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_database | NVARCHAR(4000) | no |  |
| VirtualModel_database_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_schema | NVARCHAR(4000) | no |  |
| VirtualModel_schema_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table | NVARCHAR(500) | yes |  |
| VirtualModel_table_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table_constraints_json | NVARCHAR(MAX) | yes |  |
| key | NVARCHAR(4000) | no |  |
| value | NVARCHAR(MAX) | yes |  |
| type | TINYINT | no |  |
| VirtualModel_table_constraint_type | NVARCHAR(MAX) | yes |  |
| VirtualModel_table_constraint_attributes_json | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[dbeaver_DataSources_DbSchemaTable_constraint]
AS
SELECT
 --
 [id]
 , [BulkColumn]
 , [is_json]
 , [VirtualModels]
 , [VirtualModel_key]
 , [VirtualModel_json]
 , [VirtualModel_database]
 , [VirtualModel_database_json]
 , [VirtualModel_schema]
 , [VirtualModel_schema_json]
 , [VirtualModel_table]
 , [VirtualModel_table_json]
 , [VirtualModel_table_constraints_json]
 --,[VirtualModel_table_FK_json]
 --,[VirtualModel_table_properties_json]
 , j1.*
 , j2.*
FROM [repo].[dbeaver_DataSources_DbSchemaTable] t1
CROSS APPLY OPENJSON(t1.[VirtualModel_table_constraints_json]) j1
CROSS APPLY OPENJSON(j1.[value]) WITH (
  VirtualModel_table_constraint_type NVARCHAR(MAX) N'$.type'
  , VirtualModel_table_constraint_attributes_json NVARCHAR(MAX) N'$.attributes' AS JSON
  ) j2

```

</details>

[Back to top](#dhw_self)

### repo.dbeaver_DataSources_DbSchemaTable_FK

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | INT | no |  |
| BulkColumn | VARCHAR(MAX) | yes |  |
| is_json | INT | yes |  |
| VirtualModels | NVARCHAR(MAX) | yes |  |
| VirtualModel_key | NVARCHAR(4000) | no |  |
| VirtualModel_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_database | NVARCHAR(4000) | no |  |
| VirtualModel_database_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_schema | NVARCHAR(4000) | no |  |
| VirtualModel_schema_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table | NVARCHAR(500) | yes |  |
| VirtualModel_table_json | NVARCHAR(MAX) | yes |  |
| VirtualModel_table_FK_json | NVARCHAR(MAX) | yes |  |
| key | NVARCHAR(4000) | no |  |
| value | NVARCHAR(MAX) | yes |  |
| type | TINYINT | no |  |
| VirtualModel_table_FK_entity | NVARCHAR(500) | yes |  |
| VirtualModel_table_FK_constraint | NVARCHAR(500) | yes |  |
| VirtualModel_table_FK_attributes_json | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[dbeaver_DataSources_DbSchemaTable_FK]
AS
SELECT
 --
 [id]
 , [BulkColumn]
 , [is_json]
 , [VirtualModels]
 , [VirtualModel_key]
 , [VirtualModel_json]
 , [VirtualModel_database]
 , [VirtualModel_database_json]
 , [VirtualModel_schema]
 , [VirtualModel_schema_json]
 , [VirtualModel_table]
 , [VirtualModel_table_json]
 --, [VirtualModel_table_constraints_json]
 , [VirtualModel_table_FK_json]
 --,[VirtualModel_table_properties_json]
 , j1.*
 , j2.*
FROM [repo].[dbeaver_DataSources_DbSchemaTable] t1
CROSS APPLY OPENJSON(t1.[VirtualModel_table_FK_json]) j1
CROSS APPLY OPENJSON(j1.[value]) WITH (
  VirtualModel_table_FK_entity NVARCHAR(500) N'$.entity'
  , VirtualModel_table_FK_constraint NVARCHAR(500) N'$.constraint'
  , VirtualModel_table_FK_attributes_json NVARCHAR(MAX) N'$.attributes' AS JSON
  ) j2

```

</details>

[Back to top](#dhw_self)

### repo.ExecutionLog_gross

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | BIGINT | no |  |
| parent_execution_log_id | BIGINT | yes |  |
| execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| ssis_execution_id | BIGINT | yes |  |
| sub_execution_id | INT | yes |  |
| current_execution_guid | UNIQUEIDENTIFIER | yes |  |
| proc_id | INT | yes |  |
| proc_schema_name | NVARCHAR(128) | yes |  |
| proc_name | NVARCHAR(128) | yes |  |
| step_id | INT | yes |  |
| step_name | NVARCHAR(1000) | yes |  |
| created_dt | DATETIME | yes |  |
| source_object | NVARCHAR(261) | yes |  |
| target_object | NVARCHAR(261) | yes |  |
| inserted | INT | yes |  |
| updated | INT | yes |  |
| deleted | INT | yes |  |
| info_01 | SQL_VARIANT | yes |  |
| info_02 | SQL_VARIANT | yes |  |
| info_03 | SQL_VARIANT | yes |  |
| info_04 | SQL_VARIANT | yes |  |
| info_05 | SQL_VARIANT | yes |  |
| info_06 | SQL_VARIANT | yes |  |
| info_07 | SQL_VARIANT | yes |  |
| info_08 | SQL_VARIANT | yes |  |
| info_09 | SQL_VARIANT | yes |  |
| event_info | NVARCHAR(MAX) | yes |  |
| parameter_01 | SQL_VARIANT | yes |  |
| parameter_02 | SQL_VARIANT | yes |  |
| parameter_03 | SQL_VARIANT | yes |  |
| parameter_04 | SQL_VARIANT | yes |  |
| parameter_05 | SQL_VARIANT | yes |  |
| parameter_06 | SQL_VARIANT | yes |  |
| parameter_07 | SQL_VARIANT | yes |  |
| parameter_08 | SQL_VARIANT | yes |  |
| parameter_09 | SQL_VARIANT | yes |  |
| parameter_10 | SQL_VARIANT | yes |  |
| parameter_11 | SQL_VARIANT | yes |  |
| parameter_12 | SQL_VARIANT | yes |  |
| parameter_13 | SQL_VARIANT | yes |  |
| parameter_14 | SQL_VARIANT | yes |  |
| parameter_15 | SQL_VARIANT | yes |  |
| parameter_16 | SQL_VARIANT | yes |  |
| parameter_17 | SQL_VARIANT | yes |  |
| parameter_18 | SQL_VARIANT | yes |  |
| parameter_19 | SQL_VARIANT | yes |  |
| parameter_20 | SQL_VARIANT | yes |  |
| created_dt_min__execution_instance_guid | DATETIME | yes |  |
| created_dt_max__execution_instance_guid | DATETIME | yes |  |
| duration__current_execution_guid | INT | yes |  |
| duration__execution_instance_guid | INT | yes |  |
| plantUML_Sequence | NVARCHAR(1550) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


--, [plantUML_Sequence] = --
--  --combine the result with
--  --skinparam maxmessagesize 250
CREATE VIEW [repo].[ExecutionLog_gross]
AS
--
SELECT [id]
 , [parent_execution_log_id]
 , [execution_instance_guid]
 , [ssis_execution_id]
 , [sub_execution_id]
 , [current_execution_guid]
 , [proc_id]
 , [proc_schema_name]
 , [proc_name]
 , [step_id]
 , [step_name]
 , [created_dt]
 , [source_object]
 , [target_object]
 , [inserted]
 , [updated]
 , [deleted]
 , [info_01]
 , [info_02]
 , [info_03]
 , [info_04]
 , [info_05]
 , [info_06]
 , [info_07]
 , [info_08]
 , [info_09]
 , [event_info]
 , [parameter_01]
 , [parameter_02]
 , [parameter_03]
 , [parameter_04]
 , [parameter_05]
 , [parameter_06]
 , [parameter_07]
 , [parameter_08]
 , [parameter_09]
 , [parameter_10]
 , [parameter_11]
 , [parameter_12]
 , [parameter_13]
 , [parameter_14]
 , [parameter_15]
 , [parameter_16]
 , [parameter_17]
 , [parameter_18]
 , [parameter_19]
 , [parameter_20]
 --
 , [created_dt_min__execution_instance_guid] = MIN([created_dt]) OVER (PARTITION BY [execution_instance_guid])
 , [created_dt_max__execution_instance_guid] = MAX([created_dt]) OVER (PARTITION BY [execution_instance_guid])
 , [duration__current_execution_guid] = DATEDIFF([ss], MIN([created_dt]) OVER (PARTITION BY [current_execution_guid]), MAX([created_dt]) OVER (PARTITION BY [current_execution_guid]))
 , [duration__execution_instance_guid] = DATEDIFF([ss], MIN([created_dt]) OVER (PARTITION BY [execution_instance_guid]), MAX([created_dt]) OVER (PARTITION BY [execution_instance_guid]))
 --
 , [plantUML_Sequence] = --
 --combine the result with
 --skinparam maxmessagesize 250
 CASE 
  WHEN [source_object] IS NULL
   AND [target_object] IS NULL
   THEN CONCAT (
     CHAR(13)
     , CHAR(10)
     , '== '
     , [proc_fullname]
     , ' - '
     , [step_name]
     , ' =='
     , CHAR(13)
     , CHAR(10)
     , CHAR(13)
     , CHAR(10)
     )
  ELSE CONCAT (
    --
    CASE 
     WHEN NOT [source_object] IS NULL
      THEN QUOTENAME([source_object], '"')
     END
    , CASE 
     WHEN NOT [inserted] IS NULL
      THEN CASE 
        WHEN [source_object] IS NULL
         THEN '?-> '
        ELSE ' -> '
        END
     WHEN NOT [updated] IS NULL
      THEN CASE 
        WHEN [source_object] IS NULL
         THEN '?->o '
        ELSE ' ->O '
        END
     WHEN NOT [deleted] IS NULL
      THEN CASE 
        WHEN [source_object] IS NULL
         THEN '?->x '
        ELSE ' ->x '
        END
     ELSE CASE 
       WHEN [source_object] IS NULL
        THEN '?--> '
       ELSE ' --> '
       END
     END
    , CASE 
     WHEN NOT [target_object] IS NULL
      THEN QUOTENAME([target_object], '"')
     END
    --
    --, ' : ' , QUOTENAME([step_name] , '"')
    , ' : '
    , [step_name]
    , CHAR(13)
    , CHAR(10)
    -- "r" - rectangle note
    , 'rnote right:'
    , COALESCE([inserted], [updated], [deleted])
    --
    )
  END
FROM repo.ExecutionLog

```

</details>

[Back to top](#dhw_self)

### repo.ExecutionLog_parent

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | BIGINT | no |  |
| parent_execution_log_id | BIGINT | yes |  |
| parent_current_execution_guid | UNIQUEIDENTIFIER | yes |  |
| parent_proc_id | INT | yes |  |
| parent_proc_schema_name | NVARCHAR(128) | yes |  |
| parent_proc_name | NVARCHAR(128) | yes |  |
| parent_step_id | INT | yes |  |
| parent_step_name | NVARCHAR(1000) | yes |  |
| parent_created_dt | DATETIME | yes |  |
| parent_parameter_01 | SQL_VARIANT | yes |  |
| parent_parameter_02 | SQL_VARIANT | yes |  |
| parent_parameter_03 | SQL_VARIANT | yes |  |
| parent_parameter_04 | SQL_VARIANT | yes |  |
| parent_parameter_05 | SQL_VARIANT | yes |  |
| parent_parameter_06 | SQL_VARIANT | yes |  |
| parent_parameter_07 | SQL_VARIANT | yes |  |
| parent_parameter_08 | SQL_VARIANT | yes |  |
| parent_parameter_09 | SQL_VARIANT | yes |  |
| parent_parameter_10 | SQL_VARIANT | yes |  |
| parent_parameter_11 | SQL_VARIANT | yes |  |
| parent_parameter_12 | SQL_VARIANT | yes |  |
| parent_parameter_13 | SQL_VARIANT | yes |  |
| parent_parameter_14 | SQL_VARIANT | yes |  |
| parent_parameter_15 | SQL_VARIANT | yes |  |
| parent_parameter_16 | SQL_VARIANT | yes |  |
| parent_parameter_17 | SQL_VARIANT | yes |  |
| parent_parameter_18 | SQL_VARIANT | yes |  |
| parent_parameter_19 | SQL_VARIANT | yes |  |
| parent_parameter_20 | SQL_VARIANT | yes |  |
| parent_proc_fullname | NVARCHAR(517) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[ExecutionLog_parent]
AS
--
SELECT [T1].[id]
 , [T1].[parent_execution_log_id]
 , [parent].[current_execution_guid] AS [parent_current_execution_guid]
 , [parent].[proc_id] AS [parent_proc_id]
 , [parent].[proc_schema_name] AS [parent_proc_schema_name]
 , [parent].[proc_name] AS [parent_proc_name]
 , [parent].[step_id] AS [parent_step_id]
 , [parent].[step_name] AS [parent_step_name]
 , [parent].[created_dt] AS [parent_created_dt]
 , [parent].[parameter_01] AS [parent_parameter_01]
 , [parent].[parameter_02] AS [parent_parameter_02]
 , [parent].[parameter_03] AS [parent_parameter_03]
 , [parent].[parameter_04] AS [parent_parameter_04]
 , [parent].[parameter_05] AS [parent_parameter_05]
 , [parent].[parameter_06] AS [parent_parameter_06]
 , [parent].[parameter_07] AS [parent_parameter_07]
 , [parent].[parameter_08] AS [parent_parameter_08]
 , [parent].[parameter_09] AS [parent_parameter_09]
 , [parent].[parameter_10] AS [parent_parameter_10]
 , [parent].[parameter_11] AS [parent_parameter_11]
 , [parent].[parameter_12] AS [parent_parameter_12]
 , [parent].[parameter_13] AS [parent_parameter_13]
 , [parent].[parameter_14] AS [parent_parameter_14]
 , [parent].[parameter_15] AS [parent_parameter_15]
 , [parent].[parameter_16] AS [parent_parameter_16]
 , [parent].[parameter_17] AS [parent_parameter_17]
 , [parent].[parameter_18] AS [parent_parameter_18]
 , [parent].[parameter_19] AS [parent_parameter_19]
 , [parent].[parameter_20] AS [parent_parameter_20]
 , [parent].[proc_fullname] AS [parent_proc_fullname]
FROM repo.ExecutionLog AS T1
LEFT JOIN repo.ExecutionLog AS parent
 ON parent.id = T1.parent_execution_log_id
WHERE NOT [parent].[id] IS NULL
```

</details>

[Back to top](#dhw_self)

### repo.ExecutionLog_plantUML_Sequence_start_stop

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | BIGINT | no |  |
| plantUML_Sequence_start_stop | NVARCHAR(1574) | no |  |
| proc_fullname | NVARCHAR(517) | no |  |
| parent_proc_fullname | NVARCHAR(517) | yes |  |
| created_dt | DATETIME | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[ExecutionLog_plantUML_Sequence_start_stop]
AS
--
--, [plantUML_Sequence] = --
--  --combine the result with
--  --skinparam maxmessagesize 250
--  CASE
--      WHEN [source_object] IS NULL
--           AND [target_object] IS NULL
--      THEN CONCAT(CHAR(13) , CHAR(10) , '== ' , QUOTENAME([proc_schema_name]) , '.' , QUOTENAME([proc_name]) , ' - ' , [step_name] , ' ==' , CHAR(13) , CHAR(10) , CHAR(13) , CHAR(10))
--      ELSE CONCAT(
--      --
--      CASE
--          WHEN NOT [source_object] IS NULL
--          THEN QUOTENAME([source_object] , '"')
--      END ,
--      CASE
--          WHEN NOT [inserted] IS NULL
--          THEN CASE
--                   WHEN [source_object] IS NULL
--                   THEN '?-> '
--                   ELSE ' -> '
--               END
--          WHEN NOT [updated] IS NULL
--          THEN CASE
--                   WHEN [source_object] IS NULL
--                   THEN '?->o '
--                   ELSE ' ->O '
--               END
--          WHEN NOT [deleted] IS NULL
--          THEN CASE
--                   WHEN [source_object] IS NULL
--                   THEN '?->x '
--                   ELSE ' ->x '
--               END
--      END ,
--      CASE
--          WHEN NOT [target_object] IS NULL
--          THEN QUOTENAME([target_object] , '"')
--      END
--      --
--      --, ' : ' , QUOTENAME([step_name] , '"')
--      , ' : ' , [step_name] , CHAR(13) , CHAR(10)
--      -- "r" - rectangle note
--      , 'rnote right:' , COALESCE([inserted] , [updated] , [deleted])
--      --
--      )
--  END
--  --
--, [source_object]
--, [target_object]
--, [inserted]
--, [updated]
--, [deleted]
--, [ssis_execution_id]
--, [sub_execution_id]
--, [proc_id]
--, [step_id]
--, [created_dt]
--, [info_01]
--, [info_02]
--, [info_03]
--, [info_04]
--, [info_05]
--, [info_06]
--, [info_07]
--, [info_08]
--, [info_09]
--, [event_info]
--, [parameter_01]
--, [parameter_02]
--, [parameter_03]
--, [parameter_04]
--, [parameter_05]
--, [parameter_06]
--, [parameter_07]
--, [parameter_08]
--, [parameter_09]
--, [parameter_10]
--, [parameter_11]
--, [parameter_12]
--, [parameter_13]
--, [parameter_14]
--, [parameter_15]
--, [parameter_16]
--, [parameter_17]
--, [parameter_18]
--, [parameter_19]
--, [parameter_20]
SELECT [T1].[id]
 , [plantUML_Sequence_start_stop] = --
 --
 CONCAT (
  --
  CASE 
   WHEN [parent].[parent_proc_fullname] <> ''
    THEN CONCAT (
      '"'
      , [parent].[parent_proc_fullname]
      , '"'
      )
     --ELSE CONCAT('"' , [T1].[execution_instance_guid] , '"')
   END
  --
  , CASE [T1].[step_name]
   WHEN 'start'
    THEN ' -> '
   WHEN 'end'
    THEN ' <- '
   END
  --
  , '"'
  , [T1].[proc_fullname]
  , '"'
  --
  , CHAR(13)
  , CHAR(10)
  --
  , CASE [T1].[step_name]
   WHEN 'start'
    THEN 'activate '
   WHEN 'end'
    THEN 'deactivate '
   END
  --
  , '"'
  , [T1].[proc_fullname]
  , '"'
  )
 --
 --
 , [T1].[proc_fullname]
 , [parent].[parent_proc_fullname]
 , [T1].[created_dt]
FROM [repo].[ExecutionLog] AS T1
LEFT JOIN [repo].[ExecutionLog_parent] AS parent
 ON parent.id = T1.id
WHERE [T1].[step_name] IN (
  'start'
  , 'end'
  )
 --ORDER BY
 --         [T1].[id]

```

</details>

[Back to top](#dhw_self)

### repo.ExtendedProperty_Repo2Sys_level1

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| level0type | NVARCHAR(6) | no |  |
| level0name | NVARCHAR(128) | no |  |
| level1type | VARCHAR(9) | yes |  |
| level1name | NVARCHAR(128) | no |  |
| level2type | VARCHAR(10) | yes |  |
| level2name | VARCHAR(128) | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_type | CHAR(2) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[ExtendedProperty_Repo2Sys_level1]
AS
SELECT [prop].[property_name]
 , [prop].[property_value]
 , [level0type] = N'Schema'
 , [level0name] = [ro].[RepoObject_schema_name]
 , [lev].[level1type]
 , [level1name] = [ro].[RepoObject_name]
 , [lev].[level2type]
 , [level2name] = CAST(NULL AS VARCHAR(128))
 , [prop].[RepoObject_guid]
 , [ro].[RepoObject_type]
FROM repo.RepoObjectProperty AS prop
INNER JOIN repo.RepoObject AS ro
 ON ro.RepoObject_guid = prop.RepoObject_guid
INNER JOIN [repo].[type_level1type_level2type] AS lev
 ON lev.type = ro.RepoObject_type
WHERE NOT [lev].[level1type] IS NULL
 AND [lev].[level2type] IS NULL

```

</details>

[Back to top](#dhw_self)

### repo.ExtendedProperty_Repo2Sys_level2_RepoObject

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| level0type | NVARCHAR(6) | no |  |
| level0name | NVARCHAR(128) | no |  |
| level1type | VARCHAR(9) | yes |  |
| level1name | NVARCHAR(128) | no |  |
| level2type | VARCHAR(10) | yes |  |
| level2name | NVARCHAR(128) | no |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_type | CHAR(2) | no |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| parent_RepoObject_type | CHAR(2) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[ExtendedProperty_Repo2Sys_level2_RepoObject]
AS
SELECT [prop].[property_name]
 , [prop].[property_value]
 , [level0type] = N'Schema'
 , [level0name] = [ro_parent].[RepoObject_schema_name]
 , [lev_parent].[level1type]
 , [level1name] = [ro_parent].[RepoObject_name]
 , [lev].[level2type]
 , [level2name] = [ro].[RepoObject_name]
 , [prop].[RepoObject_guid]
 , [ro].[RepoObject_type]
 , [parent_RepoObject_guid] = [ro_parent].[RepoObject_guid]
 , [parent_RepoObject_type] = [ro_parent].[RepoObject_type]
FROM repo.RepoObjectProperty AS prop
INNER JOIN repo.RepoObject AS ro
 ON ro.RepoObject_guid = prop.RepoObject_guid
INNER JOIN [repo].[type_level1type_level2type] AS lev
 ON lev.type = ro.RepoObject_type
INNER JOIN repo.RepoObject AS ro_parent
 ON ro_parent.[SysObject_id] = ro.[SysObject_parent_object_id]
INNER JOIN [repo].[type_level1type_level2type] AS lev_parent
 ON lev_parent.type = ro_parent.RepoObject_type
WHERE NOT [lev].[level2type] IS NULL
 AND [ro_parent].[SysObject_id] > 0

```

</details>

[Back to top](#dhw_self)

### repo.ExtendedProperty_Repo2Sys_level2_RepoObjectColumn

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | no |  |
| level0type | NVARCHAR(6) | no |  |
| level0name | NVARCHAR(128) | no |  |
| level1type | VARCHAR(9) | yes |  |
| level1name | NVARCHAR(128) | no |  |
| level2type | NVARCHAR(6) | no |  |
| level2name | NVARCHAR(128) | no |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| Repo_user_type_fullname | NVARCHAR(128) | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| parent_RepoObject_type | CHAR(2) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW repo.ExtendedProperty_Repo2Sys_level2_RepoObjectColumn
AS
SELECT [prop].[property_name]
 , [prop].[property_value]
 , [level0type] = N'Schema'
 , [level0name] = [ro_parent].[RepoObject_schema_name]
 , [lev_parent].[level1type]
 , [level1name] = [ro_parent].[RepoObject_name]
 , [level2type] = N'COLUMN'
 , [level2name] = [roc].[RepoObjectColumn_name]
 , [prop].[RepoObjectColumn_guid]
 , [roc].[Repo_user_type_fullname]
 , [parent_RepoObject_guid] = [ro_parent].[RepoObject_guid]
 , [parent_RepoObject_type] = [ro_parent].[RepoObject_type]
FROM [repo].[RepoObjectColumnProperty] AS prop
INNER JOIN [repo].[RepoObjectColumn] AS roc
 ON roc.[RepoObjectColumn_guid] = prop.[RepoObjectColumn_guid]
INNER JOIN repo.RepoObject AS ro_parent
 ON ro_parent.[RepoObject_guid] = roc.[RepoObject_guid]
INNER JOIN [repo].[type_level1type_level2type] AS lev_parent
 ON lev_parent.type = ro_parent.RepoObject_type
WHERE [is_RepoObjectColumn_name_uniqueidentifier] = 0

```

</details>

[Back to top](#dhw_self)

### repo.ExtendedProperty_Repo2Sys_level2_Union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| level0type | NVARCHAR(6) | no |  |
| level0name | NVARCHAR(128) | no |  |
| level1type | VARCHAR(9) | yes |  |
| level1name | NVARCHAR(128) | no |  |
| level2type | NVARCHAR(10) | yes |  |
| level2name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW repo.ExtendedProperty_Repo2Sys_level2_Union
AS
SELECT
 --
 [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM [repo].[ExtendedProperty_Repo2Sys_level2_RepoObject]

UNION ALL

SELECT
 --
 [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM [repo].ExtendedProperty_Repo2Sys_level2_RepoObjectColumn

```

</details>

[Back to top](#dhw_self)

### repo.ForeignKey_Index_guid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| ForeignKey_guid | UNIQUEIDENTIFIER | yes |  |
| is_MatchingDatatypePattern | INT | no |  |
| ForeignKey_name | SYSNAME(128) | yes |  |
| ForeignKey_fullname | NVARCHAR(261) | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| referenced_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_SysObject_name | NVARCHAR(128) | yes |  |
| referenced_SysObject_schema_name | NVARCHAR(128) | yes |  |
| referencing_index_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| referencing_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_SysObject_name | NVARCHAR(128) | yes |  |
| referencing_SysObject_schema_name | NVARCHAR(128) | yes |  |
| delete_referential_action | TINYINT | yes |  |
| update_referential_action | TINYINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql



/*
can be used to find out missing [referenced_index_guid] or [referencing_index_guid]
to create them using [repo].[usp_Index_insert]
*/
CREATE VIEW [repo].[ForeignKey_Index_guid]
AS
SELECT
 --
 [fk].[ForeignKey_guid]
 , [is_MatchingDatatypePattern] = CASE 
  WHEN [i_1].[IndexPatternColumnDatatype] = [i_2].[IndexPatternColumnDatatype]
   THEN 1
  ELSE 0
  END
 , [fk].[ForeignKey_name]
 , [fk].[ForeignKey_fullname]
 , [referenced_index_guid] = [i_2].[index_guid]
 , [referenced_IndexPatternColumnDatatype] = [i_2].[IndexPatternColumnDatatype]
 , [fk].[referenced_IndexPatternColumnName]
 , [referenced_RepoObject_fullname] = [i_2].[RepoObject_fullname]
 , [fk].[referenced_RepoObject_guid]
 , [referenced_SysObject_name] = [i_2].[SysObject_name]
 , [referenced_SysObject_schema_name] = [i_2].[SysObject_schema_name]
 , [referencing_index_guid] = [i_1].[index_guid]
 , [referencing_IndexPatternColumnDatatype] = [i_1].[IndexPatternColumnDatatype]
 , [fk].[referencing_IndexPatternColumnName]
 , [referencing_RepoObject_fullname] = [i_1].[RepoObject_fullname]
 , [fk].[referencing_RepoObject_guid]
 , [referencing_SysObject_name] = [i_1].[SysObject_name]
 , [referencing_SysObject_schema_name] = [i_1].[SysObject_schema_name]
 , [fk].[delete_referential_action]
 , [fk].[update_referential_action]
FROM [repo].[ForeignKey_IndexPattern] AS fk
LEFT JOIN [repo].[Index_gross] AS i_1
 ON i_1.[parent_RepoObject_guid] = fk.[referencing_RepoObject_guid]
  AND i_1.[IndexPatternColumnName] = fk.[referencing_IndexPatternColumnName]
LEFT JOIN [repo].[Index_gross] AS i_2
 ON i_2.[parent_RepoObject_guid] = fk.[referenced_RepoObject_guid]
  AND i_2.[IndexPatternColumnName] = fk.[referenced_IndexPatternColumnName]

```

</details>

[Back to top](#dhw_self)

### repo.ForeignKey_Index_guid_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| ForeignKey_guid | UNIQUEIDENTIFIER | yes |  |
| is_MatchingDatatypePattern | INT | no |  |
| ForeignKey_name | NVARCHAR(128) | yes |  |
| ForeignKey_fullname | NVARCHAR(517) | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| referenced_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_SysObject_name | NVARCHAR(128) | yes |  |
| referenced_SysObject_schema_name | NVARCHAR(128) | yes |  |
| referencing_index_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| referencing_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_SysObject_name | NVARCHAR(128) | yes |  |
| referencing_SysObject_schema_name | NVARCHAR(128) | yes |  |
| delete_referential_action | TINYINT | yes |  |
| update_referential_action | TINYINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql



CREATE VIEW [repo].[ForeignKey_Index_guid_union]
AS
SELECT [ForeignKey_guid]
 , [is_MatchingDatatypePattern]
 , [ForeignKey_name]
 , [ForeignKey_fullname]
 , [referenced_index_guid]
 , [referenced_IndexPatternColumnDatatype]
 , [referenced_IndexPatternColumnName]
 , [referenced_RepoObject_fullname]
 , [referenced_RepoObject_guid]
 , [referenced_SysObject_name]
 , [referenced_SysObject_schema_name]
 , [referencing_index_guid]
 , [referencing_IndexPatternColumnDatatype]
 , [referencing_IndexPatternColumnName]
 , [referencing_RepoObject_fullname]
 , [referencing_RepoObject_guid]
 , [referencing_SysObject_name]
 , [referencing_SysObject_schema_name]
 , [delete_referential_action]
 , [update_referential_action]
FROM [repo].[ForeignKey_Index_guid]

UNION ALL

SELECT [ForeignKey_guid]
 , [is_MatchingDatatypePattern]
 , [ForeignKey_name]
 , [ForeignKey_fullname]
 , [referenced_index_guid]
 , [referenced_IndexPatternColumnDatatype]
 , [referenced_IndexPatternColumnName]
 , [referenced_RepoObject_fullname]
 , [referenced_RepoObject_guid]
 , [referenced_SysObject_name]
 , [referenced_SysObject_schema_name]
 , [referencing_index_guid]
 , [referencing_IndexPatternColumnDatatype]
 , [referencing_IndexPatternColumnName]
 , [referencing_RepoObject_fullname]
 , [referencing_RepoObject_guid]
 , [referencing_SysObject_name]
 , [referencing_SysObject_schema_name]
 , [delete_referential_action]
 , [update_referential_action]
FROM [repo].[ForeignKey_virtual_Index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.ForeignKey_IndexPattern

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| constraint_object_id | INT | no |  |
| ForeignKey_guid | UNIQUEIDENTIFIER | yes |  |
| ForeignKey_name | SYSNAME(128) | yes |  |
| ForeignKey_fullname | NVARCHAR(261) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referenced_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| delete_referential_action | TINYINT | yes |  |
| update_referential_action | TINYINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[ForeignKey_IndexPattern]
AS
SELECT
 --
 fk.object_id AS [constraint_object_id]
 , fk.[ForeignKey_guid]
 , MAX([ForeignKey_name]) AS [ForeignKey_name]
 , MAX(fk.[ForeignKey_fullname]) AS [ForeignKey_fullname]
 , MAX([referencing_RepoObject_guid]) AS [referencing_RepoObject_guid]
 , MAX([referenced_RepoObject_guid]) AS [referenced_RepoObject_guid]
 , referencing_IndexPatternColumnName = String_Agg(referencing_column_name, ',') WITHIN
GROUP (
  ORDER BY [constraint_column_id]
  )
 -- , referencing_IndexPatternColumnGuid = String_Agg(CAST(referencing_RepoObjectColumn_guid AS VARCHAR(36)), ',') WITHIN
 --GROUP (
 --  ORDER BY [constraint_column_id]
 --  )
 , referenced_IndexPatternColumnName = String_Agg(referenced_column_name, ',') WITHIN
GROUP (
  ORDER BY [constraint_column_id]
  )
 -- , referenced_IndexPatternColumnGuid = String_Agg(CAST(referenced_RepoObjectColumn_guid AS VARCHAR(36)), ',') WITHIN
 --GROUP (
 --  ORDER BY [constraint_column_id]
 --  )
 , MAX([delete_referential_action]) AS [delete_referential_action]
 , MAX([update_referential_action]) AS [update_referential_action]
FROM [repo_sys].[ForeignKey] fk
LEFT JOIN [repo_sys].[ForeignKeyColumn] fkc
 ON fkc.ForeignKey_guid = fk.ForeignKey_guid
GROUP BY fk.[object_id]
 , fk.[ForeignKey_guid]

```

</details>

[Back to top](#dhw_self)

### repo.ForeignKey_RelationScript

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| DbmlRelation | NVARCHAR(4000) | no |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[DbmlRelationFK]
AS
--
SELECT
 --
 [DbmlRelation] = CONCAT (
  'Ref '
  , [ForeignKey_name]
  , ': '
  , QUOTENAME([referencing_RepoObject_fullname], '"')
  , '.('
  , [referencing_IndexPatternColumnName]
  , ')'
  --<: one-to-many. E.g: users.id < posts.user_id
  -->: many-to-one. E.g: posts.user_id > users.id
  ---: one-to-one. E.g: users.id - user_infos.user_id
  , ' > '
  , QUOTENAME([referenced_RepoObject_fullname], '"')
  , '.('
  , [referenced_IndexPatternColumnName]
  , ')'
  , '[delete: '
  , CASE [delete_referential_action]
   WHEN 0
    THEN 'no action'
   WHEN 1
    THEN 'Cascade'
   WHEN 2
    THEN 'Set null'
   WHEN 3
    THEN 'Set default'
   END
  , ', update: '
  , CASE [update_referential_action]
   WHEN 0
    THEN 'no action'
   WHEN 1
    THEN 'Cascade'
   WHEN 2
    THEN 'Set null'
   WHEN 3
    THEN 'Set default'
   END
  , ']'
  )
, [referenced_RepoObject_fullname]
, [referenced_RepoObject_guid]
, [referencing_RepoObject_fullname]
, [referencing_RepoObject_guid]
--, [ForeignKey_guid]
--, [is_MatchingDatatypePattern]
--, [ForeignKey_name]
--, [ForeignKey_fullname]
--, [referenced_index_guid]
--, [referenced_IndexPatternColumnDatatype]
--, [referenced_IndexPatternColumnName]
--, [referencing_index_guid]
--, [referencing_IndexPatternColumnDatatype]
--, [referencing_IndexPatternColumnName]
--, [delete_referential_action]
--, [update_referential_action]
FROM [repo].[ForeignKey_Index_guid_union]
WHERE NOT [referenced_index_guid] IS NULL
 AND NOT [referencing_index_guid] IS NULL

```

</details>

[Back to top](#dhw_self)

### repo.ForeignKey_virtual_Index_guid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| ForeignKey_guid | UNIQUEIDENTIFIER | no |  |
| is_MatchingDatatypePattern | INT | no |  |
| ForeignKey_name | NVARCHAR(128) | yes |  |
| ForeignKey_fullname | NVARCHAR(517) | no |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| referenced_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_SysObject_name | NVARCHAR(128) | yes |  |
| referenced_SysObject_schema_name | NVARCHAR(128) | yes |  |
| referencing_index_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| referencing_IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_SysObject_name | NVARCHAR(128) | yes |  |
| referencing_SysObject_schema_name | NVARCHAR(128) | yes |  |
| delete_referential_action | TINYINT | no |  |
| update_referential_action | TINYINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql




CREATE VIEW [repo].[ForeignKey_virtual_Index_guid]
AS
SELECT
 --
 [fk].[ForeignKey_guid]
 , [is_MatchingDatatypePattern] = CASE 
  WHEN [i_1].[IndexPatternColumnDatatype] = [i_2].[IndexPatternColumnDatatype]
   THEN 1
  ELSE 0
  END
 , [fk].[ForeignKey_name]
 , [ForeignKey_fullname] = CONCAT (
  QUOTENAME([i_1].[SysObject_schema_name])
  , '.'
  , QUOTENAME([fk].[ForeignKey_name])
  )
 , [fk].[referenced_index_guid]
 , [referenced_IndexPatternColumnDatatype] = [i_2].[IndexPatternColumnDatatype]
 , [referenced_IndexPatternColumnName] = [i_2].[IndexPatternColumnName]
 , [referenced_RepoObject_fullname] = [i_2].[RepoObject_fullname]
 , [referenced_RepoObject_guid] = [i_2].[parent_RepoObject_guid]
 , [referenced_SysObject_name] = [i_2].[SysObject_name]
 , [referenced_SysObject_schema_name] = [i_2].[SysObject_schema_name]
 , [fk].[referencing_index_guid]
 , [referencing_IndexPatternColumnDatatype] = [i_1].[IndexPatternColumnDatatype]
 , [referencing_IndexPatternColumnName] = [i_1].[IndexPatternColumnName]
 , [referencing_RepoObject_fullname] = [i_1].[RepoObject_fullname]
 , [referencing_RepoObject_guid] = [i_1].[parent_RepoObject_guid]
 , [referencing_SysObject_name] = [i_1].[SysObject_name]
 , [referencing_SysObject_schema_name] = [i_1].[SysObject_schema_name]
 , [delete_referential_action]
 , [update_referential_action]
FROM [repo].[ForeignKey_virtual] AS fk
LEFT JOIN [repo].[Index_gross] AS i_1
 ON i_1.[index_guid] = fk.[referencing_index_guid]
LEFT JOIN [repo].[Index_gross] AS i_2
 ON i_2.[index_guid] = fk.[referenced_index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUsp_filter_persistence

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | INT | no |  |
| usp_schema | NVARCHAR(128) | no |  |
| usp_name | NVARCHAR(128) | no |  |
| has_logging | TINYINT | no |  |
| usp_Description | NVARCHAR(4000) | yes |  |
| usp_fullname | NVARCHAR(261) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE
 

 VIEW [repo].[GeneratorUsp_filter_persistence]
AS
SELECT [u].[id]
 , [u].[usp_schema]
 , [u].[usp_name]
 , [u].[has_logging]
 , [u].[usp_Description]
 , [u].[usp_fullname]
FROM [repo].[GeneratorUsp] AS [u]
WHERE LEFT([u].[usp_name], 12) = 'usp_PERSIST_'
```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUsp_ParameterList

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| usp_id | INT | no |  |
| ParameterList | NVARCHAR(MAX) | yes |  |
| ParameterListLogging | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
List of parameters without trailing comma
*/
CREATE VIEW [repo].[GeneratorUsp_ParameterList]
AS
SELECT [up].[usp_id]
 , ParameterList = STRING_AGG(CONCAT (
   CAST('@' AS NVARCHAR(max))
   , [up].[Name]
   , ' '
   , [up].[UserTypeFullname]
   , IIF([up].[has_DefaultValue] = 1, CONCAT (
     ' = '
     , ISNULL([up].[DefaultValue], 'NULL')
     ), NULL)
   , IIF([up].[is_out] = 1, ' OUTPUT', NULL)
   , CHAR(13)
   , CHAR(10)
   ), ',') WITHIN
GROUP (
  ORDER BY [up].[Number]
  )
 , ParameterListLogging = STRING_AGG(CONCAT (
   CAST(' , @parameter_' AS NVARCHAR(max))
   , right(CONCAT (
     '0'
     , RowNumber_PerUsp
     ), 2)
   , CAST(' = @' AS NVARCHAR(max))
   , [up].[Name]
   , CHAR(13)
   , CHAR(10)
   ), '') WITHIN
GROUP (
  ORDER BY [up].[Number]
  )
FROM (
 SELECT [par].[usp_id]
  , [par].[Number]
  , [par].[Name]
  , [par].[UserTypeFullname]
  , [par].[is_inactive]
  , [par].[is_out]
  , [par].[has_DefaultValue]
  , [par].[DefaultValue]
  , RowNumber_PerUsp = ROW_NUMBER() OVER (
   PARTITION BY [usp_id] ORDER BY [Number]
   )
 FROM [repo].[GeneratorUspParameter] AS par
 ) AS up
WHERE [up].[is_inactive] = 0
GROUP BY [up].[usp_id]
```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUsp_SqlUsp

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| usp_id | INT | no |  |
| SqlUsp | NVARCHAR(MAX) | no |  |
| usp_schema | NVARCHAR(128) | no |  |
| usp_name | NVARCHAR(128) | no |  |
| has_logging | TINYINT | no |  |
| usp_Description | NVARCHAR(4000) | yes |  |
| usp_fullname | NVARCHAR(261) | no |  |
| ParameterList | NVARCHAR(MAX) | yes |  |
| StepList | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql




/*
[SqlUsp] contains the final code for the usp, defined in
- [repo].[GeneratorUsp]
- [repo].[GeneratorUspParameter]
- [repo].[GeneratorUspStep]
*/
CREATE
 

 VIEW [repo].[GeneratorUsp_SqlUsp]
AS
SELECT [u].[id] AS [usp_id]
 , [SqlUsp] = CONCAT (
  --todo - maybe add description as comment
  'CREATE OR ALTER PROCEDURE '
  , [u].[usp_fullname]
  , CHAR(13)
  , CHAR(10)
  , [ParameterList].[ParameterList]
  , CASE [u].[has_logging]
   WHEN 1
    THEN CONCAT (
      IIF([ParameterList].[ParameterList] <> '', ',' + CHAR(13) + CHAR(10), '')
      , 
      '----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don''t need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step ''start''.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like ''[schema].[object]'', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like ''[schema].[object]'', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get''s only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = ''start''
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant
'
      , [ParameterList].[ParameterListLogging]
      , '
--
PRINT ''', u.[usp_fullname], '''
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
'
      )
   END --[u].[has_logging]
  , [StepList].[StepList]
  , CASE [u].[has_logging]
   WHEN 1
    THEN '
--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = ''end''
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object

GO
'
   END --[u].[has_logging]
  )
 , [u].[usp_schema]
 , [u].[usp_name]
 , [u].[has_logging]
 , [u].[usp_Description]
 , [u].[usp_fullname]
 , [ParameterList].[ParameterList]
 , [StepList].[StepList]
FROM [repo].[GeneratorUsp] AS u
LEFT JOIN [repo].[GeneratorUsp_ParameterList] AS ParameterList
 ON ParameterList.usp_id = u.id
LEFT JOIN [repo].[GeneratorUsp_StepList] AS StepList
 ON StepList.usp_id = u.id

```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUsp_StepList

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| usp_id | INT | no |  |
| StepList | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
SQL for the list of all steps
*/
CREATE
 

 VIEW [repo].[GeneratorUsp_StepList]
AS
SELECT [usp_id]
 , StepList = STRING_AGG(CONCAT (
   CAST('' AS NVARCHAR(max))
   , [SqlStep]
   , CHAR(13)
   , CHAR(10)
   ), '') WITHIN
GROUP (
  ORDER BY [RowNumber_PerUsp]
  )
FROM [repo].[GeneratorUspStep_Sql] AS us
GROUP BY [us].[usp_id]
```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUspStep_Persistence

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| usp_id | INT | no |  |
| Number | INT | no |  |
| Parent_Number | INT | yes |  |
| Name | VARCHAR(45) | no |  |
| has_logging | INT | no |  |
| is_condition | INT | no |  |
| is_inactive | INT | no |  |
| is_SubProcedure | INT | no |  |
| Statement | NVARCHAR(MAX) | yes |  |
| log_source_object | NVARCHAR(261) | yes |  |
| log_target_object | NVARCHAR(261) | yes |  |
| log_flag_InsertUpdateDelete | VARCHAR(1) | yes |  |
| usp_fullname | NVARCHAR(261) | no |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql




CREATE VIEW [repo].[GeneratorUspStep_Persistence]
AS
SELECT
 --
 [usp_id] = [gu].[id]
 , [Number] = 100
 , [Parent_Number] = NULL
 , [Name] = 'check for empty source'
 , [has_logging] = 0
 , [is_condition] = 1
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = '(SELECT count(*) FROM ' + [ro].[persistence_source_SysObject_fullname] + ') = 0'
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = CAST(NULL AS NVARCHAR(261))
 , [log_flag_InsertUpdateDelete] = CAST(NULL as char(1))
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name

UNION ALL

SELECT
 --
 [usp_id] = [gu].[id]
 , [Number] = 110
 , [Parent_Number] = 100
 , [Name] = 'ERROR 50110: persistence source is empty'
 , [has_logging] = 0
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = ' THROW 50110
  , ''persistence source is empty: ' + [ro].[persistence_source_SysObject_fullname] + '''
  , 1;
'
 , [log_source_object] = CAST(NULL AS NVARCHAR(261))
 , [log_target_object] = CAST(NULL AS NVARCHAR(261))
 , [log_flag_InsertUpdateDelete] = CAST(NULL as char(1))
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name

UNION ALL

SELECT
 --will be empty if PK doesn't exist
 [usp_id] = [gu].[id]
 , [Number] = 300
 , [Parent_Number] = NULL
 , [Name] = 'check duplicate per PK'
 , [has_logging] = 0
 , [is_condition] = 1
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'EXISTS(SELECT TOP 1 1 FROM ' + [ro].[persistence_source_SysObject_fullname] + ' GROUP BY ' + [i].[ColumnList] + ' HAVING COUNT(*) > 1)'
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = CAST(NULL AS NVARCHAR(261))
 , [log_flag_InsertUpdateDelete] = CAST(NULL as char(1))
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name
--INNER JOIN because step 300 should be created only when PK exists in persistence_source
INNER JOIN repo.RepoObject_gross AS ro_s
 ON ro_s.[RepoObject_guid] = ro.[persistence_source_RepoObject_guid]
INNER JOIN [repo].[Index_ColumList] AS i
 ON i.[index_guid] = ro_s.[pk_index_guid]

UNION ALL

SELECT
 --will be empty if PK doesn't exist
 [usp_id] = [gu].[id]
 , [Number] = 310
 , [Parent_Number] = 300
 , [Name] = 'ERROR 50310: persistence source PK not unique'
 , [has_logging] = 0
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = ' THROW 50310
  , ''persistence source PK not unique: ' + [ro].[persistence_source_SysObject_fullname] + '; ' + [i].[ColumnList] + '''
  , 1;
'
 , [log_source_object] = CAST(NULL AS NVARCHAR(261))
 , [log_target_object] = CAST(NULL AS NVARCHAR(261))
 , [log_flag_InsertUpdateDelete] = CAST(NULL as char(1))
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name
--INNER JOIN because step 300 should be created only when PK exists in persistence_source
INNER JOIN repo.RepoObject_gross AS ro_s
 ON ro_s.[RepoObject_guid] = ro.[persistence_source_RepoObject_guid]
INNER JOIN [repo].[Index_ColumList] AS i
 ON i.[index_guid] = ro_s.[pk_index_guid]

UNION ALL

SELECT
 --
 [usp_id] = [gu].[id]
 , [Number] = 400
 , [Parent_Number] = NULL
 , [Name] = 'truncate persistence target'
 , [has_logging] = 1
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'TRUNCATE TABLE ' + [ro].[RepoObject_fullname]
 , [log_source_object] = CAST(NULL AS NVARCHAR(261))
 , [log_target_object] = [ro].[RepoObject_fullname]
 , [log_flag_InsertUpdateDelete] = 'D'
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name

UNION ALL

SELECT
 --will be empty if PK doesn't exist
 [usp_id] = [gu].[id]
 , [Number] = 500
 , [Parent_Number] = NULL
 , [Name] = 'delete persistence target missing in source'
 , [has_logging] = 1
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'DELETE T
FROM ' + [ro].[RepoObject_fullname] + ' AS T
WHERE
NOT EXISTS
(SELECT 1 FROM ' + [ro].[persistence_source_SysObject_fullname] + ' AS S
WHERE
' + i.PersistenceWhereColumnList + ')
 '
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = [ro].[RepoObject_fullname]
 , [log_flag_InsertUpdateDelete] = 'D'
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name
--INNER JOIN because step 500 should be created only when PK exists in persistence_source
INNER JOIN repo.RepoObject_gross AS ro_s
 ON ro_s.[RepoObject_guid] = ro.[persistence_source_RepoObject_guid]
INNER JOIN [repo].[Index_ColumList] AS i
 ON i.[index_guid] = ro_s.[pk_index_guid]

UNION ALL

SELECT
 --will be empty if PK doesn't exist
 [usp_id] = [gu].[id]
 , [Number] = 550
 , [Parent_Number] = NULL
 , [Name] = 'delete persistence target changed'
 , [has_logging] = 1
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'DELETE T
FROM ' + [ro].[RepoObject_fullname] + ' AS T
INNER JOIN ' + [ro].[persistence_source_SysObject_fullname] + ' AS S
ON
' + i.PersistenceWhereColumnList + '
WHERE
' + ro.[PersistenceCompareColumnList]
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = [ro].[RepoObject_fullname]
 , [log_flag_InsertUpdateDelete] = 'D'
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name
--INNER JOIN because step 500 should be created only when PK exists in persistence_source
INNER JOIN repo.RepoObject_gross AS ro_s
 ON ro_s.[RepoObject_guid] = ro.[persistence_source_RepoObject_guid]
INNER JOIN [repo].[Index_ColumList] AS i
 ON i.[index_guid] = ro_s.[pk_index_guid]

UNION ALL

SELECT
 --will be empty if PK doesn't exist
 [usp_id] = [gu].[id]
 , [Number] = 600
 , [Parent_Number] = NULL
 , [Name] = 'update changed'
 , [has_logging] = 1
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'UPDATE T
SET
' + ro.[PersistenceUpdateColumnList] + '
FROM ' + [ro].[RepoObject_fullname] + ' AS T
INNER JOIN ' + [ro].[persistence_source_SysObject_fullname] + ' AS S
ON
' + i.PersistenceWhereColumnList + '
WHERE
' + ro.[PersistenceCompareColumnList]
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = [ro].[RepoObject_fullname]
 , [log_flag_InsertUpdateDelete] = 'U'
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name
--INNER JOIN because step 500 should be created only when PK exists in persistence_source
INNER JOIN repo.RepoObject_gross AS ro_s
 ON ro_s.[RepoObject_guid] = ro.[persistence_source_RepoObject_guid]
INNER JOIN [repo].[Index_ColumList] AS i
 ON i.[index_guid] = ro_s.[pk_index_guid]

UNION ALL

SELECT
 --will be empty if PK doesn't exist
 [usp_id] = [gu].[id]
 , [Number] = 700
 , [Parent_Number] = NULL
 , [Name] = 'insert missing'
 , [has_logging] = 1
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'INSERT INTO 
 ' + [ro].[RepoObject_fullname] + '
 (
' + ro.[PersistenceInsertColumnList] + ')
SELECT
' + ro.[PersistenceInsertColumnList] + '
FROM ' + [ro].[persistence_source_SysObject_fullname] + ' AS S
WHERE
NOT EXISTS
(SELECT 1
FROM ' + [ro].[RepoObject_fullname] + ' AS T
WHERE
' + i.PersistenceWhereColumnList + ')'
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = [ro].[RepoObject_fullname]
 , [log_flag_InsertUpdateDelete] = 'I'
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name
--INNER JOIN because step 500 should be created only when PK exists in persistence_source
INNER JOIN repo.RepoObject_gross AS ro_s
 ON ro_s.[RepoObject_guid] = ro.[persistence_source_RepoObject_guid]
INNER JOIN [repo].[Index_ColumList] AS i
 ON i.[index_guid] = ro_s.[pk_index_guid]

UNION ALL

SELECT
 --should be used in combination with truncate
 [usp_id] = [gu].[id]
 , [Number] = 800
 , [Parent_Number] = NULL
 , [Name] = 'insert all'
 , [has_logging] = 1
 , [is_condition] = 0
 , [is_inactive] = 0
 , [is_SubProcedure] = 0
 , [Statement] = 'INSERT INTO 
 ' + [ro].[RepoObject_fullname] + '
 (
' + ro.[PersistenceInsertColumnList] + ')
SELECT
' + ro.[PersistenceInsertColumnList] + '
FROM ' + [ro].[persistence_source_SysObject_fullname] + ' AS S'
 , [log_source_object] = [ro].[persistence_source_SysObject_fullname]
 , [log_target_object] = [ro].[RepoObject_fullname]
 , [log_flag_InsertUpdateDelete] = 'I'
 --
 , [gu].[usp_fullname]
 , [ro].[RepoObject_guid]
FROM repo.RepoObject_gross AS ro
INNER JOIN repo.GeneratorUsp AS gu
 ON ro.RepoObject_schema_name = gu.usp_schema
  AND ro.usp_persistence_name = gu.usp_name



```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUspStep_Persistence_IsInactive_setpoint

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| usp_id | INT | no |  |
| Number | INT | no |  |
| is_inactive | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE
 

 VIEW [repo].[GeneratorUspStep_Persistence_IsInactive_setpoint]
AS
WITH ro_u
AS (
 SELECT [u].[id] AS [usp_id]
  , [u].[usp_schema]
  , [u].[usp_name]
  , ro.[is_persistence_check_duplicate_per_pk]
  , [ro].[is_persistence_check_for_empty_source]
  , [ro].[is_persistence_delete_missing]
  , [ro].[is_persistence_delete_changed]
  , [ro].[is_persistence_insert]
  , [ro].[is_persistence_truncate]
  , [ro].[is_persistence_update_changed]
 FROM repo.RepoObject_gross AS ro
 INNER JOIN repo.GeneratorUsp AS u
  ON ro.RepoObject_schema_name = u.usp_schema
   AND ro.usp_persistence_name = u.usp_name
 )
SELECT
 --check for empty source
 [usp_id]
 , Number = 100
 , [is_inactive] = CASE [is_persistence_check_for_empty_source]
  WHEN 1
   THEN 0
  ELSE 1
  END
FROM ro_u

UNION ALL

SELECT
 --check duplicate per PK
 [usp_id]
 , Number = 300
 , [is_inactive] = CASE [is_persistence_check_duplicate_per_pk]
  WHEN 1
   THEN 0
  ELSE 1
  END
FROM ro_u

UNION ALL

SELECT
 --truncate persistence target
 [usp_id]
 , Number = 400
 , [is_inactive] = CASE [is_persistence_truncate]
  WHEN 1
   THEN 0
  ELSE 1
  END
FROM ro_u

UNION ALL

SELECT
 --delete persistence target missing in source
 --also do not delete if truncate, because there is nothing to delete after truncate
 [usp_id]
 , Number = 500
 , [is_inactive] = CASE 
  WHEN [is_persistence_truncate] = 1
   OR [is_persistence_delete_missing] = 0
   THEN 1
  ELSE 0
  END
FROM ro_u

UNION ALL

SELECT
 --delete persistence target changed
 --also do not delete if truncate, because there is nothing to delete after truncate
 [usp_id]
 , Number = 550
 , [is_inactive] = CASE 
  WHEN [is_persistence_truncate] = 1
   OR [is_persistence_delete_changed] = 0
   THEN 1
  ELSE 0
  END
FROM ro_u

UNION ALL

SELECT
 --update changed
 --also du not update after deleting changed or after truncate, because there is nothing to update
 [usp_id]
 , Number = 600
 , [is_inactive] = CASE 
  WHEN [is_persistence_truncate] = 1
   OR [is_persistence_delete_changed] = 1
   OR [is_persistence_update_changed] = 0
   THEN 1
  ELSE 0
  END
FROM ro_u

UNION ALL

SELECT
 --insert missing
 [usp_id]
 , Number = 700
 , [is_inactive] = CASE [is_persistence_insert]
  WHEN 1
   THEN 0
  ELSE 1
  END
FROM ro_u

UNION ALL

SELECT
 --insert all
 --only in combination with truncate
 --possible enhancement: maybe some delete all is required, if truncate is not possible?
 [usp_id]
 , Number = 800
 , [is_inactive] = CASE 
  WHEN [is_persistence_truncate] = 1
  AND [is_persistence_insert] = 1
   THEN 0
  ELSE 1
  END
FROM ro_u





```

</details>

[Back to top](#dhw_self)

### repo.GeneratorUspStep_Sql

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| usp_id | INT | no |  |
| Number | INT | yes |  |
| has_logging | TINYINT | no |  |
| required_Begin_count | INT | yes |  |
| required_End_count | INT | yes |  |
| is_required_ELSE | INT | yes |  |
| usp_fullname | NVARCHAR(261) | no |  |
| RowNumber_PerUsp | BIGINT | yes |  |
| SqlStep | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
--usage:

SELECT *
FROM [repo].[GeneratorUspStep_Sql]
ORDER BY [id]
 , [RowNumber_PerUsp]


*/
CREATE VIEW [repo].[GeneratorUspStep_Sql]
AS
SELECT [u].[id] AS usp_id
 , [t].[Number]
 , [u].[has_logging]
 , [BeginEnd].[required_Begin_count]
 , [BeginEnd].[required_End_count]
 , [BeginEnd].[is_required_ELSE]
 --only information
 , [u].[usp_fullname]
 , [t].[RowNumber_PerUsp]
 --, [t].[Depth]
 --, [t].[is_condition]
 --, [t].[Root_Sort]
 --, [t].[Parent_Number]
 --, [t].[Parent_Sort]
 --, [t].[Sort]
 --, [t].[child_PerParent]
 --, [t].[Asc_PerParentChild]
 --, [t].[Desc_PerParentChild]
 , sql.SqlStep
FROM [repo].[GeneratorUsp] AS u
CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([id], NULL) AS t
LEFT JOIN (
 SELECT [s].[usp_id]
  , [t].[Number]
  , [required_Begin_count] = SUM(IIF([t].[Asc_PerParentChild] = 1, 1, 0))
  , [required_End_count] = SUM(IIF([t].[Desc_PerParentChild] = 1, 1, 0))
  , [is_required_ELSE] = MAX([t].[is_required_ELSE])
 FROM [repo].[GeneratorUspStep] AS s
 CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([usp_id], [Number]) AS t
 WHERE [s].[is_condition] = 1
 GROUP BY [s].[usp_id]
  , [t].[Number]
 ) AS BeginEnd
 ON BeginEnd.usp_id = u.id
  AND BeginEnd.Number = t.Number
CROSS APPLY [repo].[ftv_GeneratorUspStep_sql]([u].[id], [t].[Number], [u].[has_logging], [BeginEnd].[required_Begin_count], [BeginEnd].[required_End_count], [BeginEnd].[is_required_ELSE]) sql
```

</details>

[Back to top](#dhw_self)

### repo.Index_ColumList

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| ColumnList | NVARCHAR(MAX) | yes |  |
| ConstraintColumnList | NVARCHAR(MAX) | yes |  |
| DbmlIndexColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceWhereColumnList | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql



CREATE VIEW [repo].[Index_ColumList]
AS
SELECT col.[index_guid]
 --ColumnList doesn't contain Asc and Desc
 , ColumnList = STRING_AGG(CONCAT (
   --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
   CAST(' ' AS NVARCHAR(MAX))
   , QUOTENAME(col.[SysObject_column_name])
   ), ',') WITHIN
GROUP (
  ORDER BY col.[index_column_id]
  )
 --ConstraintColumnList contains Asc and Desc
 , ConstraintColumnList = STRING_AGG(CONCAT (
   --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
   CAST(' ' AS NVARCHAR(MAX))
   , QUOTENAME(col.[SysObject_column_name])
   , CASE col.[is_descending_key]
    WHEN 1
     THEN ' DESC'
    ELSE ' ASC'
    END
   ), ',') WITHIN
GROUP (
  ORDER BY col.[index_column_id]
  )
 , DbmlIndexColumnList = STRING_AGG(CONCAT (
   --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
   CAST(' ' AS NVARCHAR(MAX))
   , QUOTENAME(col.[SysObject_column_name], '"')
   ), ',') WITHIN
GROUP (
  ORDER BY col.[index_column_id]
  )
 , PersistenceWhereColumnList = STUFF(STRING_AGG(CONCAT (
    --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
    CAST('AND T.' AS NVARCHAR(MAX))
    , QUOTENAME(col.[SysObject_column_name])
    , ' = S.'
    , QUOTENAME(col.[SysObject_column_name])
    , CHAR(13)
    , CHAR(10)
    ), '') WITHIN GROUP (
   ORDER BY col.[index_column_id]
   ), 1, 4, NULL)
FROM [repo].[IndexColumn_union] AS col
GROUP BY col.[index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.Index_gross

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | no |  |
| index_name | NVARCHAR(128) | yes |  |
| index_type | TINYINT | no |  |
| IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| IndexSemanticGroup | NVARCHAR(512) | yes |  |
| is_index_disabled | BIT | yes |  |
| is_index_primary_key | BIT | yes |  |
| is_index_real | BIT | yes |  |
| is_index_unique | BIT | yes |  |
| is_persistence | BIT | yes |  |
| is_repo_managed | BIT | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RowNumber_PatternPerParentObject | BIGINT | yes |  |
| RowNumber_PkPerParentObject | BIGINT | yes |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| SysObject_schema_name | NVARCHAR(128) | no |  |
| SysObject_name | NVARCHAR(128) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| SysObject_id | INT | yes |  |
| ColumnList | NVARCHAR(MAX) | yes |  |
| ConstraintColumnList | NVARCHAR(MAX) | yes |  |
| DbmlIndexColumnList | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[Index_gross]
AS
--
SELECT [T1].[index_guid]
 , [T2].[index_name]
 , [T2].[index_type]
 , [T1].[IndexPatternColumnDatatype]
 , [T1].[IndexPatternColumnName]
 , [T1].[IndexSemanticGroup]
 , [T2].[is_index_disabled]
 , [T2].[is_index_primary_key]
 , [T2].[is_index_real]
 , [T2].[is_index_unique]
 , [T3].[is_persistence]
 , [T3].[is_repo_managed]
 , [T2].[parent_RepoObject_guid]
 , [T2].[referenced_index_guid]
 , [T3].[RepoObject_fullname]
 --if [RowNumber_PatternPerParentObject] > 1 then these are duplicates by same ColumnPattern and normally should be deleted, at least in [repo].[Index_virtual] 
 , [RowNumber_PatternPerParentObject] = ROW_NUMBER() OVER (
  PARTITION BY [T2].[parent_RepoObject_guid]
  , [T1].[IndexPatternColumnName] ORDER BY
   --priority has real index
   [T2].[is_index_real] DESC
   --priority PK
   , [T2].[is_index_primary_key] DESC
   --priority not disabled
   , [t2].[is_index_disabled]
   --priority first added index
   , [T2].[index_guid]
  )
 , [RowNumber_PkPerParentObject] = ROW_NUMBER() OVER (
  PARTITION BY [T2].[parent_RepoObject_guid]
  , [T2].[is_index_primary_key] ORDER BY
   --priority has real index
   [T2].[is_index_real] DESC
   --priority not disabled
   , [t2].[is_index_disabled]
   --priority first added index
   , [T2].[index_guid]
  )
 , [T3].[SysObject_fullname]
 , [T3].[SysObject_schema_name]
 , [T3].[SysObject_name]
 , [T3].[SysObject_type]
 , [T3].[SysObject_id]
 , [ColumList].[ColumnList]
 , [ColumList].[ConstraintColumnList]
 , [ColumList].[DbmlIndexColumnList]
FROM repo.[Index_Settings] AS T1
INNER JOIN repo.Index_union AS T2
 ON T1.index_guid = T2.index_guid
INNER JOIN repo.RepoObject_gross AS T3
 ON T2.parent_RepoObject_guid = T3.RepoObject_guid
LEFT JOIN [repo].[Index_ColumList] AS ColumList
 ON ColumList.[index_guid] = T1.[index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.Index_IndexPattern

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[Index_IndexPattern]
AS
--
SELECT [index_guid]
 , IndexPatternColumnName = String_Agg(SysObject_column_name, ',') WITHIN
GROUP (
  ORDER BY [index_column_id]
  )
 , IndexPatternColumnDatatype = String_Agg([SysObject_column_user_type_fullname], ',') WITHIN
GROUP (
  ORDER BY [index_column_id]
  )
FROM [repo].[IndexColumn_union]
WHERE NOT [index_guid] IS NULL
GROUP BY [index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.Index_referencing_IndexPatternColumnGuid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| source_index_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_IndexPatternColumnGuid | VARCHAR(8000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
if a source_index "HasFullColumnsInReferencing"
we need to know [referencing_IndexPatternColumnGuid]
to filter out different source_index referencing in same referencing column combination

Because that would only lead to multiple indexes with the same column combination in the same RepoObject
*/

CREATE   view [repo].[Index_referencing_IndexPatternColumnGuid]
as
SELECT [source_index_guid] = [ic].[index_guid]
 , [ic].[referencing_RepoObject_guid]
 , [referencing_IndexPatternColumnGuid] = STRING_AGG(CAST([ic].[referencing_RepoObjectColumn_guid] AS CHAR(36)), ',') WITHIN
GROUP (
  ORDER BY CAST([ic].[referencing_RepoObjectColumn_guid] AS CHAR(36))
  )
FROM [repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T] AS ic
GROUP BY [ic].[index_guid]
 , [ic].[referencing_RepoObject_guid]

```

</details>

[Back to top](#dhw_self)

### repo.Index_SqlConstraint_PkUq

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| SqlConstraint | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

--contains only PK or UNIQUE
--requirement:
-- - repo.Index_Settings.is_create_constraint = 1
-- - repo.Index_union.is_index_unique = 1
CREATE VIEW [repo].[Index_SqlConstraint_PkUq]
AS
SELECT [i].[index_guid]
 , [i].[parent_RepoObject_guid]
 , [SqlConstraint] = CONCAT (
  'CONSTRAINT '
  --todo missing name?
  , QUOTENAME([i].[index_name])
  , ' '
  , CASE 
   WHEN [i].[is_index_primary_key] = 1
    THEN 'PRIMARY KEY '
   WHEN [i].[is_index_unique] = 1
    THEN 'UNIQUE '
   END
  , CASE [i].[index_type]
   WHEN 1
    THEN 'CLUSTERED '
   WHEN 2
    THEN 'NONCLUSTERED '
   END
  , '('
  , [ColumnList].[ConstraintColumnList]
  , ')'
  )
-- , i.index_name
-- , i.index_type
-- , i.is_index_unique
-- , i.is_index_primary_key
-- --, i.referenced_index_guid
-- , i.is_index_disabled
----, i.is_index_real
----, i_s.is_create_constraint
FROM repo.Index_union AS i
LEFT OUTER JOIN repo.Index_Settings AS i_s
 ON i_s.index_guid = i.index_guid
LEFT OUTER JOIN repo.Index_ColumList AS ColumnList
 ON ColumnList.[index_guid] = i.[index_guid]
WHERE [i_s].[is_create_constraint] = 1
 AND [i].[is_index_unique] = 1
```

</details>

[Back to top](#dhw_self)

### repo.Index_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| index_name | NVARCHAR(128) | yes |  |
| index_type | TINYINT | no |  |
| is_index_unique | BIT | yes |  |
| is_index_primary_key | BIT | yes |  |
| is_index_disabled | BIT | yes |  |
| IndexPatternColumnGuid | VARCHAR(8000) | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| is_index_real | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[Index_union]
AS
--
SELECT T1.[index_guid]
 , T1.[parent_RepoObject_guid]
 , T1.[index_name]
 , T1.[index_type]
 , T1.[is_index_unique]
 , T1.[is_index_primary_key]
 , T1.[is_index_disabled]
 , T2.[IndexPatternColumnGuid]
 , [referenced_index_guid] = NULL
 , [is_index_real] = CAST(1 AS BIT)
FROM repo_sys.[Index_unique] T1
LEFT JOIN [repo].Index_unique_IndexPatternColumnGuid T2
 ON T2.[index_guid] = T1.[index_guid]

UNION ALL

SELECT T1.[index_guid]
 , T1.[parent_RepoObject_guid]
 , T1.[index_name]
 , T1.[index_type]
 , T1.[is_index_unique]
 , T1.[is_index_primary_key]
 , T1.[is_index_disabled]
 , T2.[IndexPatternColumnGuid]
 , T1.[referenced_index_guid]
 , [is_index_real] = CAST(0 AS BIT)
FROM repo.[Index_virtual] T1
LEFT JOIN [repo].[Index_virtual_IndexPatternColumnGuid] T2
 ON T2.[index_guid] = T1.[index_guid]
```

</details>

[Back to top](#dhw_self)

### repo.Index_unique_IndexPatternColumnGuid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| IndexPatternColumnGuid | VARCHAR(8000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[Index_unique_IndexPatternColumnGuid]
AS
SELECT [index_guid]
 , [IndexPatternColumnGuid] = STRING_AGG(CAST([ic].[RepoObjectColumn_guid] AS CHAR(36)), ',') WITHIN
GROUP (
  ORDER BY CAST([ic].[RepoObjectColumn_guid] AS CHAR(36))
  )
FROM [repo_sys].[IndexColumn_unique] ic
GROUP BY [ic].[index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.Index_virtual_IndexPatternColumnGuid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | no |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| IndexPatternColumnGuid | VARCHAR(8000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[Index_virtual_IndexPatternColumnGuid]
AS
SELECT i.[index_guid]
 --only one [parent_RepoObject_guid] per index_guid is possible
 , [parent_RepoObject_guid] = MAX(i.[parent_RepoObject_guid])
 , [IndexPatternColumnGuid] = STRING_AGG(CAST([ic].[RepoObjectColumn_guid] AS CHAR(36)), ',') WITHIN
GROUP (
  ORDER BY CAST([ic].[RepoObjectColumn_guid] AS CHAR(36))
  )
FROM [repo].[Index_virtual] i
INNER JOIN [repo].[IndexColumn_virtual] ic
 ON i.[index_guid] = ic.[index_guid]
GROUP BY [i].[index_guid]

```

</details>

[Back to top](#dhw_self)

### repo.Index_virtual_SysObject

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | no |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| index_name | NVARCHAR(128) | yes |  |
| is_index_disabled | BIT | no |  |
| is_index_unique | BIT | no |  |
| is_index_primary_key | BIT | no |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| IndexPatternColumnDatatype | NVARCHAR(4000) | yes |  |
| IndexPatternColumnName | NVARCHAR(4000) | yes |  |
| IndexSemanticGroup | NVARCHAR(512) | yes |  |
| SysObject_id | INT | yes |  |
| SysObject_schema_name | NVARCHAR(128) | no |  |
| SysObject_name | NVARCHAR(128) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| pk_index_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[Index_virtual_SysObject]
AS
--
SELECT [iv].[index_guid]
 , [iv].[parent_RepoObject_guid]
 , [iv].[index_name]
 , [iv].[is_index_disabled]
 , [iv].[is_index_unique]
 , [iv].[is_index_primary_key]
 , [iv].[referenced_index_guid]
 , [isg].[IndexPatternColumnDatatype]
 , [isg].[IndexPatternColumnName]
 , [isg].[IndexSemanticGroup]
 , [ro].[SysObject_id]
 , [ro].[SysObject_schema_name]
 , [ro].[SysObject_name]
 , [ro].[SysObject_type]
 , [ro].[pk_index_guid]
FROM repo.[Index_virtual] AS iv
INNER JOIN repo.RepoObject AS ro
 ON iv.parent_RepoObject_guid = ro.RepoObject_guid
INNER JOIN [repo].[Index_Settings] AS isg
 ON isg.[index_guid] = [iv].[index_guid]
```

</details>

[Back to top](#dhw_self)

### repo.IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| index_column_id | INT | no |  |
| is_descending_key | BIT | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| RowNumberInReferencing | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
we use all Index from repo.IndexColumn__union (real and virtual)
and we use Object references
- currently from [repo].[RepoObjectColumn_reference_union] AS ref  
  but mabe this should be changed

so we get all possible index inheritence into any referencing object

first condition: any column of the referenced index should be a referencing column in the referencing object

second condition: all columns of the referenced index should be a referencing column in the referencing object
this means: "HasFullColumnsInReferencing"


Attention:
a source object can be joined several times
=> a source index can have several target index in the same target object
=> we implement [RowNumberInReferencing]

SELECT
       [index_guid]
     , [index_column_id]
     , [RepoObjectColumn_guid]
     , [referenced_RepoObject_guid]
     , [referenced_RepoObjectColumn_guid]
     , [referencing_RepoObject_guid]
     , COUNT(*) AS [Anz]
FROM
     repo.IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing AS T1
GROUP BY
         [index_guid]
       , [index_column_id]
       , [RepoObjectColumn_guid]
       , [referenced_RepoObject_guid]
       , [referenced_RepoObjectColumn_guid]
       , [referencing_RepoObject_guid]
ORDER BY
         [Anz] DESC


*/
CREATE VIEW [repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing]
AS
--
--referencing columns, that inherit an index
--the goal of this view is to include only RepoObjects, which inherit ALL referenced columns of a source index
SELECT
 --[index_guid] is referenced index, [index_column_id] is the column of a referenced index
 [ic].[index_guid]
 , [ic].[index_column_id]
 , [ic].[is_descending_key]
 --, [ic].[RepoObjectColumn_guid] --referenced RepoObjectColumn; redundant; remove it, if not used
 , [ref].[referenced_RepoObject_guid]
 , [ref].[referenced_RepoObjectColumn_guid] --also referenced RepoObjectColumn (as above), left join; but is it possible that it is NULL? No, because of the first EXISTS condition
 , [ref].[referencing_RepoObject_guid]
 , [ref].[referencing_RepoObjectColumn_guid]
 --the same index can be inherited several times into the same referenced object, if a source is used several times
 --for example
 --SELECT A_A = A.A, B_A = B.A from source_1 as A LEFT JOIN source_1 as B ON ... 
 --normaly these indexes should have different columns
 , [RowNumberInReferencing] = ROW_NUMBER() OVER (
  PARTITION BY
  --soure index column
  [ic].[index_guid]
  , [ic].[index_column_id]
  , [ref].[referenced_RepoObject_guid]
  , [ref].[referenced_RepoObjectColumn_guid]
  --taget index, if the same source index column is inherited several times into a target object
  , [ref].[referencing_RepoObject_guid] ORDER BY [ref].[referenced_RepoObjectColumn_guid]
  )
--, roc.[RepoObjectColumn_guid]
FROM repo.IndexColumn_union AS ic
INNER JOIN --todo: maybe use another source for RepoObject references 
 --repo.[RepoObjectColumn_reference_FirstResultSet] AS ref
 [repo].[RepoObjectColumn_reference_union] ref
 ON ref.referenced_RepoObjectColumn_guid = ic.RepoObjectColumn_guid
WHERE
 --first condition: any column of the referenced index should be a referencing column in the referencing objekt
 EXISTS (
  SELECT [roc].[RepoObject_guid]
  FROM [repo].[RepoObjectColumn] AS [roc]
  WHERE
   --[RepoObject_guid] is matching
   --=> some source columns (referenced) are referenced in the target (referencing)
   --but it is possible, that not all source columns are referenced
   --to exclude these RepoObject with incomlete inheritance, the next condition will remove these RepoObject
   [roc].[RepoObject_guid] = [ref].[referencing_RepoObject_guid]
  )
 AND NOT EXISTS
 --second condition: all columns of the referenced index should be a referencing column in the referencing object
 --this means: "HasFullColumnsInReferencing"
 (
  SELECT [roc].[RepoObject_guid]
  FROM [repo].[RepoObjectColumn] AS [roc]
  WHERE
   --[RepoObject_guid] is matching
   [roc].[RepoObject_guid] = [ref].[referencing_RepoObject_guid]
   --but some referencing columns are missing in referencing object
   --this is possible in case of a composed key where not all columns of the source are referenced in the target
   AND [ref].[referencing_RepoObjectColumn_guid] IS NULL
  )

```

</details>

[Back to top](#dhw_self)

### repo.IndexColumn_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| index_column_id | INT | no |  |
| is_descending_key | BIT | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| index_name | NVARCHAR(128) | yes |  |
| parent_schema_name | NVARCHAR(128) | yes |  |
| parent_SysObject_name | NVARCHAR(128) | yes |  |
| SysObject_column_name | NVARCHAR(128) | yes |  |
| SysObject_column_user_type_fullname | NVARCHAR(182) | yes |  |
| is_index_unique | BIT | yes |  |
| is_index_primary_key | BIT | yes |  |
| is_index_real | BIT | yes |  |
| parent_SysObject_fullname | NVARCHAR(261) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[IndexColumn_union]
AS
--
SELECT [index_guid]
 , [index_column_id]
 , [is_descending_key]
 , [RepoObjectColumn_guid]
 , [parent_RepoObject_guid]
 , [index_name]
 , [parent_schema_name]
 , [parent_SysObject_name]
 , [SysObject_column_name]
 , [SysObject_column_user_type_fullname]
 , [is_index_unique]
 , [is_index_primary_key]
 , [is_index_real]
 , [parent_SysObject_fullname]
FROM repo_sys.[IndexColumn_unique] AS T1

UNION ALL

SELECT [index_guid]
 , [index_column_id]
 , [is_descending_key]
 , [RepoObjectColumn_guid]
 , [parent_RepoObject_guid]
 , [index_name]
 , [parent_schema_name]
 , [parent_Object_name]
 , [Object_column_name]
 , [column_user_type_fullname]
 , [is_index_unique]
 , [is_index_primary_key]
 , [is_index_real]
 , [parent_Object_fullname]
FROM repo.IndexColumn_virtual_gross AS T2
```

</details>

[Back to top](#dhw_self)

### repo.IndexColumn_virtual_gross

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | no |  |
| index_column_id | INT | no |  |
| is_descending_key | BIT | no |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| index_name | NVARCHAR(128) | yes |  |
| parent_schema_name | NVARCHAR(128) | yes |  |
| parent_Object_name | NVARCHAR(128) | yes |  |
| Object_column_name | NVARCHAR(128) | no |  |
| column_user_type_fullname | NVARCHAR(128) | yes |  |
| is_index_unique | BIT | no |  |
| is_index_primary_key | BIT | no |  |
| parent_Object_fullname | NVARCHAR(261) | yes |  |
| is_index_real | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[IndexColumn_virtual_gross]
AS
--
SELECT [icv].[index_guid]
 , [icv].[index_column_id]
 , [icv].[is_descending_key]
 , icv.[RepoObjectColumn_guid]
 , [iv].[parent_RepoObject_guid]
 , [iv].[index_name]
 , [parent_schema_name] = COALESCE(ro.SysObject_schema_name, ro.[RepoObject_schema_name])
 , [parent_Object_name] = iif(NOT ro.[SysObject_name] IS NULL
  AND ro.[is_SysObject_name_uniqueidentifier] = 0, ro.[SysObject_name], ro.[RepoObject_name])
 , [Object_column_name] = iif(NOT roc.[SysObjectColumn_name] IS NULL
  AND roc.[is_SysObjectColumn_name_uniqueidentifier] = 0, roc.[SysObjectColumn_name], roc.[RepoObjectColumn_name])
 , [column_user_type_fullname] = roc.[Repo_user_type_fullname]
 , [iv].[is_index_unique]
 , [iv].[is_index_primary_key]
 , [parent_Object_fullname] = iif(NOT ro.[SysObject_fullname] IS NULL
  AND ro.[is_SysObject_name_uniqueidentifier] = 0, ro.[SysObject_fullname], ro.[RepoObject_fullname])
 , [is_index_real] = CAST(0 AS BIT)
FROM repo.[IndexColumn_virtual] AS icv
INNER JOIN repo.[Index_virtual] AS iv
 ON icv.index_guid = iv.index_guid
INNER JOIN [repo].[RepoObjectColumn] roc
 ON roc.[RepoObjectColumn_guid] = icv.[RepoObjectColumn_guid]
LEFT JOIN repo.RepoObject AS ro
 ON ro.RepoObject_guid = [iv].[parent_RepoObject_guid]
```

</details>

[Back to top](#dhw_self)

### repo.IndexColumn_virtual_referenced_setpoint

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | no |  |
| index_column_id | INT | no |  |
| is_descending_key | BIT | yes |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| RowNumberInReferencing | INT | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
Sollwert
jeder Index in [repo].[Index__virtual], der einen [referenced_index_guid] hat, der also geerbt wird
benötigt für diesen geerbten Index auch geerbte Spalten
alle benötigten Spalten werden hier aufgelistet

Setpoint:
each index in [repo].[Index__virtual], having a [referenced_index_guid] (the index is inherited)
also needs the columns
these required columns are listed here
this view is a "setpoint"
all these columns should exists in [repo].[IndexColumn__virtual]



isue:
some combinations of ([index_guid], [index_column_id]) are not unique
why?
because they have multiple [referencing_RepoObjectColumn_guid]
but this is wrong, only one referencing_RepoObjectColumn_guid is possible per [index_column_id]

=> [RowNumberInReferencing]



*/
CREATE VIEW [repo].[IndexColumn_virtual_referenced_setpoint]
AS
--
SELECT [i].[index_guid] --referencing index, which inherits columns from referenced index 
 , [ic].[index_column_id]
 , [ic].[is_descending_key]
 , [ic].[referencing_RepoObjectColumn_guid] --columns in the referencing RepoObject
 , [i].[referenced_index_guid] --referenced index, which is the source for inherited columns 
 , [i].[RowNumberInReferencing]
 --only for testing:
 , [ic].[referenced_RepoObjectColumn_guid]
 , [ic].[referenced_RepoObject_guid]
 , [ic].[referencing_RepoObject_guid]
FROM repo.[Index_virtual] AS i
INNER JOIN repo.IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T AS ic --setpoint belongs to the parent_RepoObject of the index
 ON ic.referencing_RepoObject_guid = i.parent_RepoObject_guid
  --ic.index_guid is the referenced index (source index)
  AND ic.index_guid = i.referenced_index_guid
  AND ic.[RowNumberInReferencing] = i.[RowNumberInReferencing]

```

</details>

[Back to top](#dhw_self)

### repo.IndexReferencedReferencing

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| source_index_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RowNumberInReferencing_Target | INT | yes |  |
| source_index_type | TINYINT | no |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql



/*
Was ist der Sinn dieser Sicht?

Es muss bedacht werden, dass der gleiche Quell-Index im Zielobjekt mehrere Vererbungen haben kann,
wenn die Quelle mehrfach verwendet wird und der Quell-Index somit auch mehrfach im Ziel vorhanden sein kann
Das ist so lange OK, wie es im referenced unterschiedliche Spalten sind.

Wir müssten noch irgendwo prüfen, ob die gleiche Spalten-Kombination aus verschiedenen Quellen geerbt wird
Und dann dürfte es den Index nur einmal geben, aber möglicherweise mit mehrfachen Quellen?
Oder brauchen wir nur eine Quelle und ignorieren einfach weitere Quellen?

repo.RepoObject_reference__union
fasst aber alle Referenzen zwischen Objekten zusammen, auch wenn es da mehrere Ausprägungen gibt

Wenn repo.Index__virtual AS i_v richtig gefüllt wird, dann müsste es in folgender Sicht auch eine Einträge mit Anz > 1 geben 

SELECT
       [source_index_guid]
     , [referenced_RepoObject_guid]
     , [referencing_RepoObject_guid]
     , COUNT(*) AS [Anz]
FROM
     repo.IndexReferencedReferencing AS T1
GROUP BY
         [source_index_guid]
       , [referenced_RepoObject_guid]
       , [referencing_RepoObject_guid]
ORDER BY
         [Anz] DESC

*/
CREATE VIEW [repo].[IndexReferencedReferencing]
AS
--
SELECT [i_s].[index_guid] AS [source_index_guid]
 , [ror].[referencing_RepoObject_guid]
 , [i_v].[RowNumberInReferencing] AS [RowNumberInReferencing_Target]
 , [i_s].[index_type] AS [source_index_type]
 , [ror].[referenced_RepoObject_guid]
 , [i_v].[referenced_index_guid] AS [referenced_index_guid]
FROM repo.Index_union AS i_s --index source: index in referenced source object(s)
INNER JOIN repo.[RepoObject_reference_union] AS ror
 ON ror.referenced_RepoObject_guid = i_s.parent_RepoObject_guid
LEFT JOIN repo.[Index_virtual] AS i_v
 ON i_v.referenced_index_guid = i_s.index_guid
  AND i_v.parent_RepoObject_guid = ror.referencing_RepoObject_guid

```

</details>

[Back to top](#dhw_self)

### repo.IndexReferencedReferencing_HasFullColumnsInReferencing

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| source_index_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RowNumberInReferencing_Target | INT | yes |  |
| source_index_type | TINYINT | no |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_index_guid | UNIQUEIDENTIFIER | yes |  |
| RowNumberInReferencing | BIGINT | yes |  |
| referencing_IndexPatternColumnGuid | VARCHAR(8000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql




/*
HasFullColumnsInReferencing:
Filter repo.IndexReferencedReferencing
all columns, existing in referenced, should also exist in referencing
in other words, the referenced index is completely contained in the referencing object 

keep in mind, that a [source_index_guid] can be inherited into several [referenced_index_guid]
if the source object is used several times but target columns are different

Thats why we have [RowNumberInReferencing] and [RowNumberInReferencing_Target]

But [RowNumberInReferencing_Target] is a bit hard to understand. it is the [RowNumberInReferencing] stored before (in earlier runs) into [repo].[Index_virtual]
the same index can be inherited several times into the same referenced object, if a source is used several times
for example
SELECT A_A = A.A, B_A = B.A from source_1 as A LEFT JOIN source_1 as B ON ... 
normaly these indexes should have different columns

Issue:
if [repo].[Index_virtual].[referenced_index_guid] is missing, then it could be contained in repo.IndexReferencedReferencing
but [referenced_index_guid] is NULL in this case

How we could / should create a missing but possible [repo].[Index_virtual].[referenced_index_guid]?
=> in usp_index_inheritance
not only insert, but also update of [repo].[Index_virtual].[referenced_index_guid] if it is NULL but it has a source_index here in this view
*/
CREATE VIEW [repo].[IndexReferencedReferencing_HasFullColumnsInReferencing]
AS
--
SELECT [T1].[source_index_guid]
 , [T1].[referencing_RepoObject_guid]
 , [T1].[RowNumberInReferencing_Target]
 , [T1].[source_index_type]
 , [T1].[referenced_RepoObject_guid]
 , [T1].[referenced_index_guid]
 , [T2].[RowNumberInReferencing]
 , [T3].[referencing_IndexPatternColumnGuid]
FROM repo.IndexReferencedReferencing AS T1
INNER JOIN [repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T] AS [T2]
 ON [T1].[source_index_guid] = [T2].[index_guid]
  AND [T1].[referenced_RepoObject_guid] = [T2].[referenced_RepoObject_guid]
  AND [T1].[referencing_RepoObject_guid] = [T2].[referencing_RepoObject_guid]
LEFT JOIN [repo].[Index_referencing_IndexPatternColumnGuid] AS T3
 ON T3.[source_index_guid] = [T1].[source_index_guid]
  AND T3.[referencing_RepoObject_guid] = [T1].[referencing_RepoObject_guid]

```

</details>

[Back to top](#dhw_self)

### repo.InheritanceType

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| InheritanceType | INT | no |  |
| InheritanceTypeDescription | VARCHAR(83) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE   VIEW [repo].[InheritanceType]
AS
--
SELECT
       [InheritanceType] = 0
     , [InheritanceTypeDescription] = 'No inheritance from predecessor'
--
UNION ALL
SELECT
       [InheritanceType] = 11
     , [InheritanceTypeDescription] = 'Inheritance from first (or all) predecessor, if current value is NULL'
UNION ALL
SELECT
       [InheritanceType] = 12
     , [InheritanceTypeDescription] = 'Inheritance from first (or all) predecessor, if current value is NULL or empty ('''')'
UNION ALL
SELECT
       [InheritanceType] = 13
     , [InheritanceTypeDescription] = 'Inheritance from first (or all) predecessor, forced, only when source is not empty'
UNION ALL
SELECT
       [InheritanceType] = 14
     , [InheritanceTypeDescription] = 'Inheritance from first (or all) predecessor, forced without exception (dangerous!)'
----
--UNION ALL
--SELECT
--       [InheritanceType] = 21
--     , [InheritanceTypeDescription] = 'Inheritance from all predecessors - STRING_AGG(xyz, CHAR(13)+CHAR(10)), if current value is NULL'
--UNION ALL
--SELECT
--       [InheritanceType] = 22
--     , [InheritanceTypeDescription] = 'Inheritance from all predecessors - STRING_AGG(xyz, CHAR(13)+CHAR(10)), if current value is NULL or empty ('''')'
--UNION ALL
--SELECT
--       [InheritanceType] = 23
--     , [InheritanceTypeDescription] = 'Inheritance from all predecessors - STRING_AGG(xyz, CHAR(13)+CHAR(10)), forced, only when source is not empty'
--UNION ALL
--SELECT
--       [InheritanceType] = 24
--     , [InheritanceTypeDescription] = 'Inheritance from all predecessors - STRING_AGG(xyz, CHAR(13)+CHAR(10)), forced without exception (dangerous!)'

----still unclear if and how this could or should be implemented
----additional parameters for CONCAT String required
--UNION ALL
--SELECT
--       [InheritanceType] = 31
--     , [InheritanceTypeDescription] = 'use CONCAT (for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')''), Inheritance from first predecessor, if current value is NULL'
--UNION ALL
--SELECT
--       [InheritanceType] = 32
--     , [InheritanceTypeDescription] = 'use CONCAT (for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')''), Inheritance from first predecessor, if current value is NULL or empty ('''')'
--UNION ALL
--SELECT
--       [InheritanceType] = 33
--     , [InheritanceTypeDescription] = 'use CONCAT (for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')''), Inheritance from first predecessor, force'




```

</details>

[Back to top](#dhw_self)

### repo.join_type

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| join_type_variant | VARCHAR(16) | no |  |
| join_type | VARCHAR(16) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW repo.join_type
AS
--
SELECT [join_type_variant] = 'INNER JOIN'
 , [join_type] = 'INNER JOIN'

UNION ALL

SELECT [join_type_variant] = 'LEFT OUTER JOIN'
 , [join_type] = 'LEFT OUTER JOIN'

UNION ALL

SELECT [join_type_variant] = 'LEFT JOIN'
 , [join_type] = 'LEFT OUTER JOIN'

UNION ALL

SELECT [join_type_variant] = 'RIGHT OUTER JOIN'
 , [join_type] = 'RIGHT OUTER JOIN'

UNION ALL

SELECT [join_type_variant] = 'RIGHT JOIN'
 , [join_type] = 'RIGHT OUTER JOIN'

UNION ALL

SELECT [join_type_variant] = 'FULL OUTER JOIN'
 , [join_type] = 'FULL OUTER JOIN'

UNION ALL

SELECT [join_type_variant] = 'CROSS JOIN'
 , [join_type] = 'CROSS JOIN'
```

</details>

[Back to top](#dhw_self)

### repo.Match_RepoObject_referenced_UspPersistence

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| FirstNode | UNIQUEIDENTIFIER | yes |  |
| FirstNodeName | NVARCHAR(261) | yes |  |
| LastNode | UNIQUEIDENTIFIER | yes |  |
| LastNodeName | NVARCHAR(261) | yes |  |
| ListNodeName | NVARCHAR(4000) | yes |  |
| First_usp_persistence_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| Last_usp_persistence_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| First_usp_persistence_name | NVARCHAR(140) | yes |  |
| Last_usp_persistence_name | NVARCHAR(140) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
Create View repo.Match_RepoObject_referenced_UspPersistence
As
Select
    -- 
    Q.FirstNode
  , Q.FirstNodeName
  , Q.LastNode
  , Q.LastNodeName
  , Q.ListNodeName
  , ro1.[usp_persistence_RepoObject_guid] As First_usp_persistence_RepoObject_guid
  , ro2.[usp_persistence_RepoObject_guid] As Last_usp_persistence_RepoObject_guid
  , ro1.[usp_persistence_name]            As First_usp_persistence_name
  , ro2.[usp_persistence_name]            As Last_usp_persistence_name
From
(
    Select
        --
        Object1.[RepoObject_guid]                                                 As FirstNode
      , Object1.[RepoObject_fullname]                                             As FirstNodeName
      , String_Agg (Object2.[RepoObject_fullname], '->') WITHIN Group(GRAPH PATH) As ListNodeName
      , Last_Value (Object2.[RepoObject_guid]) WITHIN Group(GRAPH PATH)           As LastNode
      , Last_Value (Object2.[RepoObject_fullname]) WITHIN Group(GRAPH PATH)       As LastNodeName
    From [graph].[RepoObject] As Object1
       , [graph].[ReferencedObject] For PATH As referenced
       , [graph].[RepoObject] For PATH As Object2
    Where MATCH(SHORTEST_PATH(Object1(-(referenced)->Object2)+))
                And Object1.[RepoObject_type] In ( 'u', 'v' )
)                                       As Q
    Left Join [repo].[RepoObject_gross] ro1
        On ro1.RepoObject_guid = Q.FirstNode
    Left Join [repo].[RepoObject_gross] ro2
        On ro2.RepoObject_guid = Q.LastNode
Where ro1.[is_persistence] = 1
      And ro2.[is_persistence] = 1

```

</details>

[Back to top](#dhw_self)

### repo.Parameter_default

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Parameter_name | VARCHAR(52) | no |  |
| sub_Parameter | NVARCHAR(26) | no |  |
| Parameter_desciption | NVARCHAR(217) | no |  |
| Parameter_default_value | SQL_VARIANT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql













-- Alter View Parameter_default
/*
--merge this view into [repo].[Parameter]:

EXEC [repo].[usp_init_parameter]

--remove, what not is defined here (Dangerous: possible data loss)
--do not delete based on [sub_Parameter]!
--they can always be added!

DELETE T
FROM [repo].[Parameter] T
WHERE NOT EXISTS (
  SELECT 1
  FROM [repo].[Parameter_default] S
  WHERE S.[Parameter_name] = T.[Parameter_name]
  )


*/
CREATE VIEW [repo].[Parameter_default]
AS
--
--first [Parameter_default_value] datatype should be SQL_VARIANT to avoid taye casting issues for other entries
SELECT [Parameter_name] = 'DUMMY'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'dummy parameter, data type SQL_Variant'
 , [Parameter_default_value] = CAST(N'' AS SQL_VARIANT)

UNION ALL

SELECT [Parameter_name] = 'dwh_database_name'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'The database name must be the same as the one used in the synonyms'
 , [Parameter_default_value] = CAST(N'master' AS SYSNAME)

UNION ALL

SELECT [Parameter_name] = 'main enable usp_RepoObjectSource_FirstResultSet'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'execute (or not) usp_RepoObjectSource_FirstResultSet'
 , [Parameter_default_value] = 0

UNION ALL

SELECT [Parameter_name] = 'main enable usp_RepoObject_update_SysObjectQueryPlan'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'execute (or not) usp_RepoObject_update_SysObjectQueryPlan'
 , [Parameter_default_value] = 0

UNION ALL

SELECT [Parameter_name] = 'main enable usp_RepoObjectSource_QueryPlan'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'execute (or not) usp_RepoObjectSource_QueryPlan'
 , [Parameter_default_value] = 0

UNION ALL

SELECT [Parameter_name] = 'persistence_name_suffix'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'default suffix for persistence table which will be added to source object name'
 , [Parameter_default_value] = CAST(N'_T' AS SYSNAME)

UNION ALL

SELECT [Parameter_name] = 'Hist_ValidFrom_column_name'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'default column name for column - datetime2 GENERATED ALWAYS AS ROW START'
 , [Parameter_default_value] = CAST(N'ValidFrom' AS SYSNAME)

UNION ALL

SELECT [Parameter_name] = 'Hist_ValidTo_column_name'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'default column name for column - datetime2 GENERATED ALWAYS AS ROW END'
 , [Parameter_default_value] = CAST(N'ValidTo' AS SYSNAME)

UNION ALL

SELECT [Parameter_name] = 'Hist_Table_schema'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'default: NULL - The historization table uses the same schema as the table to be historized. otherwise the given schema is used'
 , [Parameter_default_value] = NULL

UNION ALL

SELECT [Parameter_name] = 'Hist_Table_name_suffix'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'default suffix for historization table which will be added to historized object name'
 , [Parameter_default_value] = CAST(N'_hist' AS SYSNAME)

UNION ALL

SELECT [Parameter_name] = 'RepoObjectColumn_column_id_OrderBy'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'used in repo.usp_RepoObjectColumn__update_RepoObjectColumn_column_id to define the order of columns'
 , [Parameter_default_value] = CAST(N'
ISNULL([ic].[index_column_id] , 99999) --ensure PK index is sorted before other columns
, [roc].[Repo_is_computed] --computed columns after normal columns
, [roc].[Repo_is_identity] --IDENTITY columns after normal columns, because nothing should be inserted (they are like computed columns)
, [roc].[Repo_generated_always_type]
, [roc].[RepoObjectColumn_name]
' AS NVARCHAR(4000))
--
--the following parameters can have [sub_Parameter]

UNION ALL

SELECT [Parameter_name] = 'Inheritance_StringAggSeparatorSql_column'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'if NULL then only one source is used for inheritance; if not NULL then STRING_AGG( expression, separator ) is used to aggregate all sources. Content is interpreted as TSQL. Good values are ''CHAR(13)+CHAR(10)'' or '''';'''''
 , [Parameter_default_value] = CAST(NULL AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'Inheritance_StringAggSeparatorSql_column'
 , [sub_Parameter] = N'ReferencedObjectColumnList'
 , [Parameter_desciption] = N'if NULL then only one source is used for inheritance; if not NULL then STRING_AGG( expression, separator ) is used to aggregate all sources. Content is interpreted as TSQL. Good values are ''CHAR(13)+CHAR(10)'' or '''';'''''
 , [Parameter_default_value] = CAST(CHAR(13)+CHAR(10) AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'Inheritance_StringAggSeparatorSql_object'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'if NULL then only one source is used for inheritance; if not NULL then STRING_AGG( expression, separator ) is used to aggregate all sources. Content is interpreted as TSQL. Good values are ''CHAR(13)+CHAR(10)'' or '''';'''''
 , [Parameter_default_value] = CAST(NULL AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'Inheritance_StringAggSeparatorSql_object'
 , [sub_Parameter] = N'ReferencedObjectList'
 , [Parameter_desciption] = N'if NULL then only one source is used for inheritance; if not NULL then STRING_AGG( expression, separator ) is used to aggregate all sources. Content is interpreted as TSQL. Good values are ''CHAR(13)+CHAR(10)'' or '''';'''''
 , [Parameter_default_value] = CAST(CHAR(13)+CHAR(10) AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceDefinition_column'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'CONCAT arguments to be used with some specific values in [repo].[InheritanceType], for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')'''
 , [Parameter_default_value] = CAST(NULL AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceDefinition_column'
 , [sub_Parameter] = N'MS_Description'
 , [Parameter_desciption] = N'CONCAT arguments to be used with some specific values in [repo].[InheritanceType], for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')'''
 , [Parameter_default_value] = CAST('CAST(COALESCE(referencing.[Repo_definition], repo.fs_get_RepoObjectColumnProperty_nvarchar(referenced.[RepoObjectColumn_guid], ''MS_Description'')) AS NVARCHAR(4000))' AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceDefinition_column'
 , [sub_Parameter] = N'ReferencedObjectColumnList'
 , [Parameter_desciption] = N'CONCAT arguments to be used with some specific values in [repo].[InheritanceType], for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')'''
 , [Parameter_default_value] = CAST('referenced.[RepoObjectColumn_fullname]' AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceDefinition_object'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'CONCAT arguments to be used with some specific values in [repo].[InheritanceType], for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')'''
 , [Parameter_default_value] = CAST(NULL AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceDefinition_object'
 , [sub_Parameter] = N'MS_Description'
 , [Parameter_desciption] = N'CONCAT arguments to be used with some specific values in [repo].[InheritanceType], for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')'''
 , [Parameter_default_value] = CAST(NULL AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceDefinition_object'
 , [sub_Parameter] = N'ReferencedObjectList'
 , [Parameter_desciption] = N'CONCAT arguments to be used with some specific values in [repo].[InheritanceType], for example: ''[RepoObject_name],CHAR(13),CHAR(10),EineNochZuDefinierendeFunktion(''MS_Description'')'''
 , [Parameter_default_value] = CAST('referenced.[RepoObject_fullname]' AS NVARCHAR(4000))

UNION ALL

SELECT [Parameter_name] = 'InheritanceType_column'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'TINYINT; InheritanceType for column: possible values in [repo].[InheritanceType]'
 , [Parameter_default_value] = CAST(0 AS TINYINT)

UNION ALL

SELECT [Parameter_name] = 'InheritanceType_column'
 , [sub_Parameter] = N'MS_Description'
 , [Parameter_desciption] = N'TINYINT; InheritanceType for column: possible values in [repo].[InheritanceType]'
 , [Parameter_default_value] = CAST(0 AS TINYINT)

UNION ALL

SELECT [Parameter_name] = 'InheritanceType_column'
 , [sub_Parameter] = N'ReferencedObjectColumnList'
 , [Parameter_desciption] = N'TINYINT; InheritanceType for object: possible values in [repo].[InheritanceType]'
 , [Parameter_default_value] = CAST(14 AS TINYINT)

UNION ALL

SELECT [Parameter_name] = 'InheritanceType_object'
 , [sub_Parameter] = N''
 , [Parameter_desciption] = N'TINYINT; InheritanceType for object: possible values in [repo].[InheritanceType]'
 , [Parameter_default_value] = CAST(0 AS TINYINT)

UNION ALL

SELECT [Parameter_name] = 'InheritanceType_object'
 , [sub_Parameter] = N'MS_Description'
 , [Parameter_desciption] = N'TINYINT; InheritanceType for object: possible values in [repo].[InheritanceType]'
 , [Parameter_default_value] = CAST(0 AS TINYINT)

UNION ALL

SELECT [Parameter_name] = 'InheritanceType_object'
 , [sub_Parameter] = N'ReferencedObjectList'
 , [Parameter_desciption] = N'TINYINT; InheritanceType for object: possible values in [repo].[InheritanceType]'
 , [Parameter_default_value] = CAST(14 AS TINYINT)

----todo: Warum sollte es eine Unterscheidung zwischen Sichten und Tabellen geben?
--UNION ALL

--SELECT [Parameter_name] = 'InheritanceType_object_type_u'
-- , [sub_Parameter] = N''
-- , [Parameter_desciption] = N'TINYINT; InheritanceType for object type U (user table): possible values in [repo].[InheritanceType]'
-- , [Parameter_default_value] = CAST(0 AS TINYINT)

--UNION ALL

--SELECT [Parameter_name] = 'InheritanceType_object_type_u'
-- , [sub_Parameter] = N'MS_Description'
-- , [Parameter_desciption] = N'TINYINT; InheritanceType for object type U (user table): possible values in [repo].[InheritanceType]'
-- , [Parameter_default_value] = CAST(0 AS TINYINT)
----

--UNION ALL

--SELECT [Parameter_name] = 'InheritanceType_object_type_v'
-- , [sub_Parameter] = N''
-- , [Parameter_desciption] = N'TINYINT; InheritanceType for object type V (view): possible values in [repo].[InheritanceType]'
-- , [Parameter_default_value] = CAST(0 AS TINYINT)

--UNION ALL

--SELECT [Parameter_name] = 'InheritanceType_object_type_v'
-- , [sub_Parameter] = N'MS_Description'
-- , [Parameter_desciption] = N'TINYINT; InheritanceType for object type V (view): possible values in [repo].[InheritanceType]'
-- , [Parameter_default_value] = CAST(0 AS TINYINT)


```

</details>

[Back to top](#dhw_self)

### repo.ProcedureInstanceDependency_gross

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| id | INT | no |  |
| referenced_id | INT | no |  |
| referencing_id | INT | no |  |
| is_active | BIT | no |  |
| is_PersistenceDependency | BIT | no |  |
| Description | NVARCHAR(4000) | yes |  |
| referenced_Instance | VARCHAR(500) | no |  |
| referenced_RepoObject_fullname | NVARCHAR(261) | no |  |
| referenced_Procedure_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referencing_Instance | VARCHAR(500) | no |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | no |  |
| referencing_Procedure_RepoObject_guid | UNIQUEIDENTIFIER | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW repo.ProcedureInstanceDependency_gross
AS
SELECT
 --
 [pid].[id]
 , [pid].[referenced_id]
 , [pid].[referencing_id]
 , [pid].[is_active]
 , [pid].[is_PersistenceDependency]
 , [pid].[Description]
 , [pi_1].[Instance] AS [referenced_Instance]
 , [ro_1].[RepoObject_fullname] AS [referenced_RepoObject_fullname]
 , [pi_1].[Procedure_RepoObject_guid] AS [referenced_Procedure_RepoObject_guid]
 , [pi_2].[Instance] AS [referencing_Instance]
 , [ro_2].[RepoObject_fullname] AS [referencing_RepoObject_fullname]
 , [pi_2].[Procedure_RepoObject_guid] AS [referencing_Procedure_RepoObject_guid]
FROM repo.ProcedureInstanceDependency AS pid
INNER JOIN repo.ProcedureInstance AS pi_1
 ON pid.referenced_id = pi_1.id
INNER JOIN repo.ProcedureInstance AS pi_2
 ON pid.referencing_id = pi_2.id
INNER JOIN repo.RepoObject AS ro_1
 ON pi_1.Procedure_RepoObject_guid = ro_1.RepoObject_guid
INNER JOIN repo.RepoObject AS ro_2
 ON pi_2.Procedure_RepoObject_guid = ro_2.RepoObject_guid

```

</details>

[Back to top](#dhw_self)

### repo.PropertyName_RepoObject

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[PropertyName_RepoObject]
AS
SELECT DISTINCT
 --
 [property_name]
FROM [repo].[RepoObjectProperty]

UNION

SELECT DISTINCT
 --
 [sub_Parameter]
FROM [repo].[Parameter]
WHERE [Parameter_name] IN (
  'Inheritance_StringAggSeparatorSql_object'
  , 'InheritanceDefinition_object'
  , 'InheritanceType_object'
  )
 AND [sub_Parameter] <> ''

```

</details>

[Back to top](#dhw_self)

### repo.PropertyName_RepoObjectColumn

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[PropertyName_RepoObjectColumn]
AS
SELECT DISTINCT
 --
 [property_name]
FROM [repo].[RepoObjectColumnProperty]

UNION

SELECT DISTINCT
 --
 [sub_Parameter]
FROM [repo].[Parameter]
WHERE [Parameter_name] IN (
  'Inheritance_StringAggSeparatorSql_column'
  , 'InheritanceDefinition_column'
  , 'InheritanceType_column'
  )
 AND [sub_Parameter] <> ''

```

</details>

[Back to top](#dhw_self)

### repo.Reference_UspPersistence

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referenced_usp_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_usp_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_usp_persistence_name | NVARCHAR(140) | yes |  |
| referencing_usp_persistence_name | NVARCHAR(140) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[ProcedureReferencePersistence]
AS
SELECT [Last_usp_persistence_RepoObject_guid] AS [referenced_usp_RepoObject_guid]
 , [First_usp_persistence_RepoObject_guid] AS [referencing_usp_RepoObject_guid]
 , [Last_usp_persistence_name] AS [referenced_usp_persistence_name]
 , [First_usp_persistence_name] AS [referencing_usp_persistence_name]
FROM [repo].[Match_RepoObject_referenced_UspPersistence]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_ColumnList

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| CreateColumnList | NVARCHAR(MAX) | yes |  |
| DbmlColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceCompareColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceInsertColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceUpdateColumnList | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql



CREATE VIEW [repo].[RepoObject_ColumnList]
AS
SELECT roc.[RepoObject_guid]
 , CreateColumnList = String_Agg(CONCAT (
   --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
   CAST('' AS NVARCHAR(MAX))
   , QuoteName(roc.[RepoObjectColumn_name])
   , ' '
   , CASE roc.Repo_is_computed
    WHEN 1
     THEN CONCAT (
       'AS '
       , roc.Repo_definition
       , CASE 
        WHEN roc.Repo_is_persisted = 1
         THEN ' PERSISTED'
        END
       )
    ELSE CONCAT (
      roc.[Repo_user_type_fullname]
      --CONSTRAINT
      --DEFAULT
      , CASE 
       WHEN roc.[Repo_default_name] <> ''
        AND IsNull(roc.[Repo_default_is_system_named], 0) = 0
        THEN CONCAT (
          ' CONSTRAINT '
          , roc.[Repo_default_name]
          )
       END
      --
      , CASE 
       WHEN roc.[Repo_default_definition] <> ''
        THEN CONCAT (
          ' DEFAULT '
          , roc.[Repo_default_definition]
          )
       END
      --temporal table columns
      , CASE roc.[Repo_generated_always_type]
       WHEN 1
        THEN ' GENERATED ALWAYS AS ROW START'
       WHEN 2
        THEN ' GENERATED ALWAYS AS ROW END'
       END
      --IDENTITY
      --, CASE roc.Repo_is_identity
      -- WHEN 1
      --  THEN ' IDENTITY ' + CASE 
      --    WHEN NOT roc.[Repo_seed_value] IS NULL
      --     AND NOT roc.[Repo_increment_value] IS NULL
      --     THEN CONCAT (
      --       '('
      --       , CAST(roc.[Repo_seed_value] AS NVARCHAR(max))
      --       , ', '
      --       , CAST(roc.[Repo_increment_value] AS NVARCHAR(max))
      --       , ')'
      --       )
      --    END
      -- END
      , CASE roc.[Repo_is_identity]
       WHEN 1
        THEN CONCAT (
          ' IDENTITY ('
          , IsNull(CAST(roc.[Repo_seed_value] AS NVARCHAR(MAX)), '1')
          , ', '
          , IsNull(CAST(roc.[Repo_increment_value] AS NVARCHAR(MAX)), '1')
          , ')'
          )
       END
      , CASE 
       WHEN roc.[Repo_is_nullable] = 0
        OR roc.[Repo_generated_always_type] >= 1
        THEN ' NOT'
       END
      , ' NULL '
      )
    END
   , CHAR(13)
   , CHAR(10)
   ), ', ') WITHIN
GROUP (
  ORDER BY roc.RepoObjectColumn_column_id
  )
 , DbmlColumnList = String_Agg(CONCAT (
   --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
   CAST('' AS NVARCHAR(MAX))
   , QUOTENAME(roc.[RepoObjectColumn_name], '"')
   , ' '
   , roc.[Repo_user_type_fullname]
   , ' '
   , '['
   --null or not null
   , CASE 
    WHEN roc.[Repo_is_nullable] = 0
     OR roc.[Repo_generated_always_type] >= 1
     THEN 'not'
    END
   , ' null'
   --primary key or pk
   , CASE 
    WHEN roc.[is_index_primary_key] = 1
     THEN ', pk'
    END
   --unique
   --default: some_value
   --Attention: 
   --number value starts blank: default: 123 or default: 123.456
   --string value starts with single quotes: default: 'some string value'
   --expression value is wrapped with parenthesis: default: `now() - interval '5 days'`
   --boolean (true/false/null): default: false or default: null
   --
   , CASE 
    WHEN roc.[Repo_default_definition] <> ''
     THEN CONCAT (
       ', default: '
       , QUOTENAME(roc.[Repo_default_definition], '`')
       )
    END
   --increment
   , CASE roc.[Repo_is_identity]
    WHEN 1
     THEN ', increment'
    END
   --note: 'string to add notes'
   , CASE 
    WHEN NOT roc.Property_ms_description IS NULL
     THEN ', Note: ''''''' +CHAR(13) + CHAR(10) + REPLACE(REPLACE(roc.Property_ms_description, '\', '\\'),'''''''','\''''''') +CHAR(13) + CHAR(10) +  ''''''''
    END
   , ']'
   ), CHAR(13) + CHAR(10)) WITHIN
GROUP (
  ORDER BY roc.RepoObjectColumn_column_id
  )
 , PersistenceCompareColumnList = STUFF(String_Agg(CONCAT (
    --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
    CAST('' AS NVARCHAR(MAX))
    , ''
    , CASE 
     WHEN
      --source should exists
      NOT roc.[persistence_source_RepoObjectColumn_guid] IS NULL
      AND IsNull(roc.[is_persistence_no_include], 0) = 0
      AND IsNull(roc.[is_persistence_no_check], 0) = 0
      AND IsNull(roc.is_query_plan_expression, 0) = 0
      AND roc.Repo_generated_always_type = 0
      AND roc.Repo_is_computed = 0
      AND roc.Repo_is_identity = 0
      --do not compare PK
      --issue: if the source column is marked as PK but the target column is not marked as PK, then this column is included
      --to avoid this we would need to analyze also the source column properties
      --or we could set [is_persistence_no_check] = 1
      AND roc.[is_index_primary_key] IS NULL
      THEN CONCAT (
        'OR T.'
        , QuoteName(roc.[RepoObjectColumn_name])
        , ' <> S.'
        , QuoteName(roc.[RepoObjectColumn_name])
        , CASE 
         WHEN roc.Repo_is_nullable = 1
          THEN CONCAT (
            ' OR (S.'
            , QuoteName(roc.[RepoObjectColumn_name])
            , ' IS NULL AND NOT T.'
            , QuoteName(roc.[RepoObjectColumn_name])
            , ' IS NULL)'
            , ' OR (NOT S.'
            , QuoteName(roc.[RepoObjectColumn_name])
            , ' IS NULL AND T.'
            , QuoteName(roc.[RepoObjectColumn_name])
            , ' IS NULL)'
            )
         END
        , CHAR(13)
        , CHAR(10)
        )
     END
    ), '') WITHIN GROUP (
   ORDER BY roc.RepoObjectColumn_column_id
   ), 1, 3, '   ')
 , PersistenceInsertColumnList = STUFF(String_Agg(CONCAT (
    --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
    CAST('' AS NVARCHAR(MAX))
    , ''
    , CASE 
     WHEN
      --source should exists
      NOT roc.[persistence_source_RepoObjectColumn_guid] IS NULL
      AND IsNull(roc.[is_persistence_no_include], 0) = 0
      AND IsNull(roc.is_query_plan_expression, 0) = 0
      AND roc.Repo_generated_always_type = 0
      AND roc.Repo_is_computed = 0
      AND roc.Repo_is_identity = 0
      THEN CONCAT (
        ', '
        , QuoteName(roc.[RepoObjectColumn_name])
        , CHAR(13)
        , CHAR(10)
        )
     END
    ), '') WITHIN GROUP (
   ORDER BY roc.RepoObjectColumn_column_id
   ), 1, 2, '  ')
 , PersistenceUpdateColumnList = STUFF(String_Agg(CONCAT (
    --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
    CAST('' AS NVARCHAR(MAX))
    , ''
    , CASE 
     WHEN
      --source should exists
      NOT roc.[persistence_source_RepoObjectColumn_guid] IS NULL
      AND IsNull(roc.[is_persistence_no_include], 0) = 0
      AND IsNull(roc.[is_persistence_no_check], 0) = 0
      AND IsNull(roc.is_query_plan_expression, 0) = 0
      AND roc.Repo_generated_always_type = 0
      AND roc.Repo_is_computed = 0
      AND roc.Repo_is_identity = 0
      THEN CONCAT (
        ', T.'
        , QuoteName(roc.[RepoObjectColumn_name])
        , ' = S.'
        , QuoteName(roc.[RepoObjectColumn_name])
        , CHAR(13)
        , CHAR(10)
        )
     END
    ), '') WITHIN GROUP (
   ORDER BY roc.RepoObjectColumn_column_id
   ), 1, 2, '  ')
FROM [repo].[RepoObjectColumn_gross] AS roc
WHERE
 --not [is_query_plan_expression]
 roc.[is_query_plan_expression] IS NULL
 --we need the datatype, or it should be computed
 AND (
  NOT roc.[Repo_user_type_fullname] IS NULL
  OR roc.Repo_is_computed = 1
  )
GROUP BY roc.[RepoObject_guid]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_fullname_u_v

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_fullname | NVARCHAR(261) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/****** Script for SelectTopNRows command from SSMS  ******/
CREATE VIEW repo.RepoObject_fullname_u_v
AS
SELECT [RepoObject_fullname]
FROM [repo].[RepoObject]
WHERE [RepoObject_type] IN (
  'u'
  , 'v'
  )

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_gross

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_schema_name | NVARCHAR(128) | no |  |
| RepoObject_name | NVARCHAR(128) | no |  |
| RepoObject_type | CHAR(2) | no |  |
| has_different_sys_names | BIT | yes |  |
| has_execution_plan_issue | BIT | yes |  |
| has_get_referenced_issue | BIT | yes |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |
| InheritanceType | TINYINT | yes |  |
| is_in_reference | INT | no |  |
| is_repo_managed | BIT | yes |  |
| is_RepoObject_name_uniqueidentifier | INT | no |  |
| is_SysObject_missing | BIT | yes |  |
| is_SysObject_name_uniqueidentifier | INT | no |  |
| modify_dt | DATETIME | no |  |
| node_id | BIGINT | yes |  |
| pk_index_guid | UNIQUEIDENTIFIER | yes |  |
| Repo_history_table_guid | UNIQUEIDENTIFIER | yes |  |
| Repo_temporal_type | TINYINT | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_Referencing_Count | INT | yes |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| SysObject_id | INT | yes |  |
| SysObject_modify_date | DATETIME | yes |  |
| SysObject_name | NVARCHAR(128) | no |  |
| SysObject_parent_object_id | INT | no |  |
| SysObject_query_executed_dt | DATETIME | yes |  |
| SysObject_query_plan | XML | yes |  |
| SysObject_query_sql | NVARCHAR(406) | no |  |
| SysObject_schema_name | NVARCHAR(128) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| usp_persistence_name | NVARCHAR(140) | no |  |
| usp_persistence_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| persistence_source_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| persistence_source_RepoObject_fullname | NVARCHAR(261) | yes |  |
| persistence_source_SysObject_fullname | NVARCHAR(261) | yes |  |
| has_history | BIT | yes |  |
| has_history_columns | BIT | yes |  |
| is_persistence | BIT | yes |  |
| is_persistence_check_duplicate_per_pk | BIT | yes |  |
| is_persistence_check_for_empty_source | BIT | yes |  |
| is_persistence_delete_missing | BIT | yes |  |
| is_persistence_delete_changed | BIT | yes |  |
| is_persistence_insert | BIT | yes |  |
| is_persistence_truncate | BIT | yes |  |
| is_persistence_update_changed | BIT | yes |  |
| history_schema_name | NVARCHAR(128) | yes |  |
| history_table_name | NVARCHAR(128) | yes |  |
| temporal_type | TINYINT | yes |  |
| CreateColumnList | NVARCHAR(MAX) | yes |  |
| DbmlColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceCompareColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceInsertColumnList | NVARCHAR(MAX) | yes |  |
| PersistenceUpdateColumnList | NVARCHAR(MAX) | yes |  |
| Property_ms_description | NVARCHAR(4000) | yes |  |
| sql_modules_definition | NVARCHAR(MAX) | yes |  |
| sql_modules_formatted | NVARCHAR(MAX) | yes |  |
| sql_modules_formatted2 | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_gross]
AS
--
SELECT
 --
 [ro].[RepoObject_guid]
 , [ro].[RepoObject_schema_name]
 , [ro].[RepoObject_name]
 , [ro].[RepoObject_type]
 , [ro].[has_different_sys_names]
 , [ro].[has_execution_plan_issue]
 , [ro].[has_get_referenced_issue]
 , [ro].[Inheritance_StringAggSeparatorSql]
 , [ro].[InheritanceDefinition]
 , [ro].[InheritanceType]
 , [is_in_reference] = CASE 
  WHEN EXISTS (
    SELECT 1
    FROM [graph].[RepoObject_ReferencingReferenced] AS [ref]
    WHERE [ref].[Referenced_guid] = [ro].[RepoObject_guid]
     OR [ref].[Referencing_guid] = [ro].[RepoObject_guid]
    )
   THEN 1
  ELSE 0
  END
 , [ro].[is_repo_managed]
 , [ro].[is_RepoObject_name_uniqueidentifier]
 , [ro].[is_SysObject_missing]
 , [ro].[is_SysObject_name_uniqueidentifier]
 , [ro].[modify_dt]
 , [ro].[node_id]
 , [ro].[pk_index_guid]
 , [ro].[Repo_history_table_guid]
 , [ro].[Repo_temporal_type]
 , [ro].[RepoObject_fullname]
 , [ro].[RepoObject_Referencing_Count]
 , [ro].[SysObject_fullname]
 , [ro].[SysObject_id]
 , [ro].[SysObject_modify_date]
 , [ro].[SysObject_name]
 , [ro].[SysObject_parent_object_id]
 , [QueryPlan].[SysObject_query_executed_dt]
 , [QueryPlan].[SysObject_query_plan]
 , [ro].[SysObject_query_sql]
 , [ro].[SysObject_schema_name]
 , [ro].[SysObject_type]
 , [ro].[usp_persistence_name]
 , [ro_usp_p].[RepoObject_guid] AS [usp_persistence_RepoObject_guid]
 , [ro_p].[source_RepoObject_guid] AS [persistence_source_RepoObject_guid]
 , [ro_p_s].[RepoObject_fullname] AS [persistence_source_RepoObject_fullname]
 , [ro_p_s].[SysObject_fullname] AS [persistence_source_SysObject_fullname]
 , [ro_p].[has_history]
 , [ro_p].[has_history_columns]
 , [ro_p].[is_persistence]
 , [ro_p].[is_persistence_check_duplicate_per_pk]
 , [ro_p].[is_persistence_check_for_empty_source]
 , [ro_p].[is_persistence_delete_missing]
 , [ro_p].[is_persistence_delete_changed]
 , [ro_p].[is_persistence_insert]
 , [ro_p].[is_persistence_truncate]
 , [ro_p].[is_persistence_update_changed]
 , [ro_p].[history_schema_name]
 , [ro_p].[history_table_name]
 , [ro_p].[temporal_type]
 , [ColumnList].[CreateColumnList]
 , [ColumnList].[DbmlColumnList]
 , [ColumnList].[PersistenceCompareColumnList]
 , [ColumnList].[PersistenceInsertColumnList]
 , [ColumnList].[PersistenceUpdateColumnList]
 , [Property_ms_description] = [repo].[fs_get_RepoObjectProperty_nvarchar]([ro].[RepoObject_guid], 'ms_description')
 , [SqlModules].[sql_modules_definition]
 , [SqlModules].[sql_modules_formatted]
 , [SqlModules].[sql_modules_formatted2]
FROM repo.RepoObject AS ro
LEFT OUTER JOIN repo.RepoObject_persistence AS ro_p
 ON ro_p.target_RepoObject_guid = ro.RepoObject_guid
LEFT OUTER JOIN repo.RepoObject AS ro_p_s
 ON ro_p_s.RepoObject_guid = ro_p.source_RepoObject_guid
LEFT OUTER JOIN repo.RepoObject AS ro_usp_p
 ON ro_usp_p.[RepoObject_name] = ro.[usp_persistence_name]
  AND ro_usp_p.[RepoObject_schema_name] = ro.[RepoObject_schema_name]
LEFT OUTER JOIN repo.RepoObject_ColumnList AS ColumnList
 ON ColumnList.RepoObject_guid = ro.RepoObject_guid
LEFT OUTER JOIN [repo].[RepoObject_QueryPlan] AS QueryPlan
 ON QueryPlan.[RepoObject_guid] = ro.[RepoObject_guid]
LEFT OUTER JOIN [repo].[RepoObject_SqlModules_Repo_Sys] AS SqlModules
 ON SqlModules.RepoObject_guid = [ro].[RepoObject_guid]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_InheritanceType_InheritanceDefinition

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |
| InheritanceType | INT | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_type | CHAR(2) | no |  |
| ro_InheritanceType | TINYINT | yes |  |
| sub_InheritanceType | INT | yes |  |
| par_InheritanceType | INT | yes |  |
| ro_InheritanceDefinition | NVARCHAR(4000) | yes |  |
| sub_InheritanceDefintion | NVARCHAR(4000) | yes |  |
| par_InheritanceDefintion | NVARCHAR(4000) | yes |  |
| ro_Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| sub_Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| par_Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_InheritanceType_InheritanceDefinition]
AS
SELECT
 --
 [ro].[RepoObject_guid]
 , [pn].[property_name]
 , [rop].[property_value]
 , [Inheritance_StringAggSeparatorSql] = COALESCE([ro].[Inheritance_StringAggSeparatorSql], [par_sub_sep].[Parameter_value__result_nvarchar], [par_sep].[Parameter_value__result_nvarchar])
 , [InheritanceDefinition] = COALESCE([ro].[InheritanceDefinition], [par_sub_def].[Parameter_value__result_nvarchar], [par_def].[Parameter_value__result_nvarchar])
 , [InheritanceType] = COALESCE([ro].[InheritanceType], [par_sub].[Parameter_value__result_int], [par].[Parameter_value__result_int])
 , [ro].[RepoObject_fullname]
 , [ro].[RepoObject_type]
 , [ro_InheritanceType] = [ro].[InheritanceType]
 , [sub_InheritanceType] = [par_sub].[Parameter_value__result_int]
 , [par_InheritanceType] = [par].[Parameter_value__result_int]
 , [ro_InheritanceDefinition] = [ro].[InheritanceDefinition]
 , [sub_InheritanceDefintion] = [par_sub_def].[Parameter_value__result_nvarchar]
 , [par_InheritanceDefintion] = [par_def].[Parameter_value__result_nvarchar]
 , [ro_Inheritance_StringAggSeparatorSql] = [ro].[Inheritance_StringAggSeparatorSql]
 , [sub_Inheritance_StringAggSeparatorSql] = [par_sub_sep].[Parameter_value__result_nvarchar]
 , [par_Inheritance_StringAggSeparatorSql] = [par_sep].[Parameter_value__result_nvarchar]
FROM [repo].[RepoObject] AS ro
CROSS JOIN [repo].[PropertyName_RepoObject] AS pn
LEFT JOIN [repo].[RepoObjectProperty] AS rop
 ON rop.RepoObject_guid = [ro].[RepoObject_guid]
  AND rop.property_name = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par_sub
 ON par_sub.[Parameter_name] = 'InheritanceType_object'
  AND par_sub.[sub_Parameter] = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par
 ON par.[Parameter_name] = 'InheritanceType_object'
  AND par.[sub_Parameter] = ''
LEFT JOIN [repo].[Parameter] AS par_sub_def
 ON par_sub_def.[Parameter_name] = 'InheritanceDefinition_object'
  AND par_sub_def.[sub_Parameter] = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par_def
 ON par_def.[Parameter_name] = 'InheritanceDefinition_object'
  AND par_def.[sub_Parameter] = ''
LEFT JOIN [repo].[Parameter] AS par_sub_sep
 ON par_sub_sep.[Parameter_name] = 'Inheritance_StringAggSeparatorSql_object'
  AND par_sub_sep.[sub_Parameter] = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par_sep
 ON par_sep.[Parameter_name] = 'Inheritance_StringAggSeparatorSql_object'
  AND par_sep.[sub_Parameter] = ''

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_InheritanceType_resulting_InheritanceDefinition

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| InheritanceType | INT | yes |  |
| is_force_inherit_empty_source | INT | no |  |
| is_StringAggAllSources | INT | no |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| resulting_InheritanceDefinition | NVARCHAR(4000) | yes |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_type | CHAR(2) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
--The result must be grouped to determine all required calculation variants of an inheritance

SELECT is_StringAggAllSources
 , resulting_InheritanceDefinition
FROM repo.RepoObject_InheritanceType_resulting_InheritanceDefinition
GROUP BY is_StringAggAllSources
 , resulting_InheritanceDefinition
HAVING (NOT (resulting_InheritanceDefinition IS NULL))

*/

CREATE VIEW [repo].[RepoObject_InheritanceType_resulting_InheritanceDefinition]
AS
SELECT
 --
 [inh].[RepoObject_guid]
 , [inh].[property_name]
 , [inh].[property_value]
 , [inh].[InheritanceType]
 , [is_force_inherit_empty_source] =
 --
 CASE 
  WHEN [InheritanceType] = 14
   THEN 1
  ELSE 0
  END
 , [is_StringAggAllSources] =
 --
 CASE 
  WHEN NOT [Inheritance_StringAggSeparatorSql] IS NULL
   THEN 1
  ELSE 0
  END
 , [Inheritance_StringAggSeparatorSql]
 , [resulting_InheritanceDefinition] =
 --
 CASE 
  WHEN (
    [InheritanceType] = 11
    AND [inh].[property_value] IS NULL
    )
   OR (
    [InheritanceType] = 12
    AND NULLIF([inh].[property_value], '') IS NULL
    )
   OR [InheritanceType] = 13
   OR [InheritanceType] = 14
   THEN ISNULL([InheritanceDefinition], '[repo].[fs_get_RepoObjectProperty_nvarchar]([referenced].[RepoObject_guid], [referencing].[property_name])')
  END
 --normally the result from [resulting_InheritanceDefinition] should not be empty to be inherited
 --this will avoid existing property_value to be deleted
 --but inheritance can be forced (dangerous!)
 , [inh].[InheritanceDefinition]
 , [inh].[RepoObject_fullname]
 , inh.RepoObject_type
FROM [repo].[RepoObject_InheritanceType_InheritanceDefinition] AS inh

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_persistence_column

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| target_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObjectColumn_guid_s | UNIQUEIDENTIFIER | yes |  |
| SysObject_schema_name_s | NVARCHAR(128) | yes |  |
| SysObject_name_s | NVARCHAR(128) | yes |  |
| SysObjectColumn_name_s | NVARCHAR(128) | yes |  |
| SysObject_type_s | CHAR(2) | yes |  |
| RepoObject_schema_name_t | NVARCHAR(128) | no |  |
| RepoObject_name_t | NVARCHAR(128) | no |  |
| RepoObjectColumn_name_t | NVARCHAR(128) | yes |  |
| RepoObject_type_t | CHAR(2) | no |  |
| is_repo_managed_t | BIT | yes |  |
| is_persistence_truncate | BIT | no |  |
| is_persistence_delete_missing | BIT | no |  |
| is_persistence_delete_changed | BIT | no |  |
| is_persistence_update_changed | BIT | no |  |
| is_persistence_insert | BIT | no |  |
| has_history | BIT | no |  |
| has_history_columns | BIT | no |  |
| is_persistence_check_for_empty_source | BIT | no |  |
| history_schema_name | NVARCHAR(128) | yes |  |
| history_table_name | NVARCHAR(128) | yes |  |
| is_persistence | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
wofür soll diese Sicht verwendet werden?
noch nicht fertig
*/
CREATE VIEW [repo].[RepoObject_persistence_column]
AS
--
SELECT [rop].[target_RepoObject_guid]
 , [rop].[source_RepoObject_guid]
 , [roc_s].[RepoObjectColumn_guid] AS [RepoObjectColumn_guid_s]
 , [ro_s].[SysObject_schema_name] AS [SysObject_schema_name_s]
 , [ro_s].[SysObject_name] AS [SysObject_name_s]
 , [roc_s].[SysObjectColumn_name] AS [SysObjectColumn_name_s]
 , [ro_s].[SysObject_type] AS [SysObject_type_s]
 , [ro_t].[RepoObject_schema_name] AS [RepoObject_schema_name_t]
 , [ro_t].[RepoObject_name] AS [RepoObject_name_t]
 , [roc_t].[RepoObjectColumn_name] AS [RepoObjectColumn_name_t]
 , [ro_t].[RepoObject_type] AS [RepoObject_type_t]
 , [ro_t].[is_repo_managed] AS [is_repo_managed_t]
 , [rop].[is_persistence_truncate]
 , [rop].[is_persistence_delete_missing]
 , [rop].[is_persistence_delete_changed]
 , [rop].[is_persistence_update_changed]
 , [rop].[is_persistence_insert]
 , [rop].has_history AS has_history
 , [rop].has_history_columns AS has_history_columns
 , [rop].[is_persistence_check_for_empty_source]
 , [rop].[history_schema_name]
 , [rop].[history_table_name]
 , [rop].[is_persistence]
--       --, [roc_s].[RepoObject_guid]
--       --, [roc_s].[RepoObjectColumn_name]
--       --, [roc_s].[SysObjectColumn_column_id]
--       --, [roc_s].[is_SysObjectColumn_missing]
--       --, [roc_s].[Source_PersistenceColumn_guid]
--     , [roc_s].[Target_PersistenceColumn_guid] AS [Target_PersistenceColumn_guid_s]
--     , [roc_s].[is_force_persistence] AS          [is_force_persistence_s]
--     , [roc_s].[is_force_persistence_name] AS     [is_force_persistence_name_s]
--       --, [roc_s].[persistence_source_RepoObjectColumn_guid]
--       --, [roc_s].[Referencing_Count]
--       --, [roc_s].[has_different_sys_names]
--       --, [roc_s].[is_RepoObjectColumn_name_uniqueidentifier]
--       --, [roc_s].[is_SysObjectColumn_name_uniqueidentifier]
--       --, [roc_t].[RepoObjectColumn_guid]
--       --, [roc_t].[RepoObject_guid]
--       --, [roc_t].[SysObjectColumn_name]
--       --, [roc_t].[SysObjectColumn_column_id]
--       --, [roc_t].[is_SysObjectColumn_missing]
--       --, [roc_t].[Target_PersistenceColumn_guid]
--     , [roc_t].[is_force_persistence] AS          [is_force_persistence_t]
--     , [roc_t].[is_force_persistence_name] AS     [is_force_persistence_name_t]
----, [roc_t].[persistence_source_RepoObjectColumn_guid]
----, [roc_t].[Referencing_Count]
----, [roc_t].[has_different_sys_names]
----, [roc_t].[is_RepoObjectColumn_name_uniqueidentifier]
----, [roc_t].[is_SysObjectColumn_name_uniqueidentifier]
FROM repo.RepoObject_persistence AS rop
INNER JOIN repo.RepoObject AS ro_t
 ON rop.target_RepoObject_guid = ro_t.RepoObject_guid
LEFT OUTER JOIN repo.RepoObject AS ro_s
 ON rop.source_RepoObject_guid = ro_s.RepoObject_guid
LEFT OUTER JOIN repo.RepoObjectColumn AS roc_s
 ON rop.source_RepoObject_guid = roc_s.RepoObject_guid
LEFT JOIN repo.RepoObjectColumn AS roc_t
 ON roc_t.RepoObject_guid = rop.target_RepoObject_guid
  AND roc_t.[persistence_source_RepoObjectColumn_guid] = roc_s.RepoObjectColumn_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_persistence_ForInput

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| target_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| target_RepoObject_fullname | NVARCHAR(261) | no |  |
| has_history | BIT | no |  |
| has_history_columns | BIT | no |  |
| history_schema_name | NVARCHAR(128) | yes |  |
| history_table_name | NVARCHAR(128) | yes |  |
| is_persistence_check_duplicate_per_pk | BIT | no |  |
| is_persistence_check_for_empty_source | BIT | no |  |
| is_persistence_delete_changed | BIT | no |  |
| is_persistence_delete_missing | BIT | no |  |
| is_persistence_insert | BIT | no |  |
| is_persistence_truncate | BIT | no |  |
| is_persistence_update_changed | BIT | no |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| is_persistence | BIT | yes |  |
| temporal_type | TINYINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
Added some lookup columns [repo].[RepoObject_persistence]
to simplify data entry in the frontend
*/
CREATE VIEW [repo].[RepoObject_persistence_ForInput]
AS
SELECT [ro_p].[target_RepoObject_guid]
 , [ro].[RepoObject_fullname] AS [target_RepoObject_fullname]
 , [ro_p].[has_history]
 , [ro_p].[has_history_columns]
 , [ro_p].[history_schema_name]
 , [ro_p].[history_table_name]
 , [ro_p].[is_persistence_check_duplicate_per_pk]
 , [ro_p].[is_persistence_check_for_empty_source]
 , [ro_p].[is_persistence_delete_changed]
 , [ro_p].[is_persistence_delete_missing]
 , [ro_p].[is_persistence_insert]
 , [ro_p].[is_persistence_truncate]
 , [ro_p].[is_persistence_update_changed]
 , [ro_p].[source_RepoObject_guid]
 , [ro_p].[is_persistence]
 , [ro_p].[temporal_type]
FROM [repo].[RepoObject_persistence] AS ro_p
INNER JOIN [repo].[RepoObject] AS ro
 ON ro.RepoObject_guid = ro_p.target_RepoObject_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_persistence_ObjectNames

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| target_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_schema_name_s | NVARCHAR(128) | yes |  |
| SysObject_name_s | NVARCHAR(128) | yes |  |
| SysObject_type_s | CHAR(2) | yes |  |
| RepoObject_schema_name_t | NVARCHAR(128) | no |  |
| RepoObject_name_t | NVARCHAR(128) | no |  |
| RepoObject_type_t | CHAR(2) | no |  |
| is_repo_managed_t | BIT | yes |  |
| is_persistence_truncate | BIT | no |  |
| is_persistence_delete_missing | BIT | no |  |
| is_persistence_delete_changed | BIT | no |  |
| is_persistence_update_changed | BIT | no |  |
| is_persistence_insert | BIT | no |  |
| has_history | BIT | no |  |
| has_history_columns | BIT | no |  |
| is_persistence_check_for_empty_source | BIT | no |  |
| history_schema_name | NVARCHAR(128) | yes |  |
| history_table_name | NVARCHAR(128) | yes |  |
| is_persistence | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
Source - Sys names will be used
to create
Target - Repo names (because a persistence is per definition defined as 

if ro_s columns are empty, then the entry in [rop].[source_RepoObject_guid] is wrong and should be corrected or the entry should be deleted

SELECT
       *
FROM
     repo.RepoObject_persistence_ObjectNames AS T1
WHERE  [T1].[SysObject_name_s] IS NULL

*/
CREATE VIEW [repo].[RepoObject_persistence_ObjectNames]
AS
--
SELECT [rop].[target_RepoObject_guid]
 , [rop].[source_RepoObject_guid]
 , [ro_s].[SysObject_schema_name] AS [SysObject_schema_name_s]
 , [ro_s].[SysObject_name] AS [SysObject_name_s]
 , [ro_s].[SysObject_type] AS [SysObject_type_s]
 , [ro_t].[RepoObject_schema_name] AS [RepoObject_schema_name_t]
 , [ro_t].[RepoObject_name] AS [RepoObject_name_t]
 , [ro_t].[RepoObject_type] AS [RepoObject_type_t]
 , [ro_t].[is_repo_managed] AS [is_repo_managed_t]
 , [rop].[is_persistence_truncate]
 , [rop].[is_persistence_delete_missing]
 , [rop].[is_persistence_delete_changed]
 , [rop].[is_persistence_update_changed]
 , [rop].[is_persistence_insert]
 , [rop].[has_history]
 , [rop].[has_history_columns]
 , [rop].[is_persistence_check_for_empty_source]
 , [rop].[history_schema_name]
 , [rop].[history_table_name]
 , [rop].[is_persistence]
FROM repo.RepoObject_persistence AS rop
INNER JOIN repo.RepoObject AS ro_t
 ON rop.target_RepoObject_guid = ro_t.RepoObject_guid
LEFT OUTER JOIN repo.RepoObject AS ro_s
 ON rop.source_RepoObject_guid = ro_s.RepoObject_guid
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_reference_persistence

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referenced_entity_name | NVARCHAR(128) | no |  |
| referenced_fullname | NVARCHAR(261) | no |  |
| referenced_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referenced_schema_name | NVARCHAR(128) | no |  |
| referenced_type | CHAR(2) | yes |  |
| referencing_entity_name | NVARCHAR(128) | no |  |
| referencing_fullname | NVARCHAR(261) | no |  |
| referencing_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referencing_schema_name | NVARCHAR(128) | no |  |
| referencing_type | VARCHAR(2) | yes |  |
| InformationSource | VARCHAR(27) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_reference_persistence]
AS
--
SELECT
 --
 [referenced_RepoObject_guid] = [rop].[source_RepoObject_guid]
 , [referencing_RepoObject_guid] = [rop].[target_RepoObject_guid]
 , [referenced_entity_name] = [ro_s].[SysObject_name]
 , [referenced_fullname] = [ro_s].[RepoObject_fullname]
 , [referenced_id] = [ro_s].[SysObject_id]
 , [referenced_node_id] = [ro_s].[node_id]
 , [referenced_schema_name] = [ro_s].[SysObject_schema_name]
 , [referenced_type] = [ro_s].[SysObject_type]
 , [referencing_entity_name] = [ro_t].[SysObject_name]
 , [referencing_fullname] = [ro_t].[RepoObject_fullname]
 , [referencing_id] = [ro_t].[SysObject_id]
 , [referencing_node_id] = [ro_t].[node_id]
 , [referencing_schema_name] = [ro_t].[SysObject_schema_name]
 , [referencing_type] = COALESCE([ro_t].[SysObject_type], [ro_t].[RepoObject_type], 'U')
 , [InformationSource] = 'repo.RepoObject_persistence'
FROM repo.RepoObject_persistence AS rop
INNER JOIN repo.RepoObject AS ro_t
 ON ro_t.RepoObject_guid = rop.target_RepoObject_guid
INNER JOIN repo.RepoObject AS ro_s
 ON ro_s.RepoObject_guid = rop.source_RepoObject_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_reference_SqlExpressionDependencies

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referenced_id | INT | yes |  |
| referencing_id | INT | no |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_fullname | NVARCHAR(517) | no |  |
| referenced_node_id | BIGINT | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| referencing_entity_name | NVARCHAR(128) | yes |  |
| referencing_fullname | NVARCHAR(517) | no |  |
| referencing_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_schema_name | NVARCHAR(128) | yes |  |
| referencing_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(31) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_reference_SqlExpressionDependencies]
AS
--
SELECT
 --
 [sed].[referenced_id]
 , [sed].[referencing_id]
 --, [sed].[referencing_minor_id]
 , [sed].[referenced_entity_name]
 , [referenced_fullname] = CONCAT (
  QUOTENAME([sed].[referenced_schema_name])
  , '.'
  , QUOTENAME([sed].[referenced_entity_name])
  )
 --, [sed].[referenced_minor_id]
 , CAST([sed].[referenced_id] AS BIGINT) * 10000 AS [referenced_node_id]
 , [sed].[referenced_RepoObject_guid]
 , [sed].[referenced_schema_name]
 , [sed].[referenced_type]
 --, [sed].[referenced_column_name]
 --, [sed].[referenced_RepoObjectColumn_guid]
 , [sed].[referencing_entity_name]
 , [referencing_fullname] = CONCAT (
  QUOTENAME([sed].[referencing_schema_name])
  , '.'
  , QUOTENAME([sed].[referencing_entity_name])
  )
 , CAST([sed].[referencing_id] AS BIGINT) * 10000 AS [referencing_node_id]
 , [sed].[referencing_RepoObject_guid]
 , [sed].[referencing_schema_name]
 , [sed].[referencing_type]
 --, [sed].[referencing_RepoObjectColumn_guid]
 --, [sed].[referencing_column_name]
 , [InformationSource] = 'sys.sql_expression_dependencies'
--, [sed].[referenced_server_name]
--, [sed].[referenced_database_name]
--, [sed].[referenced_class]
--, [sed].[referencing_class]
--, [sed].[referencing_class_desc]
--, [sed].[referenced_class_desc]
--, [sed].[referencing_type_desciption]
--, [sed].[referenced_type_desciption]
--, [sed].[is_schema_bound_reference]
--, [sed].[is_caller_dependent]
--, [sed].[is_ambiguous]
FROM repo_sys.sql_expression_dependencies AS sed
WHERE
 --object level
 [sed].[referencing_minor_id] = 0
 AND [sed].[referenced_minor_id] = 0
 --exclude virtual objects (like expressions used in procedures)
 --or objects without extended properties (like triggers)
 --currently:
 --[RepoObject_guid] = [sed].[referencing_RepoObject_guid]
 --and [sed].[referencing_RepoObject_guid] = SysObject_RepoObject_guid
 --these are RepoObject_guid storred in extended properties
 AND NOT [sed].[referencing_RepoObject_guid] IS NULL
 AND NOT [sed].[referenced_RepoObject_guid] IS NULL

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_reference_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_fullname | NVARCHAR(517) | no |  |
| referenced_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| referencing_entity_name | NVARCHAR(128) | yes |  |
| referencing_fullname | NVARCHAR(517) | no |  |
| referencing_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referencing_schema_name | NVARCHAR(128) | yes |  |
| referencing_type | VARCHAR(2) | yes |  |
| InformationSource | VARCHAR(31) | no |  |
| one | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_reference_union]
AS
--
SELECT
 --
 [T1].[referenced_RepoObject_guid]
 , [T1].[referencing_RepoObject_guid]
 , [T1].[referenced_entity_name]
 , [T1].[referenced_fullname]
 , [T1].[referenced_id]
 , [T1].[referenced_node_id]
 , [T1].[referenced_schema_name]
 , [T1].[referenced_type]
 , [T1].[referencing_entity_name]
 , [T1].[referencing_fullname]
 , [T1].[referencing_id]
 , [T1].[referencing_node_id]
 , [T1].[referencing_schema_name]
 , [T1].[referencing_type]
 , [T1].[InformationSource]
 , one = 1
FROM repo.[RepoObject_reference_SqlExpressionDependencies] AS T1

UNION ALL

SELECT
 --
 [T1].[referenced_RepoObject_guid]
 , [T1].[referencing_RepoObject_guid]
 , [T1].[referenced_entity_name]
 , [T1].[referenced_fullname]
 , [T1].[referenced_id]
 , [T1].[referenced_node_id]
 , [T1].[referenced_schema_name]
 , [T1].[referenced_type]
 , [T1].[referencing_entity_name]
 , [T1].[referencing_fullname]
 , [T1].[referencing_id]
 , [T1].[referencing_node_id]
 , [T1].[referencing_schema_name]
 , [T1].[referencing_type]
 , [T1].[InformationSource]
 , one = 1
FROM repo.[RepoObject_reference_persistence] AS T1

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_reference_union_node_id

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_node_id | NVARCHAR(1000) | no |  |
| referenced_node_id | NVARCHAR(1000) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
kann nicht mit VS database project synchronisiert werden, bug im SchemaCompare oder VS wegen "ro_2.$NODE_ID" usw.
*/

CREATE VIEW [repo].[RepoObject_reference_union_node_id]
AS
SELECT DISTINCT [referencing_RepoObject_guid]
 , [referenced_RepoObject_guid]
 , referencing_node_id = ro_2.$NODE_ID
 , referenced_node_id = ro_1.$NODE_ID
FROM [repo].[RepoObject_reference_union] ro_ref
JOIN [graph].[RepoObject] ro_1
 ON ro_1.[RepoObject_guid] = ro_ref.[referenced_RepoObject_guid]
JOIN [graph].[RepoObject] ro_2
 ON ro_2.[RepoObject_guid] = ro_ref.[referencing_RepoObject_guid]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_ReferenceTree

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Referencing_fullname | NVARCHAR(261) | yes |  |
| Referencing_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_type | CHAR(2) | yes |  |
| Referenced_fullname | NVARCHAR(261) | yes |  |
| Referenced_guid | UNIQUEIDENTIFIER | yes |  |
| Referenced_type | CHAR(2) | yes |  |
| Referenced_Depth | INT | yes |  |
| Referencing_Depth | INT | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_ReferenceTree]
AS
SELECT [tree].*
FROM [repo].[RepoObject_gross] AS ro
CROSS APPLY [repo].[ftv_RepoObject_ReferenceTree](ro.[RepoObject_guid], 1000, 1000) AS tree
WHERE [ro].[is_in_reference] = 1

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_RequiredRepoObjectMerge

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| ro2_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| ro2_RepoObject_fullname | NVARCHAR(261) | no |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| ro2_SysObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_name | NVARCHAR(128) | no |  |
| RepoObject_schema_name | NVARCHAR(128) | no |  |
| SysObject_name | NVARCHAR(128) | no |  |
| SysObject_schema_name | NVARCHAR(128) | no |  |
| ro2_RepoObject_name | NVARCHAR(128) | no |  |
| ro2_RepoObject_schema_name | NVARCHAR(128) | no |  |
| ro2_SysObject_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
mismatch of RepoObject_guid can create 2 entries per one RepoObject
this can happen, if the guid exists in the database extended properties and a new guid will be created in the repo
ro1 has the right RepoObject_fullname, but the guid was new created
ro2 got the "right" guid from database, but ro2 can't propagate the fullname into RepoObject because the RepoObject_fullname is occupied
now we have 2 entries, but we need to merge them

we need to replace 
ro1.RepoObject_guid by ro2.RepoObject_guid


first we check where the RepoObject PK is used in FK

--Returns logical foreign key information
EXEC sp_fkeys @pktable_name = N'RepoObject'
 , @pktable_owner = N'repo';

we should care about

repo	RepoObject_persistence	target_RepoObject_guid
repo	ProcedureInstance	Procedure_RepoObject_guid

we will not care about

repo	Index_virtual	parent_RepoObject_guid
repo	RepoObject_SqlModules	RepoObject_guid
repo	RepoObjectColumn	RepoObject_guid
repo	RepoObjectProperty	RepoObject_guid
repo	RepoObjectSource_FirstResultSet	RepoObject_guid
repo	RepoObjectSource_QueryPlan	RepoObject_guid

*/
--list of conflicting entries which needs to be merged
Create VIEW repo.RepoObject_RequiredRepoObjectMerge
AS
SELECT
 --
 ro1.RepoObject_guid
 , ro2.RepoObject_guid AS ro2_RepoObject_guid
 , ro1.RepoObject_fullname
 , ro2.RepoObject_fullname AS ro2_RepoObject_fullname
 , ro1.SysObject_fullname
 , ro2.SysObject_fullname AS ro2_SysObject_fullname
 , ro1.RepoObject_name
 , ro1.RepoObject_schema_name
 , ro1.SysObject_name
 , ro1.SysObject_schema_name
 , ro2.RepoObject_name AS ro2_RepoObject_name
 , ro2.RepoObject_schema_name AS ro2_RepoObject_schema_name
 , ro2.SysObject_name AS ro2_SysObject_name
FROM repo.RepoObject AS ro1
INNER JOIN repo.RepoObject AS ro2
 ON ro2.SysObject_fullname = ro1.RepoObject_fullname
  AND ro2.RepoObject_guid <> ro1.RepoObject_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlCreateTable

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| DbmlTable | NVARCHAR(MAX) | no |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| SqlCreateTable | NVARCHAR(MAX) | no |  |
| ConList | NVARCHAR(MAX) | yes |  |
| persistence_source_RepoObject_fullname | NVARCHAR(261) | yes |  |
| persistence_source_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| persistence_source_SysObject_fullname | NVARCHAR(261) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlCreateTable]
AS
SELECT ro.[RepoObject_guid]
 , DbmlTable = CONCAT (
  'Table '
  , QUOTENAME(ro.RepoObject_fullname, '"')
  , '{'
  , CHAR(13)
  , CHAR(10)
  , ColList.DbmlColumnList
  --note: 'string to add notes'
  , CASE 
   WHEN NOT ro.Property_ms_description IS NULL
    THEN CHAR(13) + CHAR(10) + 'Note: ''''''' + CHAR(13) + CHAR(10) + REPLACE(REPLACE(ro.Property_ms_description, '\', '\\'), '''''''', '\''''''') + CHAR(13) + CHAR(10) + ''''''''
   END
  --optional Settings [setting1: value1, setting2: value2, setting3, setting4]
  , CHAR(13)
  , CHAR(10)
  , CASE 
   WHEN NOT IndexList.DbmlIndexList IS NULL
    THEN CHAR(13) + CHAR(10) + 'indexes {' + CHAR(13) + CHAR(10) + IndexList.DbmlIndexList + CHAR(13) + CHAR(10) + '}' + CHAR(13) + CHAR(10)
   END
  , '}'
  , CHAR(13)
  , CHAR(10)
  )
 , ro.RepoObject_fullname
 , SqlCreateTable = CONCAT (
  'CREATE TABLE '
  , ro.[RepoObject_fullname]
  , ' ('
  , CHAR(13)
  , CHAR(10)
  , ColList.CreateColumnList
  --todo:
  --evtl noch ein Komma
  , CASE 
   WHEN EXISTS (
     SELECT 1
     FROM [repo].[Index_SqlConstraint_PkUq] ConList
     WHERE ConList.[parent_RepoObject_guid] = ro.[RepoObject_guid]
     )
    THEN ','
   END
  --CONSTRAINT PK, FK, depending on some settings
  , ConList.ConList
  --PERIOD FOR SYSTEM_TIME ([ValidFrom], [ValidTo])
  , CASE 
   WHEN EXISTS (
     SELECT 1
     FROM [repo].[RepoObjectColumn] roc
     WHERE roc.RepoObject_guid = ro.RepoObject_guid
      AND roc.[Repo_generated_always_type] = 1
     )
    AND EXISTS (
     SELECT 1
     FROM [repo].[RepoObjectColumn] roc
     WHERE roc.RepoObject_guid = ro.RepoObject_guid
      AND roc.[Repo_generated_always_type] = 2
     )
    THEN CONCAT (
      ', PERIOD FOR SYSTEM_TIME ('
      , QUOTENAME((
        SELECT [RepoObjectColumn_name]
        FROM [repo].[RepoObjectColumn] roc
        WHERE roc.RepoObject_guid = ro.RepoObject_guid
         AND roc.[Repo_generated_always_type] = 1
        ))
      , ', '
      , QUOTENAME((
        SELECT [RepoObjectColumn_name]
        FROM [repo].[RepoObjectColumn] roc
        WHERE roc.RepoObject_guid = ro.RepoObject_guid
         AND roc.[Repo_generated_always_type] = 2
        ))
      , ')'
      , CHAR(13)
      , CHAR(10)
      )
   END
  , ')'
  --WITH
  --(
  --SYSTEM_VERSIONING = ON ( HISTORY_TABLE = [Application].[Cities_Archive] )
  --)
  , CASE ro.[Repo_temporal_type]
   WHEN 2
    THEN CONCAT (
      CHAR(13)
      , CHAR(10)
      , 'WITH'
      , CHAR(13)
      , CHAR(10)
      , '('
      , CHAR(13)
      , CHAR(10)
      , 'SYSTEM_VERSIONING = ON ( HISTORY_TABLE = '
      --, '[Application].[Cities_Archive]'
      , COALESCE(ro_hist.[RepoObject_fullname], CONCAT (
        QUOTENAME(ISNULL(CAST([repo].[fs_get_parameter_value]('Hist_Table_schema', DEFAULT) AS NVARCHAR(128)), ro.[RepoObject_schema_name]))
        , '.'
        , QUOTENAME(CONCAT (
          ro.[RepoObject_name]
          , CAST([repo].[fs_get_parameter_value]('Hist_Table_name_suffix', DEFAULT) AS NVARCHAR(128))
          ))
        ))
      , ' )'
      , CHAR(13)
      , CHAR(10)
      , ')'
      , CHAR(13)
      , CHAR(10)
      )
   END
  )
 --ConstraintList
 , ConList.ConList
 , ro.persistence_source_RepoObject_fullname
 , ro.persistence_source_RepoObject_guid
 , ro.persistence_source_SysObject_fullname
FROM repo.[RepoObject_gross] ro
--column list should exist, otherwise CREATE statement will be invalid
INNER JOIN [repo].[RepoObject_ColumnList] AS ColList
 ON ColList.[RepoObject_guid] = ro.[RepoObject_guid]
LEFT JOIN (
 SELECT [parent_RepoObject_guid]
  , ConList = STRING_AGG(CONCAT (
    --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
    CAST(' ' AS NVARCHAR(MAX))
    , con.[SqlConstraint]
    , CHAR(13)
    , CHAR(10)
    ), ',')
 FROM [repo].[Index_SqlConstraint_PkUq] Con
 GROUP BY [parent_RepoObject_guid]
 ) ConList
 ON ConList.[parent_RepoObject_guid] = ro.[RepoObject_guid]
LEFT JOIN (
 SELECT [parent_RepoObject_guid]
  , DbmlIndexList = STRING_AGG(CONCAT (
    --we need to convert to first argument nvarchar(max) to avoid the limit of 8000 byte
    CAST(' ' AS NVARCHAR(MAX))
    , '('
    , i.[DbmlIndexColumnList]
    , ') '
    , '['
    , CASE 
     --this doesn't work. but we define pk in DbmlColumnList
     WHEN i.[is_index_primary_key] = 1
      THEN 'pk'
     WHEN i.[is_index_unique] = 1
      THEN 'unique'
     ELSE 'name:''' + [index_name] + ''''
     END
    , ']'
    ), CHAR(13) + CHAR(10)) WITHIN
 GROUP (
   ORDER BY i.[RowNumber_PkPerParentObject]
   )
 FROM [repo].[Index_gross] i
 WHERE i.[is_index_primary_key] = 0
  AND (
   i.is_index_unique = 1
   OR i.is_index_real = 1
   )
 GROUP BY [parent_RepoObject_guid]
 ) IndexList
 ON IndexList.[parent_RepoObject_guid] = ro.[RepoObject_guid]
LEFT JOIN repo.RepoObject ro_hist
 ON ro_hist.RepoObject_guid = ro.Repo_history_table_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_10_statement

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| sql_modules_json | NVARCHAR(MAX) | yes |  |
| class | NVARCHAR(500) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*extract class Statement, it should be the one and only node on first level*/
CREATE VIEW [repo].[RepoObject_SqlModules_10_statement]
AS
--
SELECT [T1].[RepoObject_guid]
 , [ro].[SysObject_fullname]
 , [T1].[sql_modules_json]
 , [j2].*
FROM [repo].[RepoObject_SqlModules] AS T1
CROSS APPLY OPENJSON(T1.[sql_modules_json]) WITH (
  class NVARCHAR(500) N'$.class'
  , is_group BIT N'$.is_group'
  , is_keyword BIT N'$.is_keyword'
  , is_whitespace BIT N'$.is_whitespace'
  , normalized NVARCHAR(MAX) N'$.normalized'
  , children NVARCHAR(MAX) N'$.children' AS JSON
  ) AS j2
LEFT JOIN [repo].[RepoObject] AS ro
 ON ro.[RepoObject_guid] = T1.[RepoObject_guid]
WHERE [T1].[is_json_sql_modules_json] = 1
 AND [j2].[class] = 'Statement'
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_20_statement_children

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |
| child0_class | NVARCHAR(500) | yes |  |
| child0_is_group | BIT | yes |  |
| child0_is_keyword | BIT | yes |  |
| child0_is_whitespace | BIT | yes |  |
| child0_normalized | NVARCHAR(MAX) | yes |  |
| child0_children | NVARCHAR(MAX) | yes |  |
| child1_class | NVARCHAR(500) | yes |  |
| child1_is_group | BIT | yes |  |
| child1_is_keyword | BIT | yes |  |
| child1_is_whitespace | BIT | yes |  |
| child1_normalized | NVARCHAR(MAX) | yes |  |
| child1_children | NVARCHAR(MAX) | yes |  |
| child2_class | NVARCHAR(500) | yes |  |
| child2_is_group | BIT | yes |  |
| child2_is_keyword | BIT | yes |  |
| child2_is_whitespace | BIT | yes |  |
| child2_normalized | NVARCHAR(MAX) | yes |  |
| child2_children | NVARCHAR(MAX) | yes |  |
| child3_class | NVARCHAR(500) | yes |  |
| child3_is_group | BIT | yes |  |
| child3_is_keyword | BIT | yes |  |
| child3_is_whitespace | BIT | yes |  |
| child3_normalized | NVARCHAR(MAX) | yes |  |
| child3_children | NVARCHAR(MAX) | yes |  |
| child4_class | NVARCHAR(500) | yes |  |
| child4_is_group | BIT | yes |  |
| child4_is_keyword | BIT | yes |  |
| child4_is_whitespace | BIT | yes |  |
| child4_normalized | NVARCHAR(MAX) | yes |  |
| child4_children | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
Assuming that a statement has only one child, this one child is decomposed into its components here.

In the next step the reiehenfolge can be checked
For example
- CREATE
- VIEW
- (identifier)
- AS
- SELECT

It can be checked if there are other components between SELECT and IdentifierList, like DISTINCT
- SELECT
- optional ... (DISTINCT, TOP xyz, ...)
- IdentifierList
- FROM

- FROM
- ...
- WHERE / HAVING

and so on

----old sql:
--SELECT [T1].[RepoObject_guid]
-- --we need the key for ROW_NUMBER
-- --key is an int in this case, maybe because the json is an array
-- , [j1].[key]
-- , [T1].[SysObject_fullname]
-- --a statement should have only one child
-- --if this is not the case we need to include into ROW_NUMBER()
-- --, T1.[children]
-- , [RowNumber_per_Object] = ROW_NUMBER() OVER (
--  PARTITION BY [T1].[RepoObject_guid] ORDER BY TRY_CAST([j1].[key] AS INT)
--  )
-- --, j1.[value]
-- --, j1.[type]
-- , [j2].*
--FROM [repo].[RepoObject_SqlModules_10_statement] AS T1
--CROSS APPLY OPENJSON(T1.[children]) AS j1
--CROSS APPLY OPENJSON(j1.[value]) WITH (
--  class NVARCHAR(500) N'$.class'
--  , is_group BIT N'$.is_group'
--  , is_keyword BIT N'$.is_keyword'
--  , is_whitespace BIT N'$.is_whitespace'
--  , normalized NVARCHAR(MAX) N'$.normalized'
--  , children NVARCHAR(MAX) N'$.children' AS JSON
--  ) AS j2


*/
CREATE VIEW [repo].[RepoObject_SqlModules_20_statement_children]
AS
--
SELECT [T1].[RepoObject_guid]
 --we need the key for ROW_NUMBER
 --key is an int in this case, maybe because the json is an array
 , [T2].[json_key]
 , [T1].[SysObject_fullname]
 --a statement should have only one child
 --if this is not the case we need to include into ROW_NUMBER()
 --, T1.[children]
 , [RowNumber_per_Object] = ROW_NUMBER() OVER (
  PARTITION BY [T1].[RepoObject_guid] ORDER BY TRY_CAST([T2].[json_key] AS INT)
  )
 , [T2].[class]
 , [T2].[is_group]
 , [T2].[is_keyword]
 , [T2].[is_whitespace]
 , [T2].[normalized]
 , [T2].[children]
 , [T2].[child0_class]
 , [T2].[child0_is_group]
 , [T2].[child0_is_keyword]
 , [T2].[child0_is_whitespace]
 , [T2].[child0_normalized]
 , [T2].[child0_children]
 , [T2].[child1_class]
 , [T2].[child1_is_group]
 , [T2].[child1_is_keyword]
 , [T2].[child1_is_whitespace]
 , [T2].[child1_normalized]
 , [T2].[child1_children]
 , [T2].[child2_class]
 , [T2].[child2_is_group]
 , [T2].[child2_is_keyword]
 , [T2].[child2_is_whitespace]
 , [T2].[child2_normalized]
 , [T2].[child2_children]
 , [T2].[child3_class]
 , [T2].[child3_is_group]
 , [T2].[child3_is_keyword]
 , [T2].[child3_is_whitespace]
 , [T2].[child3_normalized]
 , [T2].[child3_children]
 , [T2].[child4_class]
 , [T2].[child4_is_group]
 , [T2].[child4_is_keyword]
 , [T2].[child4_is_whitespace]
 , [T2].[child4_normalized]
 , [T2].[child4_children]
FROM [repo].[RepoObject_SqlModules_10_statement] AS T1
CROSS APPLY [repo].[ftv_sqlparse_with_some_children](T1.children) AS T2
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_21_statement_children_helper

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |
| is_1_create | INT | no |  |
| is_2_view | INT | no |  |
| is_3_Identifier | INT | no |  |
| is_4_as | INT | no |  |
| is_5_select | INT | no |  |
| is_6_Identifier | INT | no |  |
| is_6_IdentifierList | INT | no |  |
| is_7_from | INT | no |  |
| is_7_IdentifierList | INT | no |  |
| is_8_IdentifierList | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*helpers are required in next steps to check several conditions
here we prepare the check if the parsed statement will follow some required logic, for example
CREATE;VIEW;Identifier;AS;SELECT;IdentifierList;FROM
*/
CREATE VIEW [repo].[RepoObject_SqlModules_21_statement_children_helper]
AS
--
SELECT [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [T1].[RowNumber_per_Object]
 , [T1].[class]
 , [T1].[is_group]
 , [T1].[is_keyword]
 , [T1].[is_whitespace]
 , [T1].[normalized]
 , [T1].[children]
 --the entry 1 in the parsed sql is 'CREATE'
 , is_1_create = IIF([RowNumber_per_Object] = 1
  AND [normalized] = 'CREATE', 1, 0)
 --the entry 2 in the parsed sql is 'VIEW'
 , is_2_view = IIF([RowNumber_per_Object] = 2
  AND [normalized] = 'VIEW', 1, 0)
 , is_3_Identifier = IIF([RowNumber_per_Object] = 3
  AND [class] = 'Identifier', 1, 0)
 , is_4_as = IIF([RowNumber_per_Object] = 4
  AND [normalized] = 'AS', 1, 0)
 , is_5_select = IIF([RowNumber_per_Object] = 5
  AND [normalized] = 'SELECT', 1, 0)
 , is_6_Identifier = IIF([RowNumber_per_Object] = 6
  AND [class] = 'Identifier', 1, 0)
 , is_6_IdentifierList = IIF([RowNumber_per_Object] = 6
  AND [class] = 'IdentifierList', 1, 0)
 , is_7_from = IIF([RowNumber_per_Object] = 7
  AND [normalized] = 'FROM', 1, 0)
 , is_7_IdentifierList = IIF([RowNumber_per_Object] = 7
  AND [class] = 'IdentifierList', 1, 0)
 , is_8_IdentifierList = IIF([RowNumber_per_Object] = 8
  AND [class] = 'IdentifierList', 1, 0)
FROM [repo].[RepoObject_SqlModules_20_statement_children] T1
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_22_identifier_alias_AS

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| identifier_name | NVARCHAR(MAX) | yes |  |
| identifier_alias | NVARCHAR(MAX) | yes |  |
| RowNumber | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
this works good for identifier, used in the FROM block of a statement:
it looks like these identifiers have only one child and inside this one child only one child identifier which is the alias
we also add a Row_number to enable filtering for the first alias (there should only be one, but who knows...)
by filtering ([RowNumber] = 1) in some next steps we ensure one entry per ([RepoObject_guid], [key])

But we have also a lot of other representations of tables, especially because of the (NOLOCK)
and we need some extra handling to extract them
*/
CREATE VIEW [repo].[RepoObject_SqlModules_22_identifier_alias_AS]
AS
--
SELECT [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [identifier_name] = [T1].[normalized]
 , [identifier_alias] = [T2].[normalized]
 , [RowNumber] = ROW_NUMBER() OVER (
  PARTITION BY [T1].[RepoObject_guid]
  , [T1].[json_key] ORDER BY [T2].[json_key]
  )
FROM repo.[RepoObject_SqlModules_20_statement_children] AS T1
CROSS APPLY [repo].[ftv_sqlparse]([T1].[children]) AS T2
WHERE [T1].[class] = 'Identifier'
 AND [T2].[class] = 'Identifier'
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_23_normalized_wo_nolock

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| normalized_wo_nolock | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
resolve Function 'T1 (NOLOCK)'
=> normalized_wo_nolock = 'T1'

(NOLOCK) needs to be extracted from children
*/
CREATE VIEW [repo].[RepoObject_SqlModules_23_normalized_wo_nolock]
AS
--
SELECT [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [T1].[normalized]
 , [normalized_wo_nolock] = [T2].[child0_normalized]
FROM repo.[RepoObject_SqlModules_20_statement_children] AS T1
CROSS APPLY [repo].[ftv_sqlparse_children_pivot]([T1].[children]) AS T2
WHERE [T1].[class] = 'Function'
 AND [T1].[is_group] = 1
 AND [T2].[child1_normalized] = '(NOLOCK)'
 --
 --SELECT
 --       [RepoObject_guid]
 --     , [key]
 --     , [SysObject_fullname]
 --     , [normalized_wo_nolock] = [0]
 --     --, [1]
 --FROM
 --(
 --    SELECT
 --           [T1].[RepoObject_guid]
 --         , [T1].[key]
 --         , [T1].[SysObject_fullname]
 --         , [T1].[normalized]
 --         , [T2_normalized] = [T2].[normalized]
 --         , [T2_json_key] = [T2].[json_key]
 --    FROM
 --         repo.RepoObject__sql_modules_20_statement_children AS T1
 --         CROSS APPLY
 --         [repo].[ftv_sqlparse]([T1].[children]) AS T2
 --    WHERE  [T1].[class] = 'Function'
 --           AND [T1].[is_group] = 1
 --) AS sourcetable PIVOT(MAX(T2_normalized) FOR T2_json_key IN(
 --                                                             [0]
 --                                                           , [1])) AS PivotTable
 --WHERE [1] = '(NOLOCK)'
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_24_IdentifierList_children

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| T2_json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| T2_class | NVARCHAR(500) | yes |  |
| Identifier_alias | NVARCHAR(MAX) | yes |  |
| Identifier_source | NVARCHAR(MAX) | yes |  |
| Identifier_source_class | NVARCHAR(500) | yes |  |
| Identifier_source_children | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_24_IdentifierList_children]
AS
--
SELECT [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T2].[json_key] AS T2_json_key
 , [T1].[SysObject_fullname]
 , [T1].[RowNumber_per_Object]
 , [T1].[class]
 --, [T1].[is_group]
 --, [T1].[is_keyword]
 --, [T1].[is_whitespace]
 , [T1].[normalized]
 --, [T1].[children]
 , [T2_class] = [T2].[class]
 , [Identifier_alias] = CASE [T2].[class]
  WHEN 'Identifier'
   THEN CASE 
     WHEN [T2].[child1_normalized] IS NULL
      THEN [T2].[child0_normalized]
     WHEN [T2].[child1_normalized] = 'AS'
      THEN [T2].[child2_normalized]
     WHEN [T2].[child1_normalized] = '.'
      THEN [T2].[child2_normalized]
     WHEN [T2].[child3_normalized] = 'AS'
      THEN [T2].[child4_normalized]
     END
  WHEN 'Comparison'
   THEN CASE 
     WHEN [T2].[child1_normalized] = '='
      THEN [T2].[child0_normalized]
     END
  END
 , [Identifier_source] = CASE [T2].[class]
  WHEN 'Identifier'
   THEN CASE [T2].[child0_class]
     WHEN 'Token'
      THEN [T2].[normalized]
     WHEN 'Function'
      THEN [T2].[child0_normalized]
     END
  WHEN 'Comparison'
   THEN CASE 
     WHEN [T2].[child1_normalized] = '='
      THEN [T2].[child2_normalized]
     END
  END
 , [Identifier_source_class] = CASE [T2].[class]
  WHEN 'Identifier'
   THEN CASE [T2].[child0_class]
     WHEN 'Token'
      THEN [T2].[class]
     WHEN 'Function'
      THEN [T2].[child0_class]
     END
  WHEN 'Comparison'
   THEN CASE 
     WHEN [T2].[child1_normalized] = '='
      THEN [T2].[child2_class]
     END
  END
 , [Identifier_source_children] = CASE [T2].[class]
  WHEN 'Identifier'
   THEN CASE [T2].[child0_class]
     WHEN 'Token'
      THEN [T2].[children]
     WHEN 'Function'
      THEN [T2].[child0_children]
     END
  WHEN 'Comparison'
   THEN CASE 
     WHEN [T2].[child1_normalized] = '='
      THEN [T2].[child2_children]
     END
  END
--, [T2].[is_group]
--, [T2].[is_keyword]
--, [T2].[is_whitespace]
--, [T2].[normalized]
--, [T2].[children]
--, [T2].[child0_class]
--, [T2].[child0_is_group]
--, [T2].[child0_is_keyword]
--, [T2].[child0_is_whitespace]
--, [T2].[child0_normalized]
--, [T2].[child0_children]
--, [T2].[child1_class]
--, [T2].[child1_is_group]
--, [T2].[child1_is_keyword]
--, [T2].[child1_is_whitespace]
--, [T2].[child1_normalized]
--, [T2].[child1_children]
--, [T2].[child2_class]
--, [T2].[child2_is_group]
--, [T2].[child2_is_keyword]
--, [T2].[child2_is_whitespace]
--, [T2].[child2_normalized]
--, [T2].[child2_children]
--, [T2].[child3_class]
--, [T2].[child3_is_group]
--, [T2].[child3_is_keyword]
--, [T2].[child3_is_whitespace]
--, [T2].[child3_normalized]
--, [T2].[child3_children]
--, [T2].[child4_class]
--, [T2].[child4_is_group]
--, [T2].[child4_is_keyword]
--, [T2].[child4_is_whitespace]
--, [T2].[child4_normalized]
--, [T2].[child4_children]
FROM [repo].[RepoObject_SqlModules_20_statement_children] AS T1
CROSS APPLY [repo].[ftv_sqlparse_with_some_children](T1.children) AS T2
WHERE [T1].[class] = 'IdentifierList'
 AND [T2].[class] IN (
  'Identifier'
  , 'Comparison'
  )
 ----there was any reason for this filter
 ----now we remove it, but we need to check the case of 'Identifier'
 -- AND [T2].[class] = 'Comparison'

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_25_IdentifierList_children_IdentifierSplit

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| T2_json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| T2_class | NVARCHAR(500) | yes |  |
| Identifier_alias | NVARCHAR(MAX) | yes |  |
| Identifier_source | NVARCHAR(MAX) | yes |  |
| Identifier_source_class | NVARCHAR(500) | yes |  |
| Identifier_source_children | NVARCHAR(MAX) | yes |  |
| Identifier_source_table | NVARCHAR(4000) | yes |  |
| Identifier_source_column | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

--in case of an simple identifier like [T1].[aaa]
--get the table part [Identifier_source_table] (before dot) and the column part [Identifier_source_column] (after dot)
CREATE VIEW [repo].[RepoObject_SqlModules_25_IdentifierList_children_IdentifierSplit]
AS
--
SELECT [t1].[RepoObject_guid]
 , [t1].[json_key]
 , [t1].[T2_json_key]
 , [t1].[SysObject_fullname]
 , [t1].[RowNumber_per_Object]
 , [t1].[class]
 , [t1].[normalized]
 , [t1].[T2_class]
 , [t1].[Identifier_alias]
 , [t1].[Identifier_source]
 , [t1].[Identifier_source_class]
 , [t1].[Identifier_source_children]
 --in case of an simple identifier like [T1].[aaa] get the table part (before dot) and the column part (after dot)
 , [Identifier_source_table] = CASE [Identifier_source_class]
  WHEN 'Identifier'
   THEN CASE 
     WHEN [T3].[child1_normalized] = '.'
      AND NOT [T3].[child2_normalized] IS NULL
      THEN [T3].[child0_normalized]
     WHEN [T3].[child1_normalized] IS NULL
      THEN NULL
     END
  END
 , [Identifier_source_column] = CASE [Identifier_source_class]
  WHEN 'Identifier'
   THEN CASE 
     WHEN [T3].[child1_normalized] = '.'
      AND NOT [T3].[child2_normalized] IS NULL
      THEN [T3].[child2_normalized]
     WHEN [T3].[child1_normalized] IS NULL
      THEN [T3].[child0_normalized]
     END
  END
--, [T3].[child0_class]
--, [T3].[child0_is_group]
--, [T3].[child0_is_keyword]
--, [T3].[child0_normalized]
--, [T3].[child0_children]
--, [T3].[child1_class]
--, [T3].[child1_is_group]
--, [T3].[child1_is_keyword]
--, [T3].[child1_normalized]
--, [T3].[child1_children]
--, [T3].[child2_class]
--, [T3].[child2_is_group]
--, [T3].[child2_is_keyword]
--, [T3].[child2_normalized]
--, [T3].[child2_children]
--, [T3].[child3_class]
--, [T3].[child3_is_group]
--, [T3].[child3_is_keyword]
--, [T3].[child3_normalized]
--, [T3].[child3_children]
--, [T3].[child4_class]
--, [T3].[child4_is_group]
--, [T3].[child4_is_keyword]
--, [T3].[child4_normalized]
--, [T3].[child4_children]
FROM [repo].[RepoObject_SqlModules_24_IdentifierList_children] AS T1
CROSS APPLY [repo].[ftv_sqlparse_children_pivot](T1.[Identifier_source_children]) AS T3

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_26_IdentifierList_children_IdentifierSplit_QuoteName

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| T2_json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| T2_class | NVARCHAR(500) | yes |  |
| Identifier_alias | NVARCHAR(MAX) | yes |  |
| Identifier_source | NVARCHAR(MAX) | yes |  |
| Identifier_source_class | NVARCHAR(500) | yes |  |
| Identifier_source_children | NVARCHAR(MAX) | yes |  |
| Identifier_source_table | NVARCHAR(4000) | yes |  |
| Identifier_source_column | NVARCHAR(4000) | yes |  |
| Identifier_alias_QuoteName | NVARCHAR(MAX) | yes |  |
| Identifier_source_table_QuoteName | NVARCHAR(4000) | yes |  |
| Identifier_source_column_QuoteName | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_26_IdentifierList_children_IdentifierSplit_QuoteName]
AS
SELECT [RepoObject_guid]
 , [json_key]
 , [T2_json_key]
 , [SysObject_fullname]
 , [RowNumber_per_Object]
 , [class]
 , [normalized]
 , [T2_class]
 , [Identifier_alias]
 , [Identifier_source]
 , [Identifier_source_class]
 , [Identifier_source_children]
 , [Identifier_source_table]
 , [Identifier_source_column]
 , [Identifier_alias_QuoteName] = CASE 
  WHEN LEFT([Identifier_alias], 1) = '['
   AND RIGHT([Identifier_alias], 1) = ']'
   THEN [Identifier_alias]
  ELSE QUOTENAME([Identifier_alias])
  END
 , [Identifier_source_table_QuoteName] = CASE 
  WHEN LEFT([Identifier_source_table], 1) = '['
   AND RIGHT([Identifier_source_table], 1) = ']'
   THEN [Identifier_source_table]
  ELSE QUOTENAME([Identifier_source_table])
  END
 , [Identifier_source_column_QuoteName] = CASE 
  WHEN LEFT([Identifier_source_column], 1) = '['
   AND RIGHT([Identifier_source_column], 1) = ']'
   THEN [Identifier_source_column]
  ELSE QUOTENAME([Identifier_source_column])
  END
FROM [repo].[RepoObject_SqlModules_25_IdentifierList_children_IdentifierSplit]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_29_1_object_is_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| is_union | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
--Objects, containing the keywords ('UNION', 'UNION ALL')
--We assume that it is UNION.
CREATE VIEW [repo].[RepoObject_SqlModules_29_1_object_is_union]
AS
--
SELECT [RepoObject_guid]
 , [is_union] = 1
FROM repo.[RepoObject_SqlModules_20_statement_children]
WHERE ([is_keyword] = 1)
 AND (
  [normalized] IN (
   'UNION'
   , 'UNION ALL'
   )
  )
GROUP BY [RepoObject_guid]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_29_2_object_is_GroupBy

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| has_GroupBy | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObject_SqlModules_29_2_object_is_GroupBy]
AS
--
SELECT [RepoObject_guid]
 , [has_GroupBy] = 1
FROM repo.[RepoObject_SqlModules_20_statement_children]
WHERE [is_keyword] = 1
 AND [normalized] = 'GROUP BY'
GROUP BY [RepoObject_guid]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_31_object

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| is_1_create | INT | yes |  |
| is_2_view | INT | yes |  |
| is_3_Identifier | INT | yes |  |
| is_4_as | INT | yes |  |
| is_5_select | INT | yes |  |
| is_6_Identifier | INT | yes |  |
| is_6_IdentifierList | INT | yes |  |
| is_7_from | INT | yes |  |
| is_7_IdentifierList | INT | yes |  |
| is_8_IdentifierList | INT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_31_object]
AS
--
SELECT [RepoObject_guid]
 , MAX([SysObject_fullname]) AS [SysObject_fullname]
 , MAX([is_1_create]) AS [is_1_create]
 , MAX([is_2_view]) AS [is_2_view]
 , MAX([is_3_Identifier]) AS [is_3_Identifier]
 , MAX([is_4_as]) AS [is_4_as]
 , MAX([is_5_select]) AS [is_5_select]
 , MAX([is_6_Identifier]) AS [is_6_Identifier]
 , MAX([is_6_IdentifierList]) AS [is_6_IdentifierList]
 , MAX([is_7_from]) AS [is_7_from]
 , MAX([is_7_IdentifierList]) AS [is_7_IdentifierList]
 , MAX([is_8_IdentifierList]) AS [is_8_IdentifierList]
FROM repo.[RepoObject_SqlModules_21_statement_children_helper]
GROUP BY [RepoObject_guid]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_32_ObjectClass

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| class | NVARCHAR(500) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| Min_RowNumber_per_class | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObject_SqlModules_32_ObjectClass]
AS
--
SELECT [RepoObject_guid]
 , [class]
 , MAX([T1].[SysObject_fullname]) AS [SysObject_fullname]
 , [Min_RowNumber_per_class] = MIN([RowNumber_per_Object])
FROM [repo].[RepoObject_SqlModules_20_statement_children] AS T1
GROUP BY [RepoObject_guid]
 , [class]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_33_ObjectNormalized

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| normalized | NVARCHAR(MAX) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| Min_RowNumber_per_normalized | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObject_SqlModules_33_ObjectNormalized]
AS
--
SELECT [RepoObject_guid]
 , [normalized]
 , MAX([T1].[SysObject_fullname]) AS [SysObject_fullname]
 , [Min_RowNumber_per_normalized] = MIN([RowNumber_per_Object])
FROM [repo].[RepoObject_SqlModules_20_statement_children] AS T1
GROUP BY [RepoObject_guid]
 , [normalized]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_39_object

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| is_create_view_Identifier_as_select | INT | yes |  |
| is_select_IdentifierList_from | INT | yes |  |
| Min_RowNumber_IdentifierList | BIGINT | yes |  |
| Min_RowNumber_From | BIGINT | yes |  |
| Min_RowNumber_GroupBy | BIGINT | yes |  |
| Min_RowNumber_Where | BIGINT | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| is_1_create | INT | yes |  |
| is_2_view | INT | yes |  |
| is_3_Identifier | INT | yes |  |
| is_4_as | INT | yes |  |
| is_5_select | INT | yes |  |
| is_6_Identifier | INT | yes |  |
| is_6_IdentifierList | INT | yes |  |
| is_7_from | INT | yes |  |
| is_7_IdentifierList | INT | yes |  |
| is_8_IdentifierList | INT | yes |  |
| is_union | INT | yes |  |
| has_GroupBy | INT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_39_object]
AS
--
SELECT [T1].[RepoObject_guid]
 , [is_create_view_Identifier_as_select] = [T31].[is_1_create] * [T31].[is_2_view] * [T31].[is_3_Identifier] * [T31].[is_4_as] * [T31].[is_5_select]
 , [is_select_IdentifierList_from] = [T31].[is_5_select] * [T31].[is_6_IdentifierList] * [T31].[is_7_from]
 , [Min_RowNumber_IdentifierList] = [T32_1].[Min_RowNumber_per_class]
 , [Min_RowNumber_From] = [T33_1].[Min_RowNumber_per_normalized]
 , [Min_RowNumber_GroupBy] = [T33_2].[Min_RowNumber_per_normalized]
 , [Min_RowNumber_Where] = [T32_2].[Min_RowNumber_per_class]
 --the following columns are for easy issue tracking
 , [ro].[SysObject_fullname]
 , [T31].[is_1_create]
 , [T31].[is_2_view]
 , [T31].[is_3_Identifier]
 , [T31].[is_4_as]
 , [T31].[is_5_select]
 , [T31].[is_6_Identifier]
 , [T31].[is_6_IdentifierList]
 , [T31].[is_7_from]
 , [T31].[is_7_IdentifierList]
 , [T31].[is_8_IdentifierList]
 , [t26].[is_union]
 , [t27].[has_GroupBy]
FROM repo.RepoObject_SqlModules AS T1
LEFT OUTER JOIN repo.RepoObject AS ro
 ON ro.RepoObject_guid = T1.RepoObject_guid
LEFT OUTER JOIN repo.[RepoObject_SqlModules_31_object] AS T31
 ON T31.RepoObject_guid = T1.RepoObject_guid
LEFT OUTER JOIN repo.[RepoObject_SqlModules_32_ObjectClass] AS T32_1
 ON T32_1.RepoObject_guid = T1.RepoObject_guid
  AND T32_1.class = 'IdentifierList'
LEFT OUTER JOIN repo.[RepoObject_SqlModules_32_ObjectClass] AS T32_2
 ON T32_2.RepoObject_guid = T1.RepoObject_guid
  AND T32_2.class = 'WHERE'
LEFT OUTER JOIN repo.[RepoObject_SqlModules_33_ObjectNormalized] AS T33_1
 ON T33_1.RepoObject_guid = T1.RepoObject_guid
  AND T33_1.normalized = 'FROM'
LEFT OUTER JOIN repo.[RepoObject_SqlModules_33_ObjectNormalized] AS T33_2
 ON T33_2.RepoObject_guid = T1.RepoObject_guid
  AND T33_2.normalized = 'GROUP BY'
LEFT OUTER JOIN [repo].[RepoObject_SqlModules_29_1_object_is_union] AS T26
 ON T26.RepoObject_guid = T1.RepoObject_guid
LEFT OUTER JOIN [repo].[RepoObject_SqlModules_29_2_object_is_GroupBy] AS T27
 ON T27.RepoObject_guid = T1.RepoObject_guid
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_41_from

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |
| normalized_PatIndex_Select | BIGINT | yes |  |
| normalized_wo_nolock | NVARCHAR(MAX) | yes |  |
| Min_RowNumber_From | BIGINT | yes |  |
| Min_RowNumber_GroupBy | BIGINT | yes |  |
| Min_RowNumber_Where | BIGINT | yes |  |
| identifier_name | NVARCHAR(MAX) | yes |  |
| identifier_alias | NVARCHAR(MAX) | yes |  |
| join_type | VARCHAR(16) | yes |  |
| is_join | INT | no |  |
| is_from | INT | no |  |
| patindex_nolock | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
rows in [repo].[RepoObject__sql_modules_20_statement_children]
which define the first Block 
- between FROM and WHERE
- or between FROM and GROUP BY

Attention, this will not work for UNION to analyze all parts of the UNION
- we could get the first part
- we could get the part from the first from to a first where in another part of the UNION
*/

CREATE VIEW [repo].[RepoObject_SqlModules_41_from]
AS
--
SELECT
       [T1].[RepoObject_guid]
     , [T1].[json_key]
     , [T1].[SysObject_fullname]
     , [T1].[RowNumber_per_Object]
     , [T1].[class]
     , [T1].[is_group]
     , [T1].[is_keyword]
     , [T1].[is_whitespace]
     , [T1].[normalized]
     , [T1].[children]
     , [normalized_PatIndex_Select] = PATINDEX('%SELECT%' , [T1].[normalized])
     , [normalized_wo_nolock] = TRIM(REPLACE([T1].[normalized] , '(NOLOCK)' , ''))
       --, [T23_normalized_wo_nolock] = [T23].[normalized_wo_nolock]
     , [T2].[Min_RowNumber_From]
     , [T2].[Min_RowNumber_GroupBy]
     , [T2].[Min_RowNumber_Where]
     , [T22].[identifier_name]
     , [T22].[identifier_alias]
     , [t4].[join_type]
     , [is_join] = IIF(NOT [t4].[join_type] IS NULL , 1 , 0)
     , [is_from] = IIF([T1].[normalized] = 'FROM'
                       AND [T1].[is_keyword] = 1 , 1 , 0)
     , [patindex_nolock] = PATINDEX('%(NOLOCK)%' , [T1].[normalized])
FROM
     [repo].[RepoObject_SqlModules_20_statement_children] AS T1
     LEFT OUTER JOIN
     [repo].[RepoObject_SqlModules_39_object] AS T2
     ON T2.[RepoObject_guid] = T1.[RepoObject_guid]
     LEFT OUTER JOIN
     [repo].[RepoObject_SqlModules_22_identifier_alias_AS] AS T22
     ON T22.[RepoObject_guid] = T1.[RepoObject_guid]
        AND T22.[json_key] = T1.[json_key]
     --LEFT OUTER JOIN
     --[repo].[RepoObject__sql_modules_23_normalized_wo_nolock] AS T23
     --ON T23.[RepoObject_guid] = T1.[RepoObject_guid]
     --   AND T23.[key] = T1.[key]
     LEFT OUTER JOIN
     [repo].[join_type] AS T4
     ON T4.[join_type_variant] = T1.normalized
        AND T1.is_keyword = 1
WHERE
--extract the FROM part:
--start: [Min_RowNumber_From]
[T2].[Min_RowNumber_From] <= [T1].[RowNumber_per_Object]
--ende: [Min_RowNumber_Where] or [Min_RowNumber_GroupBy]
AND ([T2].[Min_RowNumber_Where] IS NULL
     OR [T2].[Min_RowNumber_Where] > [T1].[RowNumber_per_Object])
AND ([T2].[Min_RowNumber_GroupBy] IS NULL
     OR [T2].[Min_RowNumber_GroupBy] > [T1].[RowNumber_per_Object])
--ORDER BY
--         [T1].[RepoObject_guid]
--       , [T1].[RowNumber_per_Object]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_42_from_Identifier

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| class | NVARCHAR(500) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| name | NVARCHAR(MAX) | yes |  |
| name_charindex_dot | BIGINT | yes |  |
| alias | NVARCHAR(MAX) | yes |  |
| T1_identifier_alias | NVARCHAR(MAX) | yes |  |
| lag_normalized_wo_nolock | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

--todo IdentifierList
--done: bad performance => Persistence of [repo].[RepoObject_SqlModules_41_from]
CREATE VIEW [repo].[RepoObject_SqlModules_42_from_Identifier]
AS
--
SELECT
 --
 [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [T1].[class]
 , [T1].[RowNumber_per_Object]
 --todo: we need extra handling when the result of [name] is an IdentifierList and need to exclude them here
 , [name] = COALESCE([T1].[identifier_name], [T1].[normalized_wo_nolock])
 , [name_charindex_dot] = CHARINDEX('.', COALESCE([T1].[identifier_name], [T1].[normalized_wo_nolock]))
 --some alias we can get from [T1].[identifier_alias]
 --but in case of aaa (NOLOCK) the alias is on the next row: [lag].[normalized_wo_nolock]
 , [alias] = COALESCE([T1].[identifier_alias], [lag].[normalized_wo_nolock])
 , [T1_identifier_alias] = [T1].[identifier_alias]
 , [lag_normalized_wo_nolock] = [lag].[normalized_wo_nolock]
--, [pre_is_join] = [pre].[is_join]
--, [pre_is_from] = [pre].[is_from]
--, [T1].[patindex_nolock]
--, [lag_patindex_nolock] = [lag].[patindex_nolock]
--, [T1].[SysObject_fullname]
--, [T1].[is_group]
--, [T1].[is_keyword]
--, [T1].[is_whitespace]
--, [T1].[normalized]
--  --,T1.[children]
--, [T1].[normalized_wo_nolock]
--, [T1].[Min_RowNumber_From]
--, [T1].[Min_RowNumber_Where]
--, [T1].[identifier_name]
--, [T1].[identifier_alias]
--, [T1].[join_type]
--, [T1].[is_join]
--, [T1].[is_from]
FROM [repo].[RepoObject_SqlModules_41_from_T] AS T1
--required filter
--the predecessor (by [RowNumber_per_Object]) of T1 should be (is_from or is_join)
--then often T1 contains an identifier
--todo: sometimes an Identifier is a SELECT statement like '(SELECT ... FROM ...) as abc'
INNER JOIN [repo].[RepoObject_SqlModules_41_from_T] AS pre
 ON pre.[RepoObject_guid] = T1.[RepoObject_guid]
  AND pre.[RowNumber_per_Object] + 1 = T1.[RowNumber_per_Object]
  AND (
   pre.[is_join] = 1
   OR pre.[is_from] = 1
   )
--to extract some alias we need the folowing entry (lag 1)
LEFT OUTER JOIN (
 SELECT [T1].[RepoObject_guid]
  , [T1].[RowNumber_per_Object]
  , [T1].[normalized_wo_nolock]
 --, [T1].[json_key]
 --, [T1].[SysObject_fullname]
 --, [T1].[class]
 --, [T1].[is_group]
 --, [T1].[is_keyword]
 --, [T1].[is_whitespace]
 --, [T1].[normalized]
 --, [T1].[children]
 --, [T1].[Min_RowNumber_From]
 --, [T1].[Min_RowNumber_GroupBy]
 --, [T1].[Min_RowNumber_Where]
 --, [T1].[identifier_name]
 --, [T1].[identifier_alias]
 --, [T1].[join_type]
 --, [T1].[is_join]
 --, [T1].[is_from]
 --, [T1].[patindex_nolock]
 FROM [repo].[RepoObject_SqlModules_41_from_T] AS T1
 WHERE [T1].[patindex_nolock] > 0
 ) AS [lag]
 ON [lag].[RepoObject_guid] = T1.[RepoObject_guid]
  AND [lag].[RowNumber_per_Object] - 1 = T1.[RowNumber_per_Object]
WHERE
 --we can extract only 'Identifier'
 [T1].[class] = 'Identifier'
 --but even using this filter sometimes we get something different, for exampe a select statement
 --we will not handle them
 AND [T1].[normalized_PatIndex_Select] = 0
 --exclude UNION
 AND NOT EXISTS (
  SELECT 1
  FROM [repo].[RepoObject_SqlModules_29_1_object_is_union] AS [filter]
  WHERE [filter].[RepoObject_guid] = [T1].[RepoObject_guid]
  )

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_43_from_Identifier

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| class | NVARCHAR(500) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| name | NVARCHAR(MAX) | yes |  |
| name_charindex_dot | BIGINT | yes |  |
| name_PreDot | NVARCHAR(MAX) | yes |  |
| name_PostDot | NVARCHAR(MAX) | yes |  |
| alias | NVARCHAR(MAX) | yes |  |
| T1_identifier_alias | NVARCHAR(MAX) | yes |  |
| lag_normalized_wo_nolock | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_43_from_Identifier]
AS
SELECT
 --
 [RepoObject_guid]
 , [json_key]
 , [SysObject_fullname]
 , [class]
 , [RowNumber_per_Object]
 , [name]
 , [name_charindex_dot]
 , [name_PreDot] = CASE 
  WHEN [name_charindex_dot] > 1
   THEN LEFT([name], [name_charindex_dot] - 1)
  END
 , [name_PostDot] = CASE 
  WHEN [name_charindex_dot] > 1
   THEN SUBSTRING([name], [name_charindex_dot] + 1, LEN([name]))
  END
 , [alias]
 , [T1_identifier_alias]
 , [lag_normalized_wo_nolock]
FROM [repo].[RepoObject_SqlModules_42_from_Identifier]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_44_from_Identifier_QuoteName

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| class | NVARCHAR(500) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| name | NVARCHAR(MAX) | yes |  |
| name_charindex_dot | BIGINT | yes |  |
| name_PreDot | NVARCHAR(MAX) | yes |  |
| name_PostDot | NVARCHAR(MAX) | yes |  |
| alias | NVARCHAR(MAX) | yes |  |
| T1_identifier_alias | NVARCHAR(MAX) | yes |  |
| lag_normalized_wo_nolock | NVARCHAR(MAX) | yes |  |
| alias_QuoteName | NVARCHAR(MAX) | yes |  |
| name_PreDot_QuoteName | NVARCHAR(MAX) | yes |  |
| name_PostDot_QuoteName | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_44_from_Identifier_QuoteName]
AS
SELECT
 --
 [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [T1].[class]
 , [T1].[RowNumber_per_Object]
 , [T1].[name]
 , [T1].[name_charindex_dot]
 , [T1].[name_PreDot]
 , [T1].[name_PostDot]
 , [T1].[alias]
 , [T1].[T1_identifier_alias]
 , [T1].[lag_normalized_wo_nolock]
 , [alias_QuoteName] = CASE 
  WHEN LEFT([alias], 1) = '['
   AND RIGHT([alias], 1) = ']'
   THEN [alias]
  ELSE QUOTENAME([alias])
  END
 , [name_PreDot_QuoteName] = CASE 
  WHEN LEFT([name_PreDot], 1) = '['
   AND RIGHT([name_PreDot], 1) = ']'
   THEN [name_PreDot]
  ELSE QUOTENAME([name_PreDot])
  END
 , [name_PostDot_QuoteName] = CASE 
  WHEN LEFT([name_PostDot], 1) = '['
   AND RIGHT([name_PostDot], 1) = ']'
   THEN [name_PostDot]
  ELSE QUOTENAME([name_PostDot])
  END
FROM [repo].[RepoObject_SqlModules_43_from_Identifier] AS T1

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_51_Identitfier

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| source_table | NVARCHAR(MAX) | yes |  |
| source_column | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |
| child0_class | NVARCHAR(500) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*

--only SELECT Identifier (before FROM)
SELECT
T1.*
FROM repo.RepoObject_SqlModules_51_Identitfier T1
   INNER JOIN
   repo.RepoObject_SqlModules_39_object AS T39
   ON T39.RepoObject_guid = T1.RepoObject_guid
      AND T39.Min_RowNumber_From = T1.RowNumber_per_Object + 1


*/
CREATE VIEW [repo].[RepoObject_SqlModules_51_Identitfier]
AS
SELECT
 --
 [T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [T1].[RowNumber_per_Object]
 , [T1].[class]
 , [T1].[normalized]
 , [T1].[is_group]
 , [T1].[is_keyword]
 , [T1].[is_whitespace]
 --same logic: [repo].[RepoObject_SqlModules_25_IdentifierList_children_IdentifierSplit]
 --in case of an simple identifier like [T1].[aaa] get the table part (before dot) and the column part (after dot)
 , [source_table] = CASE 
  WHEN [T1].[child1_normalized] = '.'
   AND NOT [T1].[child2_normalized] IS NULL
   THEN [T1].[child0_normalized]
  WHEN [T1].[child1_normalized] IS NULL
   THEN NULL
  END
 , [source_column] = CASE 
  WHEN [T1].[child1_normalized] = '.'
   AND NOT [T1].[child2_normalized] IS NULL
   THEN [T1].[child2_normalized]
  WHEN [T1].[child1_normalized] IS NULL
   THEN [T1].[child0_normalized]
  END
 , [T1].[children]
 , [T1].[child0_class]
--what happens in case of aa.bb as c or c = aa.bb?
--, [T1].[RepoObject_guid]
--, [T1].[json_key]
--, [T1].[SysObject_fullname]
--, [T1].[RowNumber_per_Object]
--, [T1].[class]
--, [T1].[is_group]
--, [T1].[is_keyword]
--, [T1].[is_whitespace]
--, [T1].[normalized]
--, [T1].[children]
--, [T1].[child0_class]
--, [T1].[child0_is_group]
--, [T1].[child0_is_keyword]
--, [T1].[child0_is_whitespace]
--, [T1].[child0_normalized]
--, [T1].[child0_children]
--, [T1].[child1_class]
--, [T1].[child1_is_group]
--, [T1].[child1_is_keyword]
--, [T1].[child1_is_whitespace]
--, [T1].[child1_normalized]
--, [T1].[child1_children]
--, [T1].[child2_class]
--, [T1].[child2_is_group]
--, [T1].[child2_is_keyword]
--, [T1].[child2_is_whitespace]
--, [T1].[child2_normalized]
--, [T1].[child2_children]
--, [T1].[child3_class]
--, [T1].[child3_is_group]
--, [T1].[child3_is_keyword]
--, [T1].[child3_is_whitespace]
--, [T1].[child3_normalized]
--, [T1].[child3_children]
--, [T1].[child4_class]
--, [T1].[child4_is_group]
--, [T1].[child4_is_keyword]
--, [T1].[child4_is_whitespace]
--, [T1].[child4_normalized]
--, [T1].[child4_children]
FROM repo.RepoObject_SqlModules_20_statement_children AS T1
WHERE [T1].[class] = 'Identifier'

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_52_Identitfier_QuoteName

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| source_table | NVARCHAR(MAX) | yes |  |
| source_column | NVARCHAR(MAX) | yes |  |
| source_table_QuoteName | NVARCHAR(MAX) | yes |  |
| source_column_QuoteName | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |
| child0_class | NVARCHAR(500) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObject_SqlModules_52_Identitfier_QuoteName]
AS
SELECT
 --
 [RepoObject_guid]
 , [json_key]
 , [SysObject_fullname]
 , [RowNumber_per_Object]
 , [class]
 , [normalized]
 , [is_group]
 , [is_keyword]
 , [is_whitespace]
 , [source_table]
 , [source_column]
 , [source_table_QuoteName] = CASE 
  WHEN LEFT([source_table], 1) = '['
   AND RIGHT([source_table], 1) = ']'
   THEN [source_table]
  ELSE QUOTENAME([source_table])
  END
 , [source_column_QuoteName] = CASE 
  WHEN LEFT([source_column], 1) = '['
   AND RIGHT([source_column], 1) = ']'
   THEN [source_column]
  ELSE QUOTENAME([source_column])
  END
 , [children]
 , [child0_class]
FROM [repo].[RepoObject_SqlModules_51_Identitfier]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_61_SelectIdentifier_Union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| source_table_QuoteName | NVARCHAR(MAX) | yes |  |
| source_column_QuoteName | NVARCHAR(MAX) | yes |  |
| alias_QuoteName | NVARCHAR(MAX) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[RepoObject_SqlModules_61_SelectIdentifier_Union]
AS
SELECT [T1].[RepoObject_guid]
 , [T1].[SysObject_fullname]
 --can be empty, this is fine in case of only one source table in FROM, but it could be also OK in case of unique name within multiple source tables
 , [T1].[source_table_QuoteName]
 , [T1].[source_column_QuoteName]
 , alias_QuoteName = [T1].[source_column_QuoteName]
 , [T1].[RowNumber_per_Object]
 , [T1].[class]
 , [T1].[normalized]
FROM repo.[RepoObject_SqlModules_52_Identitfier_QuoteName] AS T1
--only SELECT Identifier before FROM
INNER JOIN repo.RepoObject_SqlModules_39_object AS T39
 ON T39.RepoObject_guid = T1.RepoObject_guid
  AND T39.Min_RowNumber_From = T1.RowNumber_per_Object + 1
WHERE NOT T1.[source_column_QuoteName] IS NULL

UNION ALL

SELECT T26.RepoObject_guid
 , T26.SysObject_fullname
 --can be empty, this is fine in case of only one source table in FROM, but it could be also OK in case of unique name within multiple source tables
 , source_table_QuoteName = T26.Identifier_source_table_QuoteName
 , source_column_QuoteName = T26.Identifier_source_column_QuoteName
 , alias_QuoteName = T26.Identifier_alias_QuoteName
 , T26.RowNumber_per_Object
 , T26.class
 , T26.normalized
FROM repo.RepoObject_SqlModules_26_IdentifierList_children_IdentifierSplit_QuoteName AS T26
INNER JOIN repo.RepoObject_SqlModules_39_object AS T39
 ON T26.RepoObject_guid = T39.RepoObject_guid
  --only default views where SELECT is the 5th element in view definition
  AND T39.is_5_select = 1
  --only SELECT IdentifierList after SELECT (5)
  AND T26.RowNumber_per_Object > 5
  --only SELECT IdentifierList before FROM
  AND T39.Min_RowNumber_From > T26.RowNumber_per_Object
--source column should exist (it will not exist in case of calculations, functions, ...)
WHERE NOT T26.Identifier_source_column_QuoteName IS NULL

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_71_reference_ExpliciteTableAlias

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| alias_QuoteName | NVARCHAR(MAX) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| source_SysObject_fullname | NVARCHAR(261) | no |  |
| source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| source_RepoObjectColumn_name | NVARCHAR(128) | no |  |
| source_table_QuoteName | NVARCHAR(MAX) | yes |  |
| source_column_QuoteName | NVARCHAR(MAX) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
explicit table alias:

T1.source_table_QuoteName exists an can be linked to an exsisting T44.alias_QuoteName
for example

T1.aaa
from
table as T1


*/
CREATE VIEW [repo].[RepoObject_SqlModules_71_reference_ExpliciteTableAlias]
AS
SELECT
 --
 T1.RepoObject_guid
 , T1.alias_QuoteName
 , T1.SysObject_fullname
 , roc.RepoObjectColumn_guid
 , roc.RepoObjectColumn_name
 , source_RepoObject_guid = ro_source.RepoObject_guid
 , source_SysObject_fullname = ro_source.[SysObject_fullname]
 , source_RepoObjectColumn_guid = roc_source.RepoObjectColumn_guid
 , source_RepoObjectColumn_name = roc_source.RepoObjectColumn_name
 , T1.source_table_QuoteName
 , T1.source_column_QuoteName
 , T1.[normalized]
FROM [repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T] AS T1
INNER JOIN [repo].[RepoObject_SqlModules_44_from_Identifier_QuoteName] AS T44
 ON T44.RepoObject_guid = T1.RepoObject_guid
  AND T44.alias_QuoteName = T1.source_table_QuoteName
INNER JOIN [repo].[RepoObjectColumn] roc
 ON QUOTENAME(roc.SysObjectColumn_name) = T1.alias_QuoteName
  AND roc.RepoObject_guid = T1.RepoObject_guid
INNER JOIN [repo].[RepoObject] ro_source
 ON quotename(ro_source.[SysObject_schema_name]) = T44.name_PreDot_QuoteName
  AND quotename(ro_source.[SysObject_name]) = T44.name_PostDot_QuoteName
INNER JOIN [repo].[RepoObjectColumn] roc_source
 ON QUOTENAME(roc_source.SysObjectColumn_name) = T1.source_column_QuoteName
  AND roc_source.RepoObject_guid = ro_source.RepoObject_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_72_reference_NoTableAlias

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| alias_QuoteName | NVARCHAR(MAX) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| source_SysObject_fullname | NVARCHAR(261) | no |  |
| source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| source_RepoObjectColumn_name | NVARCHAR(128) | no |  |
| source_table_QuoteName | NVARCHAR(MAX) | yes |  |
| source_column_QuoteName | NVARCHAR(MAX) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
missing table alias:

T1.source_table_QuoteName is NULL and can't be linked to an exsisting T44.alias_QuoteName
we try mapping only by T1.source_column_QuoteName

for example

aaa
from
table as T1

aaa
from
table
*/
CREATE VIEW [repo].[RepoObject_SqlModules_72_reference_NoTableAlias]
AS
SELECT
 --
 T1.RepoObject_guid
 , T1.alias_QuoteName
 , T1.SysObject_fullname
 , roc.RepoObjectColumn_guid
 , roc.RepoObjectColumn_name
 , source_RepoObject_guid = ro_source.RepoObject_guid
 , source_SysObject_fullname = ro_source.[SysObject_fullname]
 , source_RepoObjectColumn_guid = roc_source.RepoObjectColumn_guid
 , source_RepoObjectColumn_name = roc_source.RepoObjectColumn_name
 , T1.source_table_QuoteName
 , T1.source_column_QuoteName
 , T1.[normalized]
FROM [repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T] AS T1
INNER JOIN [repo].[RepoObject_SqlModules_44_from_Identifier_QuoteName] AS T44
 ON T44.RepoObject_guid = T1.RepoObject_guid
-- T1.source_table_QuoteName is NULL and can't be linked to an exsisting T44.alias_QuoteName
--AND T44.alias_QuoteName = T1.source_table_QuoteName
INNER JOIN [repo].[RepoObjectColumn] roc
 ON QUOTENAME(roc.SysObjectColumn_name) = T1.alias_QuoteName
  AND roc.RepoObject_guid = T1.RepoObject_guid
INNER JOIN [repo].[RepoObject] ro_source
 ON quotename(ro_source.[SysObject_schema_name]) = T44.name_PreDot_QuoteName
  AND quotename(ro_source.[SysObject_name]) = T44.name_PostDot_QuoteName
INNER JOIN [repo].[RepoObjectColumn] roc_source
 ON QUOTENAME(roc_source.SysObjectColumn_name) = T1.source_column_QuoteName
  AND roc_source.RepoObject_guid = ro_source.RepoObject_guid
WHERE
 --can't be linked to an exsisting T44.alias_QuoteName
 T1.source_table_QuoteName IS NULL

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_79_reference_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| alias_QuoteName | NVARCHAR(MAX) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| source_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| source_SysObject_fullname | NVARCHAR(261) | no |  |
| source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| source_RepoObjectColumn_name | NVARCHAR(128) | no |  |
| source_table_QuoteName | NVARCHAR(MAX) | yes |  |
| source_column_QuoteName | NVARCHAR(MAX) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[RepoObject_SqlModules_79_reference_union]
AS
SELECT [RepoObject_guid]
 , [alias_QuoteName]
 , [SysObject_fullname]
 , [RepoObjectColumn_guid]
 , [RepoObjectColumn_name]
 , [source_RepoObject_guid]
 , [source_SysObject_fullname]
 , [source_RepoObjectColumn_guid]
 , [source_RepoObjectColumn_name]
 , [source_table_QuoteName]
 , [source_column_QuoteName]
 , [normalized]
FROM [repo].[RepoObject_SqlModules_71_reference_ExpliciteTableAlias]

UNION ALL

SELECT [RepoObject_guid]
 , [alias_QuoteName]
 , [SysObject_fullname]
 , [RepoObjectColumn_guid]
 , [RepoObjectColumn_name]
 , [source_RepoObject_guid]
 , [source_SysObject_fullname]
 , [source_RepoObjectColumn_guid]
 , [source_RepoObjectColumn_name]
 , [source_table_QuoteName]
 , [source_column_QuoteName]
 , [normalized]
FROM [repo].[RepoObject_SqlModules_72_reference_NoTableAlias]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_Identitfier

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| json_key | NVARCHAR(4000) | no |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| RowNumber_per_Object | BIGINT | yes |  |
| class | NVARCHAR(500) | yes |  |
| normalized | NVARCHAR(MAX) | yes |  |
| is_group | BIT | yes |  |
| is_keyword | BIT | yes |  |
| is_whitespace | BIT | yes |  |
| source_table | NVARCHAR(MAX) | yes |  |
| source_column | NVARCHAR(MAX) | yes |  |
| children | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
obsolet?

--only SELECT Identifier (before FROM)
SELECT
T1.*
FROM repo.RepoObject_SqlModules_Identitfier T1
   INNER JOIN
   repo.RepoObject_SqlModules_39_object AS T39
   ON T39.RepoObject_guid = T1.RepoObject_guid
      AND T39.Min_RowNumber_From = T1.RowNumber_per_Object + 1


*/

CREATE   view [repo].[RepoObject_SqlModules_Identitfier]
as
SELECT 
--
[T1].[RepoObject_guid]
 , [T1].[json_key]
 , [T1].[SysObject_fullname]
 , [T1].[RowNumber_per_Object]
 , [T1].[class]
 , [T1].[normalized]
 , [T1].[is_group]
 , [T1].[is_keyword]
 , [T1].[is_whitespace]
 --same logic: [repo].[RepoObject_SqlModules_25_IdentifierList_children_IdentifierSplit]
 --in case of an simple identifier like [T1].[aaa] get the table part (before dot) and the column part (after dot)
 , [source_table] = CASE 
  WHEN [T1].[child1_normalized] = '.'
   AND NOT [T1].[child2_normalized] IS NULL
   THEN [T1].[child0_normalized]
  WHEN [T1].[child1_normalized] IS NULL
   THEN NULL
  END
 , [source_column] = CASE 
  WHEN [T1].[child1_normalized] = '.'
   AND NOT [T1].[child2_normalized] IS NULL
   THEN [T1].[child2_normalized]
  WHEN [T1].[child1_normalized] IS NULL
   THEN [T1].[child0_normalized]
  END
 , [T1].[children]
--what happens in case of aa.bb as c or c = aa.bb?
 --, [T1].[RepoObject_guid]
 --, [T1].[json_key]
 --, [T1].[SysObject_fullname]
 --, [T1].[RowNumber_per_Object]
 --, [T1].[class]
 --, [T1].[is_group]
 --, [T1].[is_keyword]
 --, [T1].[is_whitespace]
 --, [T1].[normalized]
 --, [T1].[children]
 --, [T1].[child0_class]
 --, [T1].[child0_is_group]
 --, [T1].[child0_is_keyword]
 --, [T1].[child0_is_whitespace]
 --, [T1].[child0_normalized]
 --, [T1].[child0_children]
 --, [T1].[child1_class]
 --, [T1].[child1_is_group]
 --, [T1].[child1_is_keyword]
 --, [T1].[child1_is_whitespace]
 --, [T1].[child1_normalized]
 --, [T1].[child1_children]
 --, [T1].[child2_class]
 --, [T1].[child2_is_group]
 --, [T1].[child2_is_keyword]
 --, [T1].[child2_is_whitespace]
 --, [T1].[child2_normalized]
 --, [T1].[child2_children]
 --, [T1].[child3_class]
 --, [T1].[child3_is_group]
 --, [T1].[child3_is_keyword]
 --, [T1].[child3_is_whitespace]
 --, [T1].[child3_normalized]
 --, [T1].[child3_children]
 --, [T1].[child4_class]
 --, [T1].[child4_is_group]
 --, [T1].[child4_is_keyword]
 --, [T1].[child4_is_whitespace]
 --, [T1].[child4_normalized]
 --, [T1].[child4_children]
FROM repo.RepoObject_SqlModules_20_statement_children AS T1
WHERE [T1].[class] = 'Identifier'

```

</details>

[Back to top](#dhw_self)

### repo.RepoObject_SqlModules_Repo_Sys

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| sql_modules_definition | NVARCHAR(MAX) | yes |  |
| sql_modules_dt | DATETIME | yes |  |
| sql_modules_formatted | NVARCHAR(MAX) | yes |  |
| sql_modules_formatted2 | NVARCHAR(MAX) | yes |  |
| sql_modules_json | NVARCHAR(MAX) | yes |  |
| is_json_sql_modules_json | INT | yes |  |
| modify_date | DATETIME | no |  |
| SysObject_type | CHAR(2) | yes |  |
| is_outdated | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObject_SqlModules_Repo_Sys]
AS
--
SELECT [ro].[RepoObject_guid]
 , [so].[sql_modules_definition]
 , [ros].[sql_modules_dt]
 , [ros].[sql_modules_formatted]
 , [ros].[sql_modules_formatted2]
 , [ros].[sql_modules_json]
 , [ros].[is_json_sql_modules_json]
 , [so].[modify_date]
 , [ro].[SysObject_type]
 , [is_outdated] = CAST(CASE 
   WHEN (
     [ros].[sql_modules_dt] IS NULL
     OR [ros].[sql_modules_dt] < [so].[modify_date]
     )
    THEN 1
   ELSE 0
   END AS BIT)
FROM repo.RepoObject AS ro
INNER JOIN repo_sys.SysObject AS so
 ON ro.RepoObject_guid = so.SysObject_RepoObject_guid
LEFT JOIN [repo].[RepoObject_SqlModules] AS ros
 ON ros.[RepoObject_guid] = ro.[RepoObject_guid]
WHERE NOT [so].[sql_modules_definition] IS NULL
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_gross

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| has_different_sys_names | BIT | yes |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |
| InheritanceType | TINYINT | yes |  |
| is_persistence_no_check | BIT | yes |  |
| is_persistence_no_include | BIT | yes |  |
| is_persistence_no_update | BIT | yes |  |
| is_query_plan_expression | BIT | yes |  |
| is_RepoObjectColumn_name_uniqueidentifier | INT | no |  |
| is_SysObjectColumn_missing | BIT | yes |  |
| is_SysObjectColumn_name_uniqueidentifier | INT | no |  |
| persistence_source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_Count | INT | yes |  |
| Repo_default_definition | NVARCHAR(MAX) | yes |  |
| Repo_default_is_system_named | BIT | yes |  |
| Repo_default_name | NVARCHAR(128) | yes |  |
| Repo_definition | NVARCHAR(MAX) | yes |  |
| Repo_generated_always_type | TINYINT | no |  |
| Repo_graph_type | INT | yes |  |
| Repo_is_computed | BIT | no |  |
| Repo_is_identity | BIT | no |  |
| Repo_is_nullable | BIT | yes |  |
| Repo_is_persisted | BIT | yes |  |
| Repo_seed_value | SQL_VARIANT | yes |  |
| Repo_increment_value | SQL_VARIANT | yes |  |
| Repo_user_type_fullname | NVARCHAR(128) | yes |  |
| Repo_user_type_name | NVARCHAR(128) | yes |  |
| Repo_uses_database_collation | BIT | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_column_id | INT | yes |  |
| RepoObjectColumn_fullname | NVARCHAR(520) | no |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| SysObjectColumn_column_id | INT | yes |  |
| SysObjectColumn_name | NVARCHAR(128) | no |  |
| has_get_referenced_issue | BIT | yes |  |
| is_repo_managed | BIT | yes |  |
| is_RepoObject_name_uniqueidentifier | INT | no |  |
| is_SysObject_missing | BIT | yes |  |
| is_SysObject_name_uniqueidentifier | INT | no |  |
| modify_dt | DATETIME | no |  |
| node_id | BIGINT | yes |  |
| pk_index_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| RepoObject_name | NVARCHAR(128) | no |  |
| RepoObject_Referencing_Count | INT | yes |  |
| RepoObject_schema_name | NVARCHAR(128) | no |  |
| RepoObject_type | CHAR(2) | no |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| SysObject_id | INT | yes |  |
| SysObject_modify_date | DATETIME | yes |  |
| SysObject_name | NVARCHAR(128) | no |  |
| SysObject_schema_name | NVARCHAR(128) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| SysObject_parent_object_id | INT | no |  |
| index_column_id | INT | yes |  |
| index_name | NVARCHAR(128) | yes |  |
| is_index_primary_key | BIT | yes |  |
| Property_ms_description | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[RepoObjectColumn_gross]
AS
--
SELECT
 --
 [roc].[RepoObjectColumn_guid]
 , [roc].[has_different_sys_names]
 , [roc].[Inheritance_StringAggSeparatorSql]
 , [roc].[InheritanceDefinition]
 , [roc].[InheritanceType]
 , [roc].[is_persistence_no_check]
 , [roc].[is_persistence_no_include]
 , [roc].[is_persistence_no_update]
 , [roc].[is_query_plan_expression]
 , [roc].[is_RepoObjectColumn_name_uniqueidentifier]
 , [roc].[is_SysObjectColumn_missing]
 , [roc].[is_SysObjectColumn_name_uniqueidentifier]
 , [roc].[persistence_source_RepoObjectColumn_guid]
 , [roc].[Referencing_Count]
 , [roc].[Repo_default_definition]
 , [roc].[Repo_default_is_system_named]
 , [roc].[Repo_default_name]
 , [roc].[Repo_definition]
 , [roc].[Repo_generated_always_type]
 , [roc].[Repo_graph_type]
 , [roc].[Repo_is_computed]
 , [roc].[Repo_is_identity]
 , [roc].[Repo_is_nullable]
 , [roc].[Repo_is_persisted]
 , [roc].[Repo_seed_value]
 , [roc].[Repo_increment_value]
 , [roc].[Repo_user_type_fullname]
 , [roc].[Repo_user_type_name]
 , [roc].[Repo_uses_database_collation]
 , [roc].[RepoObject_guid]
 , [roc].[RepoObjectColumn_column_id]
 , [RepoObjectColumn_fullname] = CONCAT (
  [ro].[RepoObject_fullname]
  , '.'
  , QUOTENAME([roc].[RepoObjectColumn_name])
  )
 , [roc].[RepoObjectColumn_name]
 , [roc].[SysObjectColumn_column_id]
 , [roc].[SysObjectColumn_name]
 , [ro].[has_get_referenced_issue]
 , [ro].[is_repo_managed]
 , [ro].[is_RepoObject_name_uniqueidentifier]
 , [ro].[is_SysObject_missing]
 , [ro].[is_SysObject_name_uniqueidentifier]
 , [ro].[modify_dt]
 , [ro].[node_id]
 , [ro].[pk_index_guid]
 , [ro].[RepoObject_fullname]
 , [ro].[RepoObject_name]
 , [ro].[RepoObject_Referencing_Count]
 , [ro].[RepoObject_schema_name]
 , [ro].[RepoObject_type]
 , [ro].[SysObject_fullname]
 , [ro].[SysObject_id]
 , [ro].[SysObject_modify_date]
 , [ro].[SysObject_name]
 , [ro].[SysObject_schema_name]
 , [ro].[SysObject_type]
 , [ro].[SysObject_parent_object_id]
 , [ic].[index_column_id]
 , [ic].[index_name]
 , [ic].[is_index_primary_key]
 , Property_ms_description = [repo].[fs_get_RepoObjectColumnProperty_nvarchar] ([roc].[RepoObjectColumn_guid], 'ms_description')
FROM repo.RepoObjectColumn AS roc
INNER JOIN repo.RepoObject AS ro
 ON roc.RepoObject_guid = ro.RepoObject_guid
LEFT OUTER JOIN repo.IndexColumn_union AS ic
 ON ic.index_guid = ro.pk_index_guid
  AND ic.RepoObjectColumn_guid = roc.RepoObjectColumn_guid

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_HistValidColums_setpoint

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_name | SYSNAME(128) | yes |  |
| Repo_generated_always_type | INT | no |  |
| Repo_is_nullable | INT | no |  |
| Repo_user_type_name | VARCHAR(9) | no |  |
| Repo_user_type_fullname | VARCHAR(12) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

--required colums depening on [repo].[RepoObject_persistence]
--WHERE rop.[has_history_columns] = 1  OR rop.[has_history] = 1
CREATE VIEW [repo].[RepoObjectColumn_HistValidColums_setpoint]
AS
SELECT rop.target_RepoObject_guid AS [RepoObject_guid]
 , CAST(p.[Parameter_value__result_nvarchar] AS SYSNAME) AS [RepoObjectColumn_name]
 , ValidList.[Repo_generated_always_type]
 , 0 AS [Repo_is_nullable]
 , 'DATETIME2' AS [Repo_user_type_name]
 , 'datetime2(7)' AS [Repo_user_type_fullname]
FROM [repo].[RepoObject_persistence] rop
CROSS JOIN (
 SELECT 'Hist_ValidFrom_column_name' AS [Parameter_name]
  , 1 AS [Repo_generated_always_type]
 
 UNION ALL
 
 SELECT 'Hist_ValidTo_column_name' AS [Parameter_name]
  , 2 AS [Repo_generated_always_type]
 ) ValidList
CROSS APPLY [repo].[ftv_get_parameter_value](ValidList.[Parameter_name], DEFAULT) p
WHERE rop.[has_history_columns] = 1
 OR rop.[has_history] = 1
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_InheritanceType_InheritanceDefinition

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |
| InheritanceType | INT | yes |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| roc_InheritanceType | TINYINT | yes |  |
| sub_InheritanceType | INT | yes |  |
| par_InheritanceType | INT | yes |  |
| roc_InheritanceDefinition | NVARCHAR(4000) | yes |  |
| sub_InheritanceDefinition | NVARCHAR(4000) | yes |  |
| par_InheritanceDefinition | NVARCHAR(4000) | yes |  |
| roc_Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| sub_Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| par_Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
Maybe rename RepoObjectColumnProperty_InheritanceType_InheritanceDefinition
*/
CREATE VIEW [repo].[RepoObjectColumn_InheritanceType_InheritanceDefinition]
AS
SELECT
 --
 [roc].[RepoObjectColumn_guid]
 , [pn].[property_name]
 , [rocp].[property_value]
 , [Inheritance_StringAggSeparatorSql] = COALESCE([roc].[Inheritance_StringAggSeparatorSql], [par_sub_sep].[Parameter_value__result_nvarchar], [par_sep].[Parameter_value__result_nvarchar])
 , [InheritanceDefinition] = COALESCE([roc].[InheritanceDefinition], [par_sub_def].[Parameter_value__result_nvarchar], [par_def].[Parameter_value__result_nvarchar])
 , [InheritanceType] = COALESCE([roc].[InheritanceType], [par_sub].[Parameter_value__result_int], [par].[Parameter_value__result_int])
 , [roc].[RepoObjectColumn_name]
 , [roc_InheritanceType] = [roc].[InheritanceType]
 , [sub_InheritanceType] = [par_sub].[Parameter_value__result_int]
 , [par_InheritanceType] = [par].[Parameter_value__result_int]
 , [roc_InheritanceDefinition] = [roc].[InheritanceDefinition]
 , [sub_InheritanceDefinition] = [par_sub_def].[Parameter_value__result_nvarchar]
 , [par_InheritanceDefinition] = [par_def].[Parameter_value__result_nvarchar]
 , [roc_Inheritance_StringAggSeparatorSql] = [roc].[Inheritance_StringAggSeparatorSql]
 , [sub_Inheritance_StringAggSeparatorSql] = [par_sub_sep].[Parameter_value__result_nvarchar]
 , [par_Inheritance_StringAggSeparatorSql] = [par_sep].[Parameter_value__result_nvarchar]
FROM [repo].[RepoObjectColumn] AS roc
CROSS JOIN [repo].[PropertyName_RepoObjectColumn] AS pn
LEFT JOIN [repo].[RepoObjectColumnProperty] AS rocp
 ON rocp.RepoObjectColumn_guid = [roc].[RepoObjectColumn_guid]
  AND rocp.property_name = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par_sub
 ON par_sub.[Parameter_name] = 'InheritanceType_column'
  AND par_sub.[sub_Parameter] = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par
 ON par.[Parameter_name] = 'InheritanceType_column'
  AND par.[sub_Parameter] = ''
LEFT JOIN [repo].[Parameter] AS par_sub_def
 ON par_sub_def.[Parameter_name] = 'InheritanceDefinition_column'
  AND par_sub_def.[sub_Parameter] = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par_def
 ON par_def.[Parameter_name] = 'InheritanceDefinition_column'
  AND par_def.[sub_Parameter] = ''
LEFT JOIN [repo].[Parameter] AS par_sub_sep
 ON par_sub_sep.[Parameter_name] = 'Inheritance_StringAggSeparatorSql_column'
  AND par_sub_sep.[sub_Parameter] = [pn].[property_name]
LEFT JOIN [repo].[Parameter] AS par_sep
 ON par_sep.[Parameter_name] = 'Inheritance_StringAggSeparatorSql_column'
  AND par_sep.[sub_Parameter] = ''

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_InheritanceType_resulting_InheritanceDefinition

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| property_name | NVARCHAR(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| InheritanceType | INT | yes |  |
| is_force_inherit_empty_source | INT | no |  |
| is_StringAggAllSources | INT | no |  |
| Inheritance_StringAggSeparatorSql | NVARCHAR(4000) | yes |  |
| resulting_InheritanceDefinition | NVARCHAR(4000) | yes |  |
| InheritanceDefinition | NVARCHAR(4000) | yes |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


/*
--The result must be grouped to determine all required calculation variants of an inheritance

SELECT is_StringAggAllSources
 , resulting_InheritanceDefinition
FROM repo.RepoObjectColumn_InheritanceType_resulting_InheritanceDefinition
GROUP BY is_StringAggAllSources
 , resulting_InheritanceDefinition
HAVING (NOT (resulting_InheritanceDefinition IS NULL))



Maybe rename RepoObjectColumnProperty_InheritanceType_resulting_InheritanceDefinition

*/

CREATE VIEW [repo].[RepoObjectColumn_InheritanceType_resulting_InheritanceDefinition]
AS
SELECT
 --
 [inh].[RepoObjectColumn_guid]
 , [inh].[property_name]
 , [inh].[property_value]
 , [inh].[InheritanceType]
 , [is_force_inherit_empty_source] =
 --
 CASE 
  WHEN [InheritanceType] = 14
   THEN 1
  ELSE 0
  END
 , [is_StringAggAllSources] =
 --
 CASE 
  WHEN NOT [Inheritance_StringAggSeparatorSql] IS NULL
   THEN 1
  ELSE 0
  END
 , [Inheritance_StringAggSeparatorSql]
 , [resulting_InheritanceDefinition] =
 --
 CASE 
  WHEN (
    [InheritanceType] = 11
    AND [inh].[property_value] IS NULL
    )
   OR (
    [InheritanceType] = 12
    AND NULLIF([inh].[property_value], '') IS NULL
    )
   OR [InheritanceType] = 13
   OR [InheritanceType] = 14
   THEN ISNULL([InheritanceDefinition], '[repo].[fs_get_RepoObjectColumnProperty_nvarchar]([referenced].[RepoObjectColumn_guid], [referencing].[property_name])')
  END
 --normally the result from [resulting_InheritanceDefinition] should not be empty to be inherited
 --this will avoid existing property_value to be deleted
 --but inheritance can be forced (dangerous!)
 , [inh].[InheritanceDefinition]
 , [inh].[RepoObjectColumn_name]
FROM [repo].[RepoObjectColumn_InheritanceType_InheritanceDefinition] AS inh

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_MissingSource_TypeV

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| RepoObjectColumn_name | NVARCHAR(128) | no |  |
| SysObjectColumn_name | NVARCHAR(128) | no |  |
| SysObjectColumn_column_id | INT | yes |  |
| Repo_default_definition | NVARCHAR(MAX) | yes |  |
| Repo_default_is_system_named | BIT | yes |  |
| Repo_default_name | NVARCHAR(128) | yes |  |
| Repo_definition | NVARCHAR(MAX) | yes |  |
| Repo_generated_always_type | TINYINT | no |  |
| Repo_graph_type | INT | yes |  |
| Repo_is_computed | BIT | no |  |
| Repo_is_identity | BIT | no |  |
| Repo_is_nullable | BIT | yes |  |
| Repo_is_persisted | BIT | yes |  |
| Repo_seed_value | SQL_VARIANT | yes |  |
| Repo_increment_value | SQL_VARIANT | yes |  |
| Repo_user_type_name | NVARCHAR(128) | yes |  |
| Repo_user_type_fullname | NVARCHAR(128) | yes |  |
| Repo_uses_database_collation | BIT | yes |  |
| is_SysObjectColumn_missing | BIT | yes |  |
| persistence_source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_Count | INT | yes |  |
| is_query_plan_expression | BIT | yes |  |
| has_different_sys_names | BIT | yes |  |
| is_RepoObjectColumn_name_uniqueidentifier | INT | no |  |
| is_SysObjectColumn_name_uniqueidentifier | INT | no |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| SysObject_fullname | NVARCHAR(261) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObjectColumn_MissingSource_TypeV]
AS
--
SELECT [roc].[RepoObjectColumn_guid]
 , [roc].[RepoObject_guid]
 , [roc].[RepoObjectColumn_name]
 , [roc].[SysObjectColumn_name]
 , [roc].[SysObjectColumn_column_id]
 , [roc].[Repo_default_definition]
 , [roc].[Repo_default_is_system_named]
 , [roc].[Repo_default_name]
 , [roc].[Repo_definition]
 , [roc].[Repo_generated_always_type]
 , [roc].[Repo_graph_type]
 , [roc].[Repo_is_computed]
 , [roc].[Repo_is_identity]
 , [roc].[Repo_is_nullable]
 , [roc].[Repo_is_persisted]
 , [roc].[Repo_seed_value]
 , [roc].[Repo_increment_value]
 , [roc].[Repo_user_type_name]
 , [roc].[Repo_user_type_fullname]
 , [roc].[Repo_uses_database_collation]
 , [roc].[is_SysObjectColumn_missing]
 , [roc].[persistence_source_RepoObjectColumn_guid]
 , [roc].[Referencing_Count]
 , [roc].[is_query_plan_expression]
 , [roc].[has_different_sys_names]
 , [roc].[is_RepoObjectColumn_name_uniqueidentifier]
 , [roc].[is_SysObjectColumn_name_uniqueidentifier]
 , [ro].[RepoObject_fullname]
 , [ro].[SysObject_fullname]
FROM [repo].[RepoObjectColumn] AS roc
INNER JOIN [repo].[RepoObject] AS ro
 ON ro.[RepoObject_guid] = roc.[RepoObject_guid]
WHERE
 --view
 [ro].[SysObject_type] = 'V'
 AND NOT EXISTS (
  SELECT 1
  FROM [repo].[RepoObjectColumn_reference_union] AS [roc_r]
  WHERE [roc_r].[referencing_RepoObject_guid] = [roc].[RepoObject_guid]
   AND [roc_r].[referencing_RepoObjectColumn_guid] = [roc].[RepoObjectColumn_guid]
   AND (
    [roc_r].[is_referenced_object] = 1
    OR [roc_r].[is_referencing_object_equal_referenced_object] = 1
    )
  )
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_BySamePredecessors

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | yes |  |
| referencing_minor_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_schema_name | NVARCHAR(128) | no |  |
| referencing_entity_name | NVARCHAR(128) | no |  |
| referencing_column_name | NVARCHAR(128) | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_column_name | NVARCHAR(128) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(37) | no |  |
| is_hidden | BIT | yes |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
repo.RepoObjectColumn_reference__first_result_set
for view columns the referenced columns in a predecessor table is shown, not the referenced colum in a predecessor view
but we are looking for the referenced column in a predecessor view

example

create view view_1
as
select
aaa
from table_1

create view view_2
as
select
aaa
from view_1

repo.RepoObjectColumn_reference__first_result_set result in 2 columns references
referencing -> referenced

dbo.view_1.aaa -> dbo.table_1.aaa : roc_r_t1
dbo.view_2.aaa -> dbo.table_1.aaa : roc_r_t2


we combine with object reference ro_r

view_2 -> view_1

We are looking for common predecessors:
dbo.table_1.aaa

and we get what we need:
dbo.view_2.aaa -> dbo.view_1.aaa

*/
CREATE VIEW [repo].[RepoObjectColumn_reference_BySamePredecessors]
AS
--
SELECT [roc_r_t2].[referencing_id]
 , [roc_r_t2].[referencing_minor_id]
 , [roc_r_t2].[referencing_node_id]
 , [roc_r_t2].[referencing_RepoObject_guid]
 , [roc_r_t2].[referencing_RepoObjectColumn_guid]
 , [roc_r_t2].[referencing_type]
 , [roc_r_t2].[referencing_schema_name]
 , [roc_r_t2].[referencing_entity_name]
 , [roc_r_t2].[referencing_column_name]
 , [roc_r_t1].[referencing_id] AS [referenced_id]
 , [roc_r_t1].[referencing_minor_id] AS [referenced_minor_id]
 , [roc_r_t1].[referencing_node_id] AS [referenced_node_id]
 , [ro_r].[referenced_RepoObject_guid]
 , [roc_r_t1].[referencing_RepoObjectColumn_guid] AS [referenced_RepoObjectColumn_guid]
 , [ro_r].[referenced_schema_name]
 , [ro_r].[referenced_entity_name]
 , [roc_r_t1].[referencing_column_name] AS [referenced_column_name]
 , [ro_r].[referenced_type]
 , [roc_r_t2].[InformationSource]
 , [roc_r_t2].[is_hidden]
 , [is_computed] = CAST(0 AS BIT)
 , [definition] = CAST(NULL AS NVARCHAR(MAX))
 , [is_referencing_object_equal_referenced_object] = CAST(CASE 
   WHEN [roc_r_t2].[referencing_RepoObject_guid] = [ro_r].[referenced_RepoObject_guid]
    THEN 1
   ELSE 0
   END AS BIT)
 , [is_referenced_object] = CAST(1 AS BIT)
FROM repo.[RepoObject_reference_union] AS ro_r
INNER JOIN repo.[RepoObjectColumn_reference_FirstResultSet] AS roc_r_t2
 ON ro_r.referencing_RepoObject_guid = roc_r_t2.referencing_RepoObject_guid
INNER JOIN repo.[RepoObjectColumn_reference_FirstResultSet] AS roc_r_t1
 ON ro_r.referenced_RepoObject_guid = roc_r_t1.referencing_RepoObject_guid
  AND roc_r_t2.referenced_RepoObject_guid = roc_r_t1.referenced_RepoObject_guid
  AND roc_r_t2.referenced_RepoObjectColumn_guid = roc_r_t1.referenced_RepoObjectColumn_guid
--we don't care about [is_hidden] columns or other possible not required entries
--and to ensure all results can be used we ensure RepoObjectColum exists
WHERE NOT [roc_r_t2].[referencing_RepoObjectColumn_guid] IS NULL
 AND NOT [roc_r_t1].[referencing_RepoObjectColumn_guid] IS NULL
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_FirstResultSet

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | yes |  |
| referencing_minor_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_schema_name | NVARCHAR(128) | no |  |
| referencing_entity_name | NVARCHAR(128) | no |  |
| referencing_column_name | NVARCHAR(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_column_name | NVARCHAR(128) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(37) | no |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |
| is_hidden | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
--"common" references
--these should be "common" columns in views, not containing expressions
--Attention: views on views are "resolved" like views on the underlaying tables!
--it looks like we don't get references between views here!
CREATE VIEW [repo].[RepoObjectColumn_reference_FirstResultSet]
AS
--
SELECT [ro].[SysObject_id] AS [referencing_id]
 , [roc].[SysObjectColumn_column_id] AS [referencing_minor_id]
 , CAST([ro].[SysObject_id] AS BIGINT) * 10000 + [roc].[SysObjectColumn_column_id] AS [referencing_node_id]
 , [roc2].[SysObject_id] AS [referenced_id]
 , [roc2].[SysObjectColumn_column_id] AS [referenced_minor_id]
 , CAST([roc2].[SysObject_id] AS BIGINT) * 10000 + [roc2].[SysObjectColumn_column_id] AS [referenced_node_id]
 , [ros].[RepoObject_guid] AS [referencing_RepoObject_guid]
 , [roc].[RepoObjectColumn_guid] AS [referencing_RepoObjectColumn_guid]
 , [roc2].[RepoObject_guid] AS [referenced_RepoObject_guid]
 , [roc2].[RepoObjectColumn_guid] AS [referenced_RepoObjectColumn_guid]
 , [ro].[SysObject_type] AS [referencing_type]
 , [ro].[SysObject_schema_name] AS [referencing_schema_name]
 , [ro].[SysObject_name] AS [referencing_entity_name]
 , [ros].[target_column_name] AS [referencing_column_name]
 , [ros].[source_schema_name] AS [referenced_schema_name]
 , [ros].[source_table_name] AS [referenced_entity_name]
 , [ros].[source_column_name] AS [referenced_column_name]
 , [roc2].[SysObject_type] AS [referenced_type]
 , [InformationSource] = 'sys.dm_exec_describe_first_result_set'
 , [is_referencing_object_equal_referenced_object] = CAST(CASE 
   WHEN [ros].[RepoObject_guid] = [roc2].[RepoObject_guid]
    THEN 1
   ELSE 0
   END AS BIT)
 --Flag, if the [referenced_RepoObject_guid] is a referenced object in [repo].[RepoObject_reference__union]
 , [is_referenced_object] = (
  SELECT TOP 1 CAST(1 AS BIT)
  FROM [repo].[RepoObject_reference_union] AS [ro_r]
  WHERE [ro_r].[referencing_RepoObject_guid] = [ros].[RepoObject_guid]
   AND [ro_r].[referenced_RepoObject_guid] = [roc2].[RepoObject_guid]
  )
 , [ros].[is_hidden]
FROM repo.RepoObjectSource_FirstResultSet AS ros
INNER JOIN repo.RepoObject AS ro
 ON ros.RepoObject_guid = ro.RepoObject_guid
LEFT JOIN repo.[RepoObjectColumn_gross] AS roc
 ON ro.SysObject_schema_name = roc.SysObject_schema_name
  AND ro.SysObject_name = roc.SysObject_name
  AND ros.target_column_name = roc.SysObjectColumn_name
LEFT JOIN repo.[RepoObjectColumn_gross] AS roc2
 ON ros.source_schema_name = roc2.SysObject_schema_name
  AND ros.source_table_name = roc2.SysObject_name
  AND ros.source_column_name = roc2.SysObjectColumn_name
  AND ros.source_server_name IS NULL
--exclude reference on self (target column = source column)
WHERE NOT (
  [ro].[SysObject_schema_name] = [ros].[source_schema_name]
  AND [ro].[SysObject_name] = [ros].[source_table_name]
  AND [ros].[target_column_name] = [ros].[source_column_name]
  )
 --exclude source 'sys 
 --todo: make this an option via parameter
 AND NOT [ros].[source_schema_name] = 'sys'
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_Persistence

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | yes |  |
| referencing_minor_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_schema_name | NVARCHAR(128) | no |  |
| referencing_entity_name | NVARCHAR(128) | no |  |
| referencing_column_name | NVARCHAR(128) | no |  |
| referenced_schema_name | NVARCHAR(128) | no |  |
| referenced_entity_name | NVARCHAR(128) | no |  |
| referenced_column_name | NVARCHAR(128) | no |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(27) | no |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObjectColumn_reference_Persistence]
AS
--
SELECT [referencing_id] = [ro_t].[SysObject_id]
 , [referencing_minor_id] = [roc_t].[SysObjectColumn_column_id]
 , [referencing_node_id] = [ro_t].[node_id]
 , [referenced_id] = [ro_s].[SysObject_id]
 , [referenced_minor_id] = [roc_s].[SysObjectColumn_column_id]
 , [referenced_node_id] = [ro_s].[node_id]
 , [referencing_RepoObject_guid] = [rop].[target_RepoObject_guid]
 , [referencing_RepoObjectColumn_guid] = [roc_t].[RepoObjectColumn_guid]
 , [referenced_RepoObject_guid] = [rop].[source_RepoObject_guid]
 , [referenced_RepoObjectColumn_guid] = [roc_s].[RepoObjectColumn_guid]
 --Target = referencing: Repo Names or Sys Names?
 --it is possible, that only Repo Objects exists, but they are not yet in the database
 --or they could have other names in the database
 --if they doesn't exist in the database guid are used as names
 -- => Sys Names are fine
 , [referencing_type] = [ro_t].[SysObject_type]
 , [referencing_schema_name] = [ro_t].[SysObject_schema_name]
 , [referencing_entity_name] = [ro_t].[SysObject_name]
 , [referencing_column_name] = [roc_t].[SysObjectColumn_name]
 --Source = referenced: Source should exists and we should use Sys Names
 , [referenced_schema_name] = [ro_s].[SysObject_schema_name]
 , [referenced_entity_name] = [ro_s].[SysObject_name]
 , [referenced_column_name] = [roc_s].[SysObjectColumn_name]
 , [referenced_type] = [ro_s].[SysObject_type]
 , [InformationSource] = 'repo.RepoObject_persistence'
 --persisted basic columns which are inherited are not computed
 , [is_computed] = CAST(0 AS BIT)
 , [definition] = CAST(NULL AS NVARCHAR(MAX))
 , [is_referencing_object_equal_referenced_object] = CAST(CASE 
   WHEN [rop].[target_RepoObject_guid] = [rop].[source_RepoObject_guid]
    THEN 1
   ELSE 0
   END AS BIT)
 , [is_referenced_object] = CAST(1 AS BIT)
FROM repo.RepoObject_persistence AS rop
INNER JOIN repo.RepoObject AS ro_s
 ON ro_s.RepoObject_guid = rop.source_RepoObject_guid
INNER JOIN repo.RepoObject AS ro_t
 ON ro_t.RepoObject_guid = rop.target_RepoObject_guid
INNER JOIN repo.RepoObjectColumn AS roc_s
 ON roc_s.RepoObject_guid = rop.source_RepoObject_guid
INNER JOIN repo.RepoObjectColumn AS roc_t
 ON roc_t.RepoObject_guid = rop.target_RepoObject_guid
  AND roc_t.[persistence_source_RepoObjectColumn_guid] = roc_s.RepoObjectColumn_guid
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_QueryPlan

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | yes |  |
| referencing_minor_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_schema_name | NVARCHAR(128) | no |  |
| referencing_entity_name | NVARCHAR(128) | no |  |
| referencing_column_name | NVARCHAR(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_column_name | NVARCHAR(128) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(10) | no |  |
| source_schema_name_quoted | NVARCHAR(128) | yes |  |
| source_table_name_quoted | NVARCHAR(128) | yes |  |
| is_target_column_name_expression | BIT | yes |  |
| is_source_column_name_expression | BIT | yes |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObjectColumn_reference_QueryPlan]
AS
--
SELECT [ro].[SysObject_id] AS [referencing_id]
 , [roc].[SysObjectColumn_column_id] AS [referencing_minor_id]
 , CAST([ro].[SysObject_id] AS BIGINT) * 10000 + [roc].[SysObjectColumn_column_id] AS [referencing_node_id]
 , [roc2].[SysObject_id] AS [referenced_id]
 , [roc2].[SysObjectColumn_column_id] AS [referenced_minor_id]
 , CAST([roc2].[SysObject_id] AS BIGINT) * 10000 + [roc2].[SysObjectColumn_column_id] AS [referenced_node_id]
 , [ros].[RepoObject_guid] AS [referencing_RepoObject_guid]
 , [roc].[RepoObjectColumn_guid] AS [referencing_RepoObjectColumn_guid]
 , [roc2].[RepoObject_guid] AS [referenced_RepoObject_guid]
 , [roc2].[RepoObjectColumn_guid] AS [referenced_RepoObjectColumn_guid]
 , [ro].[SysObject_type] AS [referencing_type]
 , [ro].[SysObject_schema_name] AS [referencing_schema_name]
 , [ro].[SysObject_name] AS [referencing_entity_name]
 , [ros].[target_column_name] AS [referencing_column_name]
 , [roc2].[SysObject_schema_name] AS [referenced_schema_name]
 , [roc2].[SysObject_name] AS [referenced_entity_name]
 , [ros].[source_column_name] AS [referenced_column_name]
 , [roc2].[SysObject_type] AS [referenced_type]
 , [InformationSource] = 'query plan'
 ----, [ros].[source_server_name] AS      [source_server_name]
 ----, [repo].[fs_dwh_database_name]() AS [source_database_name]
 --, [ros].[source_database_name] AS      [source_database_name_quoted]
 , [ros].[source_schema_name] AS [source_schema_name_quoted]
 , [ros].[source_table_name] AS [source_table_name_quoted]
 , [ros].[is_target_column_name_expression]
 , [ros].[is_source_column_name_expression]
 , [is_computed] = CAST(CASE 
   WHEN [ros].[is_target_column_name_expression] = 1
    OR [ros].[is_source_column_name_expression] = 1
    THEN 1
   ELSE 0
   END AS BIT)
 , [definition] = CAST(NULL AS NVARCHAR(MAX))
 , [is_referencing_object_equal_referenced_object] = CAST(CASE 
   WHEN [ros].[RepoObject_guid] = [roc2].[RepoObject_guid]
    THEN 1
   ELSE 0
   END AS BIT)
 , [is_referenced_object] = (
  SELECT TOP 1 CAST(1 AS BIT)
  FROM [repo].[RepoObject_reference_union] AS [ro_r]
  WHERE [ro_r].[referencing_RepoObject_guid] = [ros].[RepoObject_guid]
   AND [ro_r].[referenced_RepoObject_guid] = [roc2].[RepoObject_guid]
  )
FROM repo.RepoObjectSource_QueryPlan AS ros
INNER JOIN repo.RepoObject AS ro
 ON ros.RepoObject_guid = ro.RepoObject_guid
LEFT JOIN repo.[RepoObjectColumn_gross] AS roc
 ON ro.SysObject_schema_name = roc.SysObject_schema_name
  AND ro.SysObject_name = roc.SysObject_name
  AND ros.target_column_name = roc.SysObjectColumn_name
LEFT JOIN repo.[RepoObjectColumn_gross] AS roc2
 ON ros.source_column_name = roc2.SysObjectColumn_name
  AND ros.source_server_name IS NULL
  AND (
   (
    ros.source_database_name = QUOTENAME([repo].[fs_dwh_database_name]())
    AND ros.source_schema_name = QUOTENAME(roc2.SysObject_schema_name)
    AND ros.source_table_name = QUOTENAME(roc2.SysObject_name)
    )
   --if source_column is expression like 'Expr1006' then these are missing: ros.source_schema_name, ros.source_table_name
   --we should use these names from the target column (which is in the same object)
   OR (
    ros.[is_source_column_name_expression] = 1
    AND [ro].[SysObject_schema_name] = roc2.SysObject_schema_name
    AND [ro].[SysObject_name] = roc2.SysObject_name
    )
   )
--
--
WHERE
 --exclude reference on self (target column = source column)
 NOT (
  [ro].[SysObject_schema_name] = [roc2].[SysObject_schema_name]
  AND [ro].[SysObject_name] = [roc2].[SysObject_name]
  AND [ros].[target_column_name] = [ros].[source_column_name]
  )
 ------
 --AND --
 --[ros].[RepoObject_guid] = '6076940B-2B57-EB11-84D8-A81E8446D5B0'
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_SqlExpressionDependencies

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | no |  |
| referencing_minor_id | INT | no |  |
| referencing_node_id | BIGINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | no |  |
| referenced_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_schema_name | NVARCHAR(128) | yes |  |
| referencing_entity_name | NVARCHAR(128) | yes |  |
| referencing_column_name | SYSNAME(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_column_name | SYSNAME(128) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(31) | no |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObjectColumn_reference_SqlExpressionDependencies]
AS
--
SELECT [sed].[referencing_id]
 , [sed].[referencing_minor_id]
 , CAST([sed].[referencing_id] AS BIGINT) * 10000 + [sed].[referencing_minor_id] AS [referencing_node_id]
 , [sed].[referenced_id]
 , [sed].[referenced_minor_id]
 , CAST([sed].[referenced_id] AS BIGINT) * 10000 + [sed].[referenced_minor_id] AS [referenced_node_id]
 , [sed].[referencing_RepoObject_guid]
 , [sed].[referencing_RepoObjectColumn_guid]
 , [sed].[referenced_RepoObject_guid]
 , [sed].[referenced_RepoObjectColumn_guid]
 , [sed].[referencing_type]
 , [sed].[referencing_schema_name]
 , [sed].[referencing_entity_name]
 , [sed].[referencing_column_name]
 , [sed].[referenced_schema_name]
 , [sed].[referenced_entity_name]
 , [sed].[referenced_column_name]
 , [sed].[referenced_type]
 , [InformationSource] = 'sys.sql_expression_dependencies'
 , [sed].[is_computed]
 , [sed].[definition]
 , [is_referencing_object_equal_referenced_object] = CAST(CASE 
   WHEN [sed].[referencing_RepoObject_guid] = [sed].[referenced_RepoObject_guid]
    THEN 1
   ELSE 0
   END AS BIT)
 --Flag, if the [referenced_RepoObject_guid] is a referenced object in [repo].[RepoObject_reference__union]
 , [is_referenced_object] = (
  SELECT TOP 1 CAST(1 AS BIT)
  FROM [repo].[RepoObject_reference_union] AS [ro_r]
  WHERE [ro_r].[referencing_RepoObject_guid] = [sed].[referencing_RepoObject_guid]
   AND [ro_r].[referenced_RepoObject_guid] = [sed].[referenced_RepoObject_guid]
  )
--, [sed].[referenced_server_name]
--, [sed].[referenced_database_name]
--, [sed].[referenced_class]
--, [sed].[referencing_class]
--, [sed].[referencing_class_desc]
--, [sed].[referenced_class_desc]
--, [sed].[referencing_type_desciption]
--, [sed].[referenced_type_desciption]
--, [sed].[is_schema_bound_reference]
--, [sed].[is_caller_dependent]
--, [sed].[is_ambiguous]
FROM repo_sys.sql_expression_dependencies AS sed
WHERE
 --column level
 [sed].[referencing_minor_id] <> 0
 AND [sed].[referenced_minor_id] <> 0
 --exclude virtual objects (like expressions used in procedures)
 --or objects without extended properties (like triggers)
 --currently:
 --[RepoObject_guid] = [sed].[referencing_RepoObject_guid]
 --and [sed].[referencing_RepoObject_guid] = SysObject_RepoObject_guid
 --these are RepoObject_guid storred in extended properties
 AND NOT [sed].[referencing_RepoObject_guid] IS NULL
 AND NOT [sed].[referenced_RepoObject_guid] IS NULL
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_SqlModules

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | yes |  |
| referencing_minor_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_schema_name | NVARCHAR(128) | no |  |
| referencing_entity_name | NVARCHAR(128) | no |  |
| referencing_column_name | NVARCHAR(128) | no |  |
| referenced_schema_name | NVARCHAR(128) | no |  |
| referenced_entity_name | NVARCHAR(128) | no |  |
| referenced_column_name | NVARCHAR(128) | no |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(27) | no |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObjectColumn_reference_SqlModules]
AS
--
SELECT [referencing_id] = [ro_t].[SysObject_id]
 , [referencing_minor_id] = [roc_t].[SysObjectColumn_column_id]
 , [referencing_node_id] = [ro_t].[node_id]
 , [referenced_id] = [ro_s].[SysObject_id]
 , [referenced_minor_id] = [roc_s].[SysObjectColumn_column_id]
 , [referenced_node_id] = [ro_s].[node_id]
 , [referencing_RepoObject_guid] = [T1].[RepoObject_guid]
 , [referencing_RepoObjectColumn_guid] = [T1].[RepoObjectColumn_guid]
 , [referenced_RepoObject_guid] = [T1].[source_RepoObject_guid]
 , [referenced_RepoObjectColumn_guid] = [T1].[source_RepoObjectColumn_guid]
 --Target = referencing: Repo Names or Sys Names?
 --it is possible, that only Repo Objects exists, but they are not yet in the database
 --or they could have other names in the database
 --if they doesn't exist in the database guid are used as names
 -- => Sys Names are fine
 , [referencing_type] = [ro_t].[SysObject_type]
 , [referencing_schema_name] = [ro_t].[SysObject_schema_name]
 , [referencing_entity_name] = [ro_t].[SysObject_name]
 , [referencing_column_name] = [roc_t].[SysObjectColumn_name]
 --Source = referenced: Source should exists and we should use Sys Names
 , [referenced_schema_name] = [ro_s].[SysObject_schema_name]
 , [referenced_entity_name] = [ro_s].[SysObject_name]
 , [referenced_column_name] = [roc_s].[SysObjectColumn_name]
 , [referenced_type] = [ro_s].[SysObject_type]
 , [InformationSource] = 'repo.RepoObject_persistence'
 --persisted basic columns which are inherited are not computed
 , [is_computed] = CAST(0 AS BIT)
 , [definition] = [T1].[normalized]
 , [is_referencing_object_equal_referenced_object] = CAST(CASE 
   WHEN [T1].[RepoObject_guid] = [T1].[source_RepoObject_guid]
    THEN 1
   ELSE 0
   END AS BIT)
 , [is_referenced_object] = CAST(1 AS BIT)
 --for easy error check
 , [T1].[SysObject_fullname]
FROM [repo].[RepoObject_SqlModules_79_reference_union] AS T1
INNER JOIN repo.RepoObject AS ro_s
 ON ro_s.RepoObject_guid = T1.[source_RepoObject_guid]
INNER JOIN repo.RepoObject AS ro_t
 ON ro_t.RepoObject_guid = T1.[RepoObject_guid]
INNER JOIN repo.RepoObjectColumn AS roc_s
 ON roc_s.[RepoObjectColumn_guid] = T1.[source_RepoObjectColumn_guid]
INNER JOIN repo.RepoObjectColumn AS roc_t
 ON roc_t.[RepoObjectColumn_guid] = T1.[RepoObjectColumn_guid]

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_reference_union

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_column_name | NVARCHAR(128) | yes |  |
| referencing_schema_name | NVARCHAR(128) | yes |  |
| referencing_entity_name | NVARCHAR(128) | yes |  |
| referencing_column_name | NVARCHAR(128) | yes |  |
| referencing_id | INT | yes |  |
| referencing_minor_id | INT | yes |  |
| referencing_node_id | BIGINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_type | CHAR(2) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| InformationSource | VARCHAR(31) | no |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_referencing_object_equal_referenced_object | BIT | yes |  |
| is_referenced_object | BIT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
check

SELECT
       [referencing_id]
     , [referencing_minor_id]
     , [InformationSource]
     , [referencing_schema_name]
     , [referencing_entity_name]
     , [referencing_column_name]
     , [referencing_type]
     , [referenced_schema_name]
     , [referenced_entity_name]
     , [referenced_column_name]
     , [referenced_type]
     , [referencing_RepoObject_guid]
     , [referencing_RepoObjectColumn_guid]
     , [referenced_RepoObject_guid]
     , [referenced_RepoObjectColumn_guid]
--, [referencing_node_id]
--, [referenced_id]
--, [referenced_minor_id]
--, [referenced_node_id]
FROM
     [repo].[RepoObjectColumn_reference__union]
ORDER BY
         [referencing_id]
       , [referencing_minor_id]
       , [referenced_id]
       , [referenced_minor_id]
       , [InformationSource]


*/
CREATE VIEW [repo].[RepoObjectColumn_reference_union]
AS
--
--repo.RepoObjectColumn_reference__sql_expression_dependencies
--contains calculated columns
--maybe colums in case of SCHEMA_BINDING (not tested)
SELECT
 --
 [referenced_schema_name]
 , [referenced_entity_name]
 , [referenced_column_name]
 , [referencing_schema_name]
 , [referencing_entity_name]
 , [referencing_column_name]
 , [referencing_id]
 , [referencing_minor_id]
 , [referencing_node_id]
 , [referenced_id]
 , [referenced_minor_id]
 , [referenced_node_id]
 , [referencing_RepoObject_guid]
 , [referencing_RepoObjectColumn_guid]
 , [referenced_RepoObject_guid]
 , [referenced_RepoObjectColumn_guid]
 , [referencing_type]
 , [referenced_type]
 , [InformationSource]
 , [is_computed]
 , [definition]
 , [is_referencing_object_equal_referenced_object]
 , [is_referenced_object]
FROM repo.[RepoObjectColumn_reference_SqlExpressionDependencies]
--[repo].[RepoObjectColumn_reference__persistence]
--contains virtual references for persistence tables
--these references can't exist in the real database but only in the repository

UNION ALL

SELECT
 --
 [referenced_schema_name]
 , [referenced_entity_name]
 , [referenced_column_name]
 , [referencing_schema_name]
 , [referencing_entity_name]
 , [referencing_column_name]
 , [referencing_id]
 , [referencing_minor_id]
 , [referencing_node_id]
 , [referenced_id]
 , [referenced_minor_id]
 , [referenced_node_id]
 , [referencing_RepoObject_guid]
 , [referencing_RepoObjectColumn_guid]
 , [referenced_RepoObject_guid]
 , [referenced_RepoObjectColumn_guid]
 , [referencing_type]
 , [referenced_type]
 , [InformationSource]
 , [is_computed]
 , [definition]
 , [is_referencing_object_equal_referenced_object]
 , [is_referenced_object]
FROM [repo].[RepoObjectColumn_reference_Persistence]

UNION ALL

SELECT
 --
 [referenced_schema_name]
 , [referenced_entity_name]
 , [referenced_column_name]
 , [referencing_schema_name]
 , [referencing_entity_name]
 , [referencing_column_name]
 , [referencing_id]
 , [referencing_minor_id]
 , [referencing_node_id]
 , [referenced_id]
 , [referenced_minor_id]
 , [referenced_node_id]
 , [referencing_RepoObject_guid]
 , [referencing_RepoObjectColumn_guid]
 , [referenced_RepoObject_guid]
 , [referenced_RepoObjectColumn_guid]
 , [referencing_type]
 , [referenced_type]
 , [InformationSource]
 , [is_computed]
 , [definition]
 , [is_referencing_object_equal_referenced_object]
 , [is_referenced_object]
FROM [repo].[RepoObjectColumn_reference_SqlModules]
 --UNION ALL
 ----repo.RepoObjectColumn_reference__first_result_set
 ----"common" references
 ----these should be "common" columns in views, not containing expressions
 ----Attention: views on views are "resolved" like views on the underlaying tables!
 ----it looks like we don't get references between views here!
 ----we filter by [is_referenced_object] = 1
 ----to get only referenced columns from referenced objects
 --SELECT [referencing_id]
 -- , [referencing_minor_id]
 -- , [referencing_node_id]
 -- , [referenced_id]
 -- , [referenced_minor_id]
 -- , [referenced_node_id]
 -- , [referencing_RepoObject_guid]
 -- , [referencing_RepoObjectColumn_guid]
 -- , [referenced_RepoObject_guid]
 -- , [referenced_RepoObjectColumn_guid]
 -- , [referencing_type]
 -- , [referencing_schema_name]
 -- , [referencing_entity_name]
 -- , [referencing_column_name]
 -- , [referenced_schema_name]
 -- , [referenced_entity_name]
 -- , [referenced_column_name]
 -- , [referenced_type]
 -- , [InformationSource]
 -- , [is_computed] = CAST(0 AS BIT)
 -- , [definition] = NULL
 -- , [is_referencing_object_equal_referenced_object]
 -- , [is_referenced_object]
 --FROM repo.[RepoObjectColumn_reference_FirstResultSet]
 --WHERE [is_referenced_object] = 1
 --UNION ALL
 --SELECT [referencing_id]
 -- , [referencing_minor_id]
 -- , [referencing_node_id]
 -- , [referenced_id]
 -- , [referenced_minor_id]
 -- , [referenced_node_id]
 -- , [referencing_RepoObject_guid]
 -- , [referencing_RepoObjectColumn_guid]
 -- , [referenced_RepoObject_guid]
 -- , [referenced_RepoObjectColumn_guid]
 -- , [referencing_type]
 -- , [referencing_schema_name]
 -- , [referencing_entity_name]
 -- , [referencing_column_name]
 -- , [referenced_schema_name]
 -- , [referenced_entity_name]
 -- , [referenced_column_name]
 -- , [referenced_type]
 -- , [InformationSource]
 -- , [is_computed] = CAST(0 AS BIT)
 -- , [definition] = NULL
 -- , [is_referencing_object_equal_referenced_object]
 -- , [is_referenced_object]
 --FROM repo.[RepoObjectColumn_reference_BySamePredecessors]
 ---- additional references for view columns, which are not common columns
 ----the result is not yet OK
 --UNION ALL
 --SELECT [referencing_id]
 -- , [referencing_minor_id]
 -- , [referencing_node_id]
 -- , [referenced_id]
 -- , [referenced_minor_id]
 -- , [referenced_node_id]
 -- , [referencing_RepoObject_guid]
 -- , [referencing_RepoObjectColumn_guid]
 -- , [referenced_RepoObject_guid]
 -- , [referenced_RepoObjectColumn_guid]
 -- , [referencing_type]
 -- , [referencing_schema_name]
 -- , [referencing_entity_name]
 -- , [referencing_column_name]
 -- , [referenced_schema_name]
 -- , [referenced_entity_name]
 -- , [referenced_column_name]
 -- , [referenced_type]
 -- , [InformationSource]
 -- , [is_computed]
 -- , [definition]
 -- , [is_referencing_object_equal_referenced_object]
 -- , [is_referenced_object]
 --FROM [repo].[RepoObjectColumn_reference_QueryPlan] AS roc_r
 --WHERE
 -- --only views
 -- [referencing_type] = 'V'
 -- --not common, they should be an expresssion or based on an expression
 -- AND [is_computed] = 1
 -- AND (
 --  --these are expressions, which belongs to columns in an referenced object
 --  --we want to include view_1.aaa -> table_1.aaa
 --  --but this should be excluded: view_2.aaa -> table_1.aaa
 --  [is_referenced_object] = 1
 --  --expressions can reference a predecessor of a referenced object
 --  --but how to handle these columns?
 --  --for example:
 --  --dbo.view_2.Expr2005 -> dbo.table_1.bbb
 --  --but the direct expression should be dbo.view_2.bbb -> dbo.view_1.bbb
 --  --we could try to use same-predecessor-logic
 --  OR [is_target_column_name_expression] = 1
 --  --these are references to expressions, and by definition they are virtually created in the referenced object
 --  OR is_referencing_object_equal_referenced_object = 1
 --  --
 --  )
 -- --exclude references from the query above
 -- --if referenced columns exists there we will not use any possible expression
 -- --because an expression sometimes is also used in case the table column is some special, for example if it is an Auto ID
 -- AND NOT EXISTS (
 --  SELECT 1
 --  FROM [repo].[RepoObjectColumn_reference_FirstResultSet] AS [roc_r_common]
 --  WHERE [is_referenced_object] = 1
 --   AND [roc_r_common].[referencing_RepoObject_guid] = [roc_r].[referencing_RepoObject_guid]
 --   AND [roc_r_common].[referencing_RepoObjectColumn_guid] = [roc_r].[referencing_RepoObjectColumn_guid]
 --  )
 -- --exclude references from the another query above
 -- AND NOT EXISTS (
 --  SELECT 1
 --  FROM [repo].[RepoObjectColumn_reference_BySamePredecessors] AS [roc_r_derived]
 --  WHERE [roc_r_derived].[referencing_RepoObject_guid] = [roc_r].[referencing_RepoObject_guid]
 --   AND [roc_r_derived].[referencing_RepoObjectColumn_guid] = [roc_r].[referencing_RepoObjectColumn_guid]
 --  )

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_ReferenceTree

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| Referenced_fullname | NVARCHAR(261) | yes |  |
| Referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| Referenced_type | CHAR(2) | yes |  |
| ReferencedColumn_fullname | NVARCHAR(520) | yes |  |
| ReferencedColumn_type | NVARCHAR(128) | yes |  |
| Referenced_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_fullname | NVARCHAR(261) | yes |  |
| Referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_type | CHAR(2) | yes |  |
| ReferencingColumn_fullname | NVARCHAR(520) | yes |  |
| ReferencingColumn_type | NVARCHAR(128) | yes |  |
| Referencing_guid | UNIQUEIDENTIFIER | yes |  |
| Referenced_Depth | INT | yes |  |
| Referencing_Depth | INT | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[RepoObjectColumn_ReferenceTree]
AS
SELECT [tree].*
FROM [repo].[RepoObjectColumn] AS roc
CROSS APPLY [repo].[ftv_RepoObjectColumn_ReferenceTree](roc.[RepoObjectColumn_guid], 1000, 1000) AS tree

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumn_RelationScript

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| DbmlRelation | NVARCHAR(786) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[RepoObjectColumn_RelationScript]
AS
--
SELECT DISTINCT
 --
 [referenced_RepoObject_guid]
 , [referencing_RepoObject_guid]
 , [DbmlRelation] = CONCAT (
  'Ref'
  , ': '
  , QUOTENAME(QUOTENAME([referencing_schema_name]) + '.' + QUOTENAME([referencing_entity_name]), '"')
  , '."'
  , [referencing_column_name]
  , '"'
  --<: one-to-many. E.g: users.id < posts.user_id
  -->: many-to-one. E.g: posts.user_id > users.id
  ---: one-to-one. E.g: users.id - user_infos.user_id
  , ' > '
  , QUOTENAME(QUOTENAME([referenced_schema_name]) + '.' + QUOTENAME([referenced_entity_name]), '"')
  , '."'
  , [referenced_column_name]
  , '"'
  )
FROM [repo].[RepoObjectColumn_reference_union] AS rocu
INNER JOIN [repo].[RepoObjectColumn] AS roc1
 ON roc1.RepoObjectColumn_guid = rocu.referencing_RepoObjectColumn_guid
INNER JOIN [repo].[RepoObjectColumn] AS roc2
 ON roc2.RepoObjectColumn_guid = rocu.referenced_RepoObjectColumn_guid
WHERE
 --exclude virtual columns, which have [uniqueidentifier] as name
 [roc1].[is_RepoObjectColumn_name_uniqueidentifier] = 0
 AND [roc2].[is_RepoObjectColumn_name_uniqueidentifier] = 0
 AND [roc1].[is_SysObjectColumn_name_uniqueidentifier] = 0
 AND [roc2].[is_SysObjectColumn_name_uniqueidentifier] = 0
 --AND NOT [referenced_RepoObjectColumn_guid] IS NULL
 --AND NOT [referencing_RepoObjectColumn_guid] IS NULL

```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectColumnProperty_sys_repo

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| property_name | SYSNAME(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| SysObjectColumn_name | NVARCHAR(128) | yes |  |
| RepoObjectColumnProperty_id | INT | yes |  |
| RepoObjectColumnProperty_property_value | SQL_VARIANT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObjectColumnProperty_sys_repo]
AS
--
SELECT [roc].[RepoObjectColumn_guid]
 , [ses].[property_name]
 , [ses].[property_value]
 , [ses].[SysObject_schema_name]
 , [ses].[SysObject_name]
 , [ses].[entity_column_name] AS [SysObjectColumn_name]
 , [link].[RepoObjectColumnProperty_id]
 , [link].[property_value] AS [RepoObjectColumnProperty_property_value]
FROM repo_sys.[ExtendedProperties] AS ses
INNER JOIN repo.RepoObject AS ro
 ON ses.SysObject_schema_name = ro.SysObject_schema_name
  AND ses.SysObject_name = ro.SysObject_name
INNER JOIN repo.RepoObjectColumn AS roc
 ON ro.RepoObject_guid = roc.RepoObject_guid
  AND ses.entity_column_name = roc.SysObjectColumn_name
  AND ses.property_name <> 'RepoObjectColumn_guid'
LEFT JOIN repo.RepoObjectColumnProperty AS link
 ON roc.RepoObjectColumn_guid = link.RepoObjectColumn_guid
  AND [ses].[property_name] = link.[property_name]
```

</details>

[Back to top](#dhw_self)

### repo.RepoObjectProperty_sys_repo

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| property_name | SYSNAME(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| RepoObjectProperty_id | INT | yes |  |
| RepoObjectProperty_property_value | SQL_VARIANT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[RepoObjectProperty_sys_repo]
AS
--
SELECT [ro].[RepoObject_guid]
 , [ses].[property_name]
 , [ses].[property_value]
 , [ses].[SysObject_schema_name]
 , [ses].[SysObject_name]
 , [link].[RepoObjectProperty_id]
 , [link].[property_value] AS [RepoObjectProperty_property_value]
FROM repo_sys.[ExtendedProperties] AS ses
INNER JOIN repo.RepoObject AS ro
 ON ses.SysObject_schema_name = ro.SysObject_schema_name
  AND ses.SysObject_name = ro.SysObject_name
  AND ses.minor_name IS NULL
  AND ses.class = 1 --OBJECT_OR_COLUMN
  --todo: handle class = 3 SCHEMA
  --todo: handle class = 7 INDEX
  AND ses.property_name <> 'RepoObject_guid'
LEFT JOIN repo.RepoObjectProperty AS link
 ON ro.RepoObject_guid = link.RepoObject_guid
  AND [ses].[property_name] = link.[property_name]
```

</details>

[Back to top](#dhw_self)

### repo.SysColumn_RepoObjectColumn_via_guid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_id | INT | no |  |
| SysObject_column_id | INT | no |  |
| is_repo_managed | BIT | yes |  |
| RepoObject_fullname | NVARCHAR(261) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| has_different_sys_names | BIT | yes |  |
| is_query_plan_expression | BIT | yes |  |
| is_RepoObjectColumn_name_uniqueidentifier | INT | yes |  |
| is_SysObjectColumn_missing | BIT | yes |  |
| is_SysObjectColumn_name_uniqueidentifier | INT | yes |  |
| persistence_source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_Count | INT | yes |  |
| Repo_default_definition | NVARCHAR(MAX) | yes |  |
| Repo_default_name | NVARCHAR(128) | yes |  |
| Repo_default_is_system_named | BIT | yes |  |
| Repo_definition | NVARCHAR(MAX) | yes |  |
| Repo_generated_always_type | TINYINT | yes |  |
| Repo_graph_type | INT | yes |  |
| Repo_is_computed | BIT | yes |  |
| Repo_is_identity | BIT | yes |  |
| Repo_is_nullable | BIT | yes |  |
| Repo_is_persisted | BIT | yes |  |
| Repo_seed_value | SQL_VARIANT | yes |  |
| Repo_increment_value | SQL_VARIANT | yes |  |
| Repo_user_type_fullname | NVARCHAR(128) | yes |  |
| Repo_user_type_name | NVARCHAR(128) | yes |  |
| Repo_uses_database_collation | BIT | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObjectColumn_name | NVARCHAR(128) | yes |  |
| SysObjectColumn_column_id | INT | yes |  |
| SysObjectColumn_name | NVARCHAR(128) | yes |  |
| default_definition | NVARCHAR(MAX) | yes |  |
| default_is_system_named | BIT | yes |  |
| default_name | SYSNAME(128) | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| generated_always_type | TINYINT | yes |  |
| graph_type | INT | yes |  |
| is_computed | BIT | no |  |
| is_identity | BIT | no |  |
| is_nullable | BIT | yes |  |
| is_persisted | BIT | yes |  |
| seed_value | SQL_VARIANT | yes |  |
| increment_value | SQL_VARIANT | yes |  |
| SysObject_column_name | SYSNAME(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| SysObject_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_type | CHAR(2) | yes |  |
| user_type_fullname | NVARCHAR(182) | yes |  |
| user_type_name | SYSNAME(128) | yes |  |
| uses_database_collation | BIT | yes |  |
| RowNumberOverName | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[SysColumn_RepoObjectColumn_via_guid]
AS
--
SELECT [sc].[SysObject_id]
 , [sc].[SysObject_column_id]
 , [ro].[is_repo_managed]
 , [ro].[RepoObject_fullname]
 , [ro].[SysObject_fullname]
 , [roc].[has_different_sys_names]
 , [roc].[is_query_plan_expression]
 , [roc].[is_RepoObjectColumn_name_uniqueidentifier]
 , [roc].[is_SysObjectColumn_missing]
 , [roc].[is_SysObjectColumn_name_uniqueidentifier]
 , [roc].[persistence_source_RepoObjectColumn_guid]
 , [roc].[Referencing_Count]
 , [roc].[Repo_default_definition]
 , [roc].[Repo_default_name]
 , [roc].[Repo_default_is_system_named]
 , [roc].[Repo_definition]
 , [roc].[Repo_generated_always_type]
 , [roc].[Repo_graph_type]
 , [roc].[Repo_is_computed]
 , [roc].[Repo_is_identity]
 , [roc].[Repo_is_nullable]
 , [roc].[Repo_is_persisted]
 , [roc].[Repo_seed_value]
 , [roc].[Repo_increment_value]
 , [roc].[Repo_user_type_fullname]
 , [roc].[Repo_user_type_name]
 , [roc].[Repo_uses_database_collation]
 , [roc].[RepoObject_guid]
 , [roc].[RepoObjectColumn_guid]
 , [roc].[RepoObjectColumn_name]
 , [roc].[SysObjectColumn_column_id]
 , [roc].[SysObjectColumn_name]
 , [sc].[default_definition]
 , [sc].[default_is_system_named]
 , [sc].[default_name]
 , [sc].[definition]
 , [sc].[generated_always_type]
 , [sc].[graph_type]
 , [sc].[is_computed]
 , [sc].[is_identity]
 , [sc].[is_nullable]
 , [sc].[is_persisted]
 , [sc].[seed_value]
 , [sc].[increment_value]
 , [sc].[SysObject_column_name]
 , [sc].[SysObject_name]
 , [sc].[SysObject_RepoObject_guid]
 , [sc].[SysObject_RepoObjectColumn_guid]
 , [sc].[SysObject_schema_name]
 , [sc].[SysObject_type]
 , [sc].[user_type_fullname]
 , [sc].[user_type_name]
 , [sc].[uses_database_collation]
 --sometimes by error we have same named columns in repo.RepoObjectColumn, additinal columns should be deleted in [repo].[usp_sync_guid_RepoObjectColumn]
 , [RowNumberOverName] = ROW_NUMBER() OVER (
  PARTITION BY [sc].[SysObject_RepoObject_guid]
  , [sc].[SysObject_column_name] ORDER BY [roc].[RepoObjectColumn_guid]
  )
FROM repo_sys.SysColumn AS sc
LEFT OUTER JOIN repo.RepoObjectColumn AS roc
 ON sc.SysObject_RepoObjectColumn_guid = roc.RepoObjectColumn_guid
LEFT OUTER JOIN repo.RepoObject AS ro
 ON roc.RepoObject_guid = ro.RepoObject_guid
```

</details>

[Back to top](#dhw_self)

### repo.SysColumn_RepoObjectColumn_via_name

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_id | INT | no |  |
| SysObject_column_id | INT | no |  |
| is_repo_managed | BIT | yes |  |
| RepoObject_fullname | NVARCHAR(261) | yes |  |
| SysObject_fullname | NVARCHAR(261) | yes |  |
| has_different_sys_names | BIT | yes |  |
| is_query_plan_expression | BIT | yes |  |
| is_RepoObjectColumn_name_uniqueidentifier | INT | yes |  |
| is_SysObjectColumn_missing | BIT | yes |  |
| is_SysObjectColumn_name_uniqueidentifier | INT | yes |  |
| persistence_source_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| Referencing_Count | INT | yes |  |
| Repo_default_definition | NVARCHAR(MAX) | yes |  |
| Repo_default_name | NVARCHAR(128) | yes |  |
| Repo_default_is_system_named | BIT | yes |  |
| Repo_definition | NVARCHAR(MAX) | yes |  |
| Repo_generated_always_type | TINYINT | yes |  |
| Repo_graph_type | INT | yes |  |
| Repo_is_computed | BIT | yes |  |
| Repo_is_identity | BIT | yes |  |
| Repo_is_nullable | BIT | yes |  |
| Repo_is_persisted | BIT | yes |  |
| Repo_seed_value | SQL_VARIANT | yes |  |
| Repo_increment_value | SQL_VARIANT | yes |  |
| Repo_user_type_fullname | NVARCHAR(128) | yes |  |
| Repo_user_type_name | NVARCHAR(128) | yes |  |
| Repo_uses_database_collation | BIT | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObjectColumn_name | NVARCHAR(128) | yes |  |
| SysObjectColumn_column_id | INT | yes |  |
| SysObjectColumn_name | NVARCHAR(128) | yes |  |
| default_definition | NVARCHAR(MAX) | yes |  |
| default_is_system_named | BIT | yes |  |
| default_name | SYSNAME(128) | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| generated_always_type | TINYINT | yes |  |
| graph_type | INT | yes |  |
| is_computed | BIT | no |  |
| is_identity | BIT | no |  |
| is_nullable | BIT | yes |  |
| is_persisted | BIT | yes |  |
| seed_value | SQL_VARIANT | yes |  |
| increment_value | SQL_VARIANT | yes |  |
| SysObject_column_name | SYSNAME(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| SysObject_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_type | CHAR(2) | yes |  |
| user_type_fullname | NVARCHAR(182) | yes |  |
| user_type_name | SYSNAME(128) | yes |  |
| uses_database_collation | BIT | yes |  |
| RowNumberOverName | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[SysColumn_RepoObjectColumn_via_name]
AS
--
SELECT [sc].[SysObject_id]
 , [sc].[SysObject_column_id]
 , [ro].[is_repo_managed]
 , [ro].[RepoObject_fullname]
 , [ro].[SysObject_fullname]
 , [roc].[has_different_sys_names]
 , [roc].[is_query_plan_expression]
 , [roc].[is_RepoObjectColumn_name_uniqueidentifier]
 , [roc].[is_SysObjectColumn_missing]
 , [roc].[is_SysObjectColumn_name_uniqueidentifier]
 , [roc].[persistence_source_RepoObjectColumn_guid]
 , [roc].[Referencing_Count]
 , [roc].[Repo_default_definition]
 , [roc].[Repo_default_name]
 , [roc].[Repo_default_is_system_named]
 , [roc].[Repo_definition]
 , [roc].[Repo_generated_always_type]
 , [roc].[Repo_graph_type]
 , [roc].[Repo_is_computed]
 , [roc].[Repo_is_identity]
 , [roc].[Repo_is_nullable]
 , [roc].[Repo_is_persisted]
 , [roc].[Repo_seed_value]
 , [roc].[Repo_increment_value]
 , [roc].[Repo_user_type_fullname]
 , [roc].[Repo_user_type_name]
 , [roc].[Repo_uses_database_collation]
 , [roc].[RepoObject_guid]
 , [roc].[RepoObjectColumn_guid]
 , [roc].[RepoObjectColumn_name]
 , [roc].[SysObjectColumn_column_id]
 , [roc].[SysObjectColumn_name]
 , [sc].[default_definition]
 , [sc].[default_is_system_named]
 , [sc].[default_name]
 , [sc].[definition]
 , [sc].[generated_always_type]
 , [sc].[graph_type]
 , [sc].[is_computed]
 , [sc].[is_identity]
 , [sc].[is_nullable]
 , [sc].[is_persisted]
 , [sc].[seed_value]
 , [sc].[increment_value]
 , [sc].[SysObject_column_name]
 , [sc].[SysObject_name]
 , [sc].[SysObject_RepoObject_guid]
 , [sc].[SysObject_RepoObjectColumn_guid]
 , [sc].[SysObject_schema_name]
 , [sc].[SysObject_type]
 , [sc].[user_type_fullname]
 , [sc].[user_type_name]
 , [sc].[uses_database_collation]
 --sometimes by error we have same named columns in repo.RepoObjectColumn, additinal columns should be deleted in [repo].[usp_sync_guid_RepoObjectColumn]
 , [RowNumberOverName] = ROW_NUMBER() OVER (
  PARTITION BY [sc].[SysObject_RepoObject_guid]
  , [sc].[SysObject_column_name] ORDER BY [roc].[RepoObjectColumn_guid]
  )
FROM repo_sys.SysColumn AS sc
LEFT JOIN repo.RepoObjectColumn AS roc
 ON sc.SysObject_RepoObject_guid = roc.RepoObject_guid
  AND sc.SysObject_column_name = roc.SysObjectColumn_name
LEFT JOIN repo.RepoObject AS ro
 ON roc.RepoObject_guid = ro.RepoObject_guid
```

</details>

[Back to top](#dhw_self)

### repo.SysObject_RepoObject_via_guid

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_id | INT | no |  |
| is_repo_managed | BIT | yes |  |
| SysObject_schema_name | SYSNAME(128) | yes |  |
| SysObject_name | SYSNAME(128) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| modify_date | DATETIME | no |  |
| parent_object_id | INT | no |  |
| SysObject_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| history_table_guid | UNIQUEIDENTIFIER | yes |  |
| history_table_id | INT | yes |  |
| temporal_type | TINYINT | yes |  |
| Repo_history_table_guid | UNIQUEIDENTIFIER | yes |  |
| Repo_temporal_type | TINYINT | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObject_schema_name | NVARCHAR(128) | yes |  |
| RepoObject_name | NVARCHAR(128) | yes |  |
| RepoObject_type | CHAR(2) | yes |  |
| RepoObject_SysObject_id | INT | yes |  |
| RepoObject_SysObject_schema_name | NVARCHAR(128) | yes |  |
| RepoObject_SysObject_name | NVARCHAR(128) | yes |  |
| RepoObject_SysObject_type | CHAR(2) | yes |  |
| RepoObject_SysObject_modify_date | DATETIME | yes |  |
| RepoObject_SysObject_parent_object_id | INT | yes |  |
| RepoObject_is_SysObject_missing | BIT | yes |  |
| is_RepoObject_name_uniqueidentifier | INT | yes |  |
| is_SysObject_name_uniqueidentifier | INT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo].[SysObject_RepoObject_via_guid]
AS
--
SELECT [so].[SysObject_id]
 , [ro].[is_repo_managed]
 , [so].[SysObject_schema_name]
 , [so].[SysObject_name]
 , [so].[type] AS [SysObject_type]
 , [so].[modify_date] AS [modify_date]
 , [so].[parent_object_id] AS [parent_object_id]
 , [so].[SysObject_RepoObject_guid] AS [SysObject_RepoObject_guid]
 , [ro_hist].[RepoObject_guid] AS [history_table_guid]
 , [so].[history_table_id]
 , [so].[temporal_type]
 --, [so].[max_column_id_used] AS         [SysObject_max_column_id_used]
 , [ro].[Repo_history_table_guid]
 , [ro].[Repo_temporal_type]
 , [ro].[RepoObject_guid] AS [RepoObject_guid]
 , [ro].[RepoObject_schema_name]
 , [ro].[RepoObject_name]
 , [ro].[RepoObject_type]
 , [ro].[SysObject_id] AS [RepoObject_SysObject_id]
 , [ro].[SysObject_schema_name] AS [RepoObject_SysObject_schema_name]
 , [ro].[SysObject_name] AS [RepoObject_SysObject_name]
 , [ro].[SysObject_type] AS [RepoObject_SysObject_type]
 , [ro].[SysObject_modify_date] AS [RepoObject_SysObject_modify_date]
 , [ro].[SysObject_parent_object_id] AS [RepoObject_SysObject_parent_object_id]
 , [ro].[is_SysObject_missing] AS [RepoObject_is_SysObject_missing]
 , [ro].[is_RepoObject_name_uniqueidentifier]
 , [ro].[is_SysObject_name_uniqueidentifier]
--, [ro].SysObject_parent_object_id AS          [RepoObject_parent_SysObject_id]
--, [ro].[SysObject_temporal_type] AS      [RepoObject_SysObject_temporal_type]
--, [ro].[SysObject_history_table_id] AS   [RepoObject_SysObject_history_table_id]
--, [ro].[SysObject_max_column_id_used] AS [RepoObject_SysObject_max_column_id_used]
FROM repo_sys.SysObject AS so
LEFT OUTER JOIN repo.RepoObject AS ro
 ON so.SysObject_RepoObject_guid = ro.RepoObject_guid
LEFT OUTER JOIN repo.RepoObject AS ro_hist
 ON so.[history_table_id] = ro_hist.[SysObject_id]
```

</details>

[Back to top](#dhw_self)

### repo.SysObject_RepoObject_via_name

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_id | INT | no |  |
| is_repo_managed | BIT | yes |  |
| SysObject_schema_name | SYSNAME(128) | yes |  |
| SysObject_name | SYSNAME(128) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| modify_date | DATETIME | no |  |
| parent_object_id | INT | no |  |
| SysObject_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| history_table_guid | UNIQUEIDENTIFIER | yes |  |
| history_table_id | INT | yes |  |
| temporal_type | TINYINT | yes |  |
| Repo_history_table_guid | UNIQUEIDENTIFIER | yes |  |
| Repo_temporal_type | TINYINT | yes |  |
| RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| RepoObject_schema_name | NVARCHAR(128) | yes |  |
| RepoObject_name | NVARCHAR(128) | yes |  |
| RepoObject_type | CHAR(2) | yes |  |
| RepoObject_SysObject_id | INT | yes |  |
| RepoObject_SysObject_schema_name | NVARCHAR(128) | yes |  |
| RepoObject_SysObject_name | NVARCHAR(128) | yes |  |
| RepoObject_SysObject_type | CHAR(2) | yes |  |
| RepoObject_SysObject_modify_date | DATETIME | yes |  |
| RepoObject_SysObject_parent_object_id | INT | yes |  |
| RepoObject_is_SysObject_missing | BIT | yes |  |
| is_RepoObject_name_uniqueidentifier | INT | yes |  |
| is_SysObject_name_uniqueidentifier | INT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE VIEW [repo].[SysObject_RepoObject_via_name]
AS
--
SELECT [so].[SysObject_id]
 , [ro].[is_repo_managed]
 , [so].[SysObject_schema_name]
 , [so].[SysObject_name]
 , [so].[type] AS [SysObject_type]
 , [so].[modify_date] AS [modify_date]
 , [so].[parent_object_id] AS [parent_object_id]
 , [so].[SysObject_RepoObject_guid] AS [SysObject_RepoObject_guid]
 , [ro_hist].[RepoObject_guid] AS [history_table_guid]
 , [so].[history_table_id]
 , [so].[temporal_type]
 --, [so].[max_column_id_used] AS         [SysObject_max_column_id_used]
 , [ro].[Repo_history_table_guid]
 , [ro].[Repo_temporal_type]
 , [ro].[RepoObject_guid] AS [RepoObject_guid]
 , [ro].[RepoObject_schema_name]
 , [ro].[RepoObject_name]
 , [ro].[RepoObject_type]
 , [ro].[SysObject_id] AS [RepoObject_SysObject_id]
 , [ro].[SysObject_schema_name] AS [RepoObject_SysObject_schema_name]
 , [ro].[SysObject_name] AS [RepoObject_SysObject_name]
 , [ro].[SysObject_type] AS [RepoObject_SysObject_type]
 , [ro].[SysObject_modify_date] AS [RepoObject_SysObject_modify_date]
 , [ro].[SysObject_parent_object_id] AS [RepoObject_SysObject_parent_object_id]
 , [ro].[is_SysObject_missing] AS [RepoObject_is_SysObject_missing]
 , [ro].[is_RepoObject_name_uniqueidentifier]
 , [ro].[is_SysObject_name_uniqueidentifier]
--, [ro].SysObject_parent_object_id AS          [RepoObject_parent_SysObject_id]
--, [ro].[SysObject_temporal_type] AS      [RepoObject_SysObject_temporal_type]
--, [ro].[SysObject_history_table_id] AS   [RepoObject_SysObject_history_table_id]
--, [ro].[SysObject_max_column_id_used] AS [RepoObject_SysObject_max_column_id_used]
FROM repo_sys.SysObject AS so
LEFT OUTER JOIN repo.RepoObject AS ro
 ON so.SysObject_schema_name = ro.SysObject_schema_name
  AND so.SysObject_name = ro.SysObject_name
LEFT OUTER JOIN repo.RepoObject AS ro_hist
 ON so.[history_table_id] = ro_hist.[SysObject_id]
```

</details>

[Back to top](#dhw_self)

### repo.SysObjectColumn_QueryPlanExpression

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| SysObjectColumn_column_id | INT | yes |  |
| SysObjectColumn_name | NVARCHAR(128) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo].[SysObjectColumn_QueryPlanExpression]
AS
--
SELECT [referencing_RepoObject_guid] AS [RepoObject_guid]
 , TRY_CAST(RIGHT([referencing_column_name], 4) AS INT) AS [SysObjectColumn_column_id]
 , [referencing_column_name] AS [SysObjectColumn_name]
FROM repo.[RepoObjectColumn_reference_QueryPlan]
WHERE [is_target_column_name_expression] = 1

UNION

SELECT [referenced_RepoObject_guid]
 , TRY_CAST(RIGHT([referenced_column_name], 4) AS INT) AS [SysObjectColumn_column_id]
 , [referenced_column_name]
FROM repo.[RepoObjectColumn_reference_QueryPlan]
WHERE [is_source_column_name_expression] = 1
 AND NOT [referenced_RepoObject_guid] IS NULL
```

</details>

[Back to top](#dhw_self)

### repo.type

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| type | NVARCHAR(128) | yes |  |
| type_desc | NVARCHAR(128) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
master.dbo.spt_values is an undocumemted hidden view or table, containing useful entries 
it's copy should be in in repo_config.spt_values
*/
CREATE VIEW [repo].[type]
 --WITH SCHEMABINDING
AS
--
SELECT PARSENAME(REPLACE([name], ':', '.'), 2) AS 'type'
 , PARSENAME(REPLACE([name], ':', '.'), 1) AS 'type_desc'
FROM repo.spt_values
WHERE [type] = 'O9T'
 AND [number] = - 1;
```

</details>

[Back to top](#dhw_self)

### repo.type_level1type_level2type

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| type | NVARCHAR(128) | yes |  |
| type_desc | NVARCHAR(128) | yes |  |
| level1type | VARCHAR(9) | yes |  |
| level2type | VARCHAR(10) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
Mappping from repo_sys.type (used in [type] in system catalog views)
to level1type (used in sp_addextendedproperty, sp_updateextendedproperty) 
*/
CREATE VIEW [repo].[type_level1type_level2type]
 --WITH SCHEMABINDING
AS
--
SELECT [type]
 , [type_desc]
 , [level1type] = CASE 
  WHEN [type] = 'AF'
   THEN 'AGGREGATE'
    --When [type] = 'D '
    --Then 'DEFAULT'
  WHEN [type] IN (
    'FN'
    , 'FS'
    , 'FT'
    , 'IF'
    , 'IS'
    , 'TF'
    )
   THEN 'FUNCTION'
    --WHEN [type] = 'V ' THEN 'LOGICAL FILE NAME'
  WHEN [type] IN (
    'P '
    , 'PC'
    , 'RF'
    , 'X '
    )
   THEN 'PROCEDURE'
  WHEN [type] = 'SQ'
   THEN 'QUEUE'
  WHEN [type] = 'R '
   THEN 'RULE'
  WHEN [type] = 'SN'
   THEN 'SYNONYM'
  WHEN [type] = 'U '
   THEN 'TABLE'
    --WHEN [type] = 'V ' THEN 'TABLE_TYPE'
    --WHEN [type] = 'V ' THEN 'TYPE'
  WHEN [type] = 'V '
   THEN 'VIEW'
    --WHEN [type] = 'V ' THEN 'XML SCHEMA COLLECTION'
  END
 , [level2type] = CASE [type]
  WHEN 'C'
   THEN 'CONSTRAINT' --CHECK_CONSTRAINT
  WHEN 'D'
   THEN 'CONSTRAINT' --DEFAULT_CONSTRAINT
  WHEN 'EC'
   THEN 'CONSTRAINT' --EDGE_CONSTRAINT
  WHEN 'F'
   THEN 'CONSTRAINT' --FOREIGN_KEY_CONSTRAINT
  WHEN 'PK'
   THEN 'CONSTRAINT' --PRIMARY_KEY_CONSTRAINT
  WHEN 'UQ'
   THEN 'CONSTRAINT' --UNIQUE_CONSTRAINT
  END
FROM repo.type
```

</details>

[Back to top](#dhw_self)

### repo.visjs_EdgeList_object_test01

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_node_id | BIGINT | yes |  |
| referenced_node_id | BIGINT | yes |  |
| EdgeListElement | VARCHAR(64) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
<script type="text/javascript">
    // create an array with nodes
    var nodes = new vis.DataSet([
        {id: 1, label: 'Node 1'},
        {id: 2, label: 'Node 2'},
        {id: 3, label: 'Node 3'},
        {id: 4, label: 'Node 4'},
        {id: 5, label: 'Node 5'}
    ]);

    // create an array with edges
    var edges = new vis.DataSet([
        {from: 1, to: 3},
        {from: 1, to: 2},
        {from: 2, to: 4},
        {from: 2, to: 5}
    ]);

*/
CREATE VIEW [repo].[visjs_EdgeList_object_test01]
AS
SELECT [referencing_node_id]
 , [referenced_node_id]
 , EdgeListElement = CONCAT (
  '{ from: '
  , [referenced_node_id]
  , ', to:'
  , [referencing_node_id]
  , ' },'
  )
FROM repo.[RepoObject_reference_SqlExpressionDependencies]
```

</details>

[Back to top](#dhw_self)

### repo.visjs_nodelist_object_test01

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| SysObject_type | CHAR(2) | yes |  |
| node_id | BIGINT | yes |  |
| NodeListElement | NVARCHAR(303) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
<script type="text/javascript">
    // create an array with nodes
    var nodes = new vis.DataSet([
        {id: 1, label: 'Node 1'},
        {id: 2, label: 'Node 2'},
        {id: 3, label: 'Node 3'},
        {id: 4, label: 'Node 4'},
        {id: 5, label: 'Node 5'}
    ]);

    // create an array with edges
    var edges = new vis.DataSet([
        {from: 1, to: 3},
        {from: 1, to: 2},
        {from: 2, to: 4},
        {from: 2, to: 5}
    ]);

*/
CREATE VIEW [repo].[visjs_nodelist_object_test01]
AS
SELECT [RepoObject_guid]
 , [SysObject_fullname]
 , [SysObject_type]
 , [node_id]
 , NodeListElement = CONCAT (
  '{id: '
  , [node_id]
  , ', label: '''
  , [SysObject_fullname]
  , '''},'
  )
FROM repo.RepoObject
WHERE [SysObject_type] IN (
  'U'
  , 'V'
  , 'P'
  )
```

</details>

[Back to top](#dhw_self)

### repo_sys.ColumnReference

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_full_name | NVARCHAR(517) | no |  |
| referencing_minor_id | INT | yes |  |
| referenced_server_name | NVARCHAR(128) | yes |  |
| referenced_database_name | NVARCHAR(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_minor_name | NVARCHAR(128) | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_class | TINYINT | yes |  |
| referenced_class_desc | NVARCHAR(60) | yes |  |
| is_caller_dependent | BIT | no |  |
| is_ambiguous | BIT | no |  |
| is_selected | BIT | no |  |
| is_updated | BIT | no |  |
| is_select_all | BIT | no |  |
| is_all_columns_found | BIT | no |  |
| is_insert_all | BIT | no |  |
| is_incomplete | BIT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo_sys].[ColumnReference]
AS
--
--muss / kann noch angereichert werden
SELECT [so].SysObject_fullname AS SysObject_full_name
 , [sdsre].[referencing_minor_id]
 , [sdsre].[referenced_server_name]
 , [sdsre].[referenced_database_name]
 , [sdsre].[referenced_schema_name]
 , [sdsre].[referenced_entity_name]
 , [sdsre].[referenced_minor_name]
 , [sdsre].[referenced_id]
 , [sdsre].[referenced_minor_id]
 , [sdsre].[referenced_class]
 , [sdsre].[referenced_class_desc]
 , [sdsre].[is_caller_dependent]
 , [sdsre].[is_ambiguous]
 , [sdsre].[is_selected]
 , [sdsre].[is_updated]
 , [sdsre].[is_select_all]
 , [sdsre].[is_all_columns_found]
 , [sdsre].[is_insert_all]
 , [sdsre].[is_incomplete]
FROM repo_sys.SysObject AS so
CROSS APPLY sys_dwh.dm_sql_referenced_entities(so.SysObject_fullname, 'OBJECT') AS sdsre
WHERE [so].[type] IN (
  'U'
  , 'V'
  )
```

</details>

[Back to top](#dhw_self)

### repo_sys.ExtendedProperties

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| class | TINYINT | no |  |
| major_id | INT | no |  |
| minor_id | INT | no |  |
| property_name | SYSNAME(128) | no |  |
| class_desc | NVARCHAR(60) | yes |  |
| property_value | SQL_VARIANT | yes |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| minor_name | NVARCHAR(128) | yes |  |
| entity_column_name | NVARCHAR(128) | yes |  |
| entity_parameter_name | NVARCHAR(128) | yes |  |
| entity_index_name | NVARCHAR(128) | yes |  |
| level2type | VARCHAR(9) | yes |  |
| property_basetype | SQL_VARIANT | yes |  |
| property_nvarchar | NVARCHAR(4000) | yes |  |
| parent_object_id | INT | yes |  |
| parent_name | SYSNAME(128) | yes |  |
| parent_type | CHAR(2) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
database_id required in
- OBJECT_SCHEMA_NAME
- OBJECT_NAME
*/
CREATE VIEW [repo_sys].[ExtendedProperties]
AS
--
SELECT [sep].[class]
 , [sep].[major_id]
 , [sep].[minor_id]
 , [sep].[name] COLLATE database_default AS [property_name]
 , [sep].[class_desc]
 , [sep].value AS [property_value]
 , CASE 
  WHEN [sep].[class] IN (
    1
    , 2
    , 7
    )
   THEN OBJECT_SCHEMA_NAME([sep].[major_id], [db].[dwh_database_id])
  END AS [SysObject_schema_name]
 , CASE 
  WHEN [sep].[class] IN (
    1
    , 2
    , 7
    )
   THEN OBJECT_NAME([sep].[major_id], [db].[dwh_database_id])
  END AS [SysObject_name]
 , CASE [sep].[class]
  WHEN 1
   THEN [sc].[name]
  WHEN 2
   THEN [sp].[name]
  WHEN 3
   THEN [si].[name]
  END COLLATE database_default AS [minor_name]
 , CASE 
  WHEN [sep].[class] = 1
   THEN [sc].[name]
  END COLLATE database_default AS [entity_column_name]
 , CASE 
  WHEN [sep].[class] = 2
   THEN [sp].[name]
  END COLLATE database_default AS [entity_parameter_name]
 , CASE 
  WHEN [sep].[class] = 7
   THEN [si].[name]
  END COLLATE database_default AS [entity_index_name]
 , [level2type] = CASE 
  WHEN [sep].[class] = 1
   AND [sep].[minor_id] > 0
   THEN 'COLUMN'
  WHEN [sep].[class] = 2
   AND [sep].[minor_id] > 0
   THEN 'PARAMETER'
  WHEN [sep].[class] = 7
   AND [sep].[minor_id] > 0
   THEN 'INDEX'
  END
 , [property_basetype] = SQL_VARIANT_PROPERTY([sep].value, 'BaseType')
 , [property_nvarchar] = TRY_CAST([sep].value AS NVARCHAR(4000))
 , [so].[parent_object_id]
 , [parent_name] = [parent].[name]
 , [parent_type] = [parent].[type]
-- Explicit conversion from data type int to uniqueidentifier is not allowed.
--, [property_value_uniqueidentifier] = TRY_CAST([sep].value As UniqueIdentifier)
FROM sys_dwh.extended_properties AS sep
LEFT OUTER JOIN sys_dwh.columns AS sc
 ON sep.major_id = sc.object_id
  AND sep.minor_id = sc.column_id
LEFT OUTER JOIN sys_dwh.parameters AS sp
 ON sep.major_id = sp.object_id
  AND sep.minor_id = sp.parameter_id
LEFT OUTER JOIN sys_dwh.indexes AS si
 ON sep.major_id = si.object_id
  AND sep.minor_id = si.index_id
LEFT OUTER JOIN sys_dwh.objects AS so
 ON sep.major_id = so.object_id
LEFT OUTER JOIN sys_dwh.objects AS parent
 ON parent.object_id = so.parent_object_id
--
CROSS APPLY repo.ftv_dwh_database() AS db
```

</details>

[Back to top](#dhw_self)

### repo_sys.ExtendedProperties_ParameterForAddUpdateDrop

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | SYSNAME(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| level0type | VARCHAR(6) | no |  |
| level0name | NVARCHAR(128) | yes |  |
| level1type | VARCHAR(9) | yes |  |
| level1name | NVARCHAR(128) | yes |  |
| level2type | VARCHAR(10) | yes |  |
| level2name | NVARCHAR(128) | yes |  |
| minor_id | INT | no |  |
| class | TINYINT | no |  |
| class_desc | NVARCHAR(60) | yes |  |
| type | CHAR(2) | yes |  |
| type_level1type | VARCHAR(9) | yes |  |
| type_level2type | VARCHAR(10) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo_sys].[ExtendedProperties_ParameterForAddUpdateDrop]
AS
--
SELECT [sep].[property_name]
 , [sep].[property_value]
 , 'SCHEMA' AS [level0type]
 , [sep].[SysObject_schema_name] AS [level0name]
 , [level1type] = IIF([stl].[level2type] = 'CONSTRAINT', 'TABLE', [stl].[level1type])
 , [level1name] = IIF([stl].[level2type] = 'CONSTRAINT', [sep].[parent_name] COLLATE database_default, [sep].[SysObject_name] COLLATE database_default)
 , [level2type] = IIF([stl].[level2type] = 'CONSTRAINT', [stl].[level2type], [sep].[level2type] COLLATE database_default)
 , [level2name] = IIF([stl].[level2type] = 'CONSTRAINT', [sep].[SysObject_name], [sep].[minor_name])
 , [sep].[minor_id]
 , [sep].[class]
 , [sep].[class_desc]
 , [so].[type]
 , [type_level1type] = [stl].[level1type]
 , [type_level2type] = [stl].[level2type]
FROM repo_sys.[ExtendedProperties] AS sep
INNER JOIN sys_dwh.objects AS so
 ON sep.major_id = so.object_id
INNER JOIN repo.[type_level1type_level2type] AS stl
 ON so.type COLLATE database_default = stl.type
```

</details>

[Back to top](#dhw_self)

### repo_sys.ForeignKey

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| name | SYSNAME(128) | no |  |
| object_id | INT | no |  |
| principal_id | INT | yes |  |
| schema_id | INT | no |  |
| parent_object_id | INT | no |  |
| type | CHAR(2) | yes |  |
| type_desc | NVARCHAR(60) | yes |  |
| create_date | DATETIME | no |  |
| modify_date | DATETIME | no |  |
| is_ms_shipped | BIT | no |  |
| is_published | BIT | no |  |
| is_schema_published | BIT | no |  |
| referenced_object_id | INT | yes |  |
| key_index_id | INT | yes |  |
| is_disabled | BIT | no |  |
| is_not_for_replication | BIT | no |  |
| is_not_trusted | BIT | no |  |
| delete_referential_action | TINYINT | yes |  |
| delete_referential_action_desc | NVARCHAR(60) | yes |  |
| update_referential_action | TINYINT | yes |  |
| update_referential_action_desc | NVARCHAR(60) | yes |  |
| is_system_named | BIT | no |  |
| ForeignKey_guid | UNIQUEIDENTIFIER | yes |  |
| ForeignKey_fullname | NVARCHAR(261) | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| parent_RepoObject_fullname | NVARCHAR(261) | yes |  |
| parent_SysObject_fullname | NVARCHAR(261) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql


CREATE View [repo_sys].[ForeignKey]
As
Select
    name
  , object_id
  , principal_id
  , schema_id
  , parent_object_id
  , type
  , type_desc
  , create_date
  , modify_date
  , is_ms_shipped
  , is_published
  , is_schema_published
  , referenced_object_id
  , key_index_id
  , is_disabled
  , is_not_for_replication
  , is_not_trusted
  , delete_referential_action
  , delete_referential_action_desc
  , update_referential_action
  , update_referential_action_desc
  , is_system_named
  , ForeignKey_guid = ro.RepoObject_guid
  , ForeignKey_fullname = ro.RepoObject_fullname
  , parent_RepoObject_guid     = parent_ro.RepoObject_guid
  , parent_RepoObject_fullname = parent_ro.RepoObject_fullname
  , parent_SysObject_fullname  = parent_ro.SysObject_fullname
From sys_dwh.foreign_keys     As fk
    Left Join repo.RepoObject As ro
        On ro.SysObject_id = fk.object_id
    Left Join repo.RepoObject As parent_ro
        On parent_ro.SysObject_id = fk.parent_object_id

```

</details>

[Back to top](#dhw_self)

### repo_sys.ForeignKeyColumn

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| constraint_object_id | INT | no |  |
| constraint_column_id | INT | no |  |
| parent_object_id | INT | no |  |
| parent_column_id | INT | no |  |
| referenced_object_id | INT | no |  |
| referenced_column_id | INT | no |  |
| ForeignKey_name | SYSNAME(128) | yes |  |
| ForeignKey_fullname | NVARCHAR(261) | yes |  |
| ForeignKey_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_column_name | SYSNAME(128) | yes |  |
| referencing_name | NVARCHAR(128) | yes |  |
| referencing_schema_name | NVARCHAR(128) | yes |  |
| referencing_RepoObject_fullname | NVARCHAR(261) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_SysObject_fullname | NVARCHAR(261) | yes |  |
| referenced_column_name | SYSNAME(128) | yes |  |
| referenced_name | NVARCHAR(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE VIEW [repo_sys].[ForeignKeyColumn]
AS
SELECT
 --
 fkc.constraint_object_id
 , fkc.constraint_column_id
 , fkc.parent_object_id
 , fkc.parent_column_id
 , fkc.referenced_object_id
 , fkc.referenced_column_id
 , ForeignKey_name = fk.name
 , ForeignKey_fullname
 , ForeignKey_guid
 , referencing_column_name = parent_sc.SysObject_column_name
 , referencing_name = parent_sc.SysObject_name
 , referencing_schema_name = parent_sc.SysObject_schema_name
 , referencing_RepoObject_fullname = fk.parent_RepoObject_fullname
 , referencing_RepoObject_guid = parent_sc.SysObject_RepoObject_guid
 , referencing_RepoObjectColumn_guid = parent_sc.SysObject_RepoObjectColumn_guid
 , referencing_SysObject_fullname = fk.parent_SysObject_fullname
 , referenced_column_name = referenced_sc.SysObject_column_name
 , referenced_name = referenced_sc.SysObject_name
 , referenced_schema_name = referenced_sc.SysObject_schema_name
 , referenced_RepoObject_guid = referenced_sc.SysObject_RepoObject_guid
 , referenced_RepoObjectColumn_guid = referenced_sc.SysObject_RepoObjectColumn_guid
FROM sys_dwh.foreign_key_columns AS fkc
LEFT OUTER JOIN repo_sys.ForeignKey AS fk
 ON fk.object_id = fkc.constraint_object_id
LEFT OUTER JOIN [repo_sys].[SysColumn] parent_sc
 ON parent_sc.SysObject_id = fkc.parent_object_id
  AND parent_sc.SysObject_column_id = fkc.parent_column_id
LEFT OUTER JOIN [repo_sys].[SysColumn] referenced_sc
 ON referenced_sc.SysObject_id = fkc.referenced_object_id
  AND referenced_sc.SysObject_column_id = fkc.referenced_column_id

```

</details>

[Back to top](#dhw_self)

### repo_sys.Index_unique

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| index_name | SYSNAME(128) | yes |  |
| index_id | INT | no |  |
| is_index_unique | BIT | yes |  |
| is_index_primary_key | BIT | yes |  |
| is_index_unique_constraint | BIT | yes |  |
| is_index_disabled | BIT | yes |  |
| index_type | TINYINT | no |  |
| index_type_desc | NVARCHAR(60) | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| parent_schema_name | NVARCHAR(128) | yes |  |
| parent_SysObject_name | NVARCHAR(128) | yes |  |
| parent_SysObject_fullname | NVARCHAR(261) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo_sys].[Index_real_unique]
AS
--
SELECT [index_guid] = [ro_index].[RepoObject_guid]
 , [index_name] = [si].[name] COLLATE database_default
 , [si].[index_id]
 , [si].[is_unique] AS [is_index_unique]
 , [si].[is_primary_key] AS [is_index_primary_key]
 , [si].[is_unique_constraint] AS [is_index_unique_constraint]
 , [si].[is_disabled] AS [is_index_disabled]
 , [si].[type] AS [index_type]
 , [si].[type_desc] AS [index_type_desc]
 , [parent_RepoObject_guid] = [ro_parent].[RepoObject_guid]
 , [parent_schema_name] = [ro_parent].[SysObject_schema_name]
 , [parent_SysObject_name] = [ro_parent].[SysObject_name]
 , [parent_SysObject_fullname] = [ro_parent].[SysObject_fullname]
FROM sys_dwh.indexes AS si
LEFT JOIN repo.RepoObject AS ro_index
 ON ro_index.SysObject_name = si.name COLLATE database_default
  AND ro_index.SysObject_parent_object_id = si.object_id
LEFT JOIN repo.RepoObject AS ro_parent
 ON ro_parent.SysObject_id = si.object_id
WHERE [si].[is_unique] = 1
 AND NOT [ro_index].[RepoObject_guid] IS NULL
```

</details>

[Back to top](#dhw_self)

### repo_sys.IndexColumn_unique

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| index_guid | UNIQUEIDENTIFIER | yes |  |
| index_column_id | INT | no |  |
| is_descending_key | BIT | yes |  |
| RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| parent_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| index_name | SYSNAME(128) | yes |  |
| parent_schema_name | NVARCHAR(128) | yes |  |
| parent_SysObject_name | NVARCHAR(128) | yes |  |
| SysObject_column_name | SYSNAME(128) | yes |  |
| SysObject_column_user_type_fullname | NVARCHAR(182) | yes |  |
| is_index_unique | BIT | yes |  |
| is_index_primary_key | BIT | yes |  |
| parent_SysObject_fullname | NVARCHAR(261) | yes |  |
| is_index_real | BIT | yes |  |
| index_id | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
Index hat folgende Eindeutigkeiten

- RepoObject_guid
- Schema.NameDesIndex - kann sich aber ändern, wenn der Index umbenannt wird
- Parent-Objekt (Tabelle) + NameDesIndex - kann sich auch ändern
- object_id des Index in der Datenbank
  - hier in der Sicht nicht enthalten, müsste oder könnte man joinen über sys.Object oder sys.key_constraints
  - ist aber wenig nützlich, wenn es auch virtuelle Index geben soll, die nicht in der Datenbank erstellt werden können und somit keine object_id bekommen

Kombination mit virtuellen Index

- Schema.NameDesIndex müssen auch für die UNION aus echten und virtuellen Index unique sein 
- Ablage
  - eine gemeinsame Tabelle (UK einfach möglich)
  - separate Tabellen und UNION ALL
    - wenn WITH SCHEMABINDING, dann wäre auch ein UK möglich
	  - da die Quellen aber System-Sichten sind, geht SCHEMABINDING nicht
	- man bräuchte sich nur um die Tabelle mit den virtuellen Index kümmern, die echten wären immer über diese Sicht aktuell  
	  zumindest nach einem sync der guid wegen repo_sys.SysColumn_RepoObjectColumn_via_column_name

semantische Gruppen müssen aber ebenfalls (und vor allem) den echten Index zugeordnet werden, dafür wird also eh eine Tabelle benötigt

*/
CREATE VIEW [repo_sys].[IndexColumn_unique]
AS
--
SELECT [index_guid] = [sc_ro].[RepoObject_guid]
 , [sic].[index_column_id]
 , [sic].[is_descending_key]
 , [sc_roc].[RepoObjectColumn_guid] --could by empty for new Objects, execute [repo].[usp_sync_guid]
 , [parent_RepoObject_guid] = [sc_roc].[RepoObject_guid] --could by empty for new Objects, execute [repo].[usp_sync_guid]
 , [index_name] = [si].[name] COLLATE database_default
 , [parent_schema_name] = [sc_roc].[SysObject_schema_name]
 , [parent_SysObject_name] = [sc_roc].[SysObject_name]
 , [sc_roc].[SysObject_column_name]
 , [sc_roc].[user_type_fullname] AS [SysObject_column_user_type_fullname]
 , [si].[is_unique] AS [is_index_unique]
 , [si].[is_primary_key] AS [is_index_primary_key]
 , [parent_SysObject_fullname] = [sc_roc].[SysObject_fullname]
 , [is_index_real] = CAST(1 AS BIT)
 , [sic].[index_id]
--, [sic].[key_ordinal]
--, [si].[type] AS                   [index_type]
--, [si].[type_desc] AS              [index_type_desc]
--, [si].[is_unique_constraint] AS   [is_index_unique_constraint]
--  --
--, [sic].object_id
--, [sic].[column_id]
--, [sic].[partition_ordinal]
--, [sic].[is_included_column]
--, [sic].[column_store_order_ordinal]
--  --, [si].[data_space_id]
--  --, [si].[ignore_dup_key]
--, [si].[fill_factor]
--, [si].[is_padded]
--, [si].[is_disabled]
--, [si].[is_hypothetical]
--, [si].[is_ignored_in_optimization]
--, [si].[allow_row_locks]
--, [si].[allow_page_locks]
--, [si].[has_filter]
--, [si].[filter_definition]
--, [si].[compression_delay]
--, [si].[suppress_dup_key_messages]
--, [si].[auto_created]
--, [si].[optimize_for_sequential_key]
FROM sys_dwh.index_columns AS sic
INNER JOIN sys_dwh.indexes AS si
 ON sic.object_id = si.object_id
  AND sic.index_id = si.index_id
INNER JOIN repo.SysColumn_RepoObjectColumn_via_name AS sc_roc
 ON sic.object_id = sc_roc.SysObject_id
  AND sic.column_id = sc_roc.SysObject_column_id
LEFT JOIN repo.SysObject_RepoObject_via_name AS sc_ro
 ON sc_ro.SysObject_name = si.name COLLATE database_default
  AND sc_ro.SysObject_schema_name = sc_roc.SysObject_schema_name
WHERE [si].[is_unique] = 1
```

</details>

[Back to top](#dhw_self)

### repo_sys.RepoObjectReferenced

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| SysObject_id | INT | yes |  |
| SysObject_type | CHAR(2) | yes |  |
| SysObject_modify_date | DATETIME | yes |  |
| is_repo_managed | BIT | yes |  |
| has_different_sys_names | BIT | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| referencing_minor_id | INT | yes |  |
| referenced_server_name | NVARCHAR(128) | yes |  |
| referenced_database_name | NVARCHAR(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_minor_name | NVARCHAR(128) | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | yes |  |
| referenced_class | TINYINT | yes |  |
| referenced_class_desc | NVARCHAR(60) | yes |  |
| is_caller_dependent | BIT | no |  |
| is_ambiguous | BIT | no |  |
| is_selected | BIT | no |  |
| is_updated | BIT | no |  |
| is_select_all | BIT | no |  |
| is_all_columns_found | BIT | no |  |
| is_insert_all | BIT | no |  |
| is_incomplete | BIT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
this view can be used to check if SysObject renaming is safe or if exists referenced objects and refactoring is required
*/
CREATE VIEW [repo_sys].[RepoObjectReferenced]
AS
--
SELECT [ro].[RepoObject_guid]
 --, [ro].[RepoObject_schema_name]
 --, [ro].[RepoObject_name]
 --, [ro].[RepoObject_type]
 , [ro].[SysObject_id]
 --, [ro].[SysObject_schema_name]
 --, [ro].[SysObject_name]
 , [ro].[SysObject_type]
 , [ro].[SysObject_modify_date]
 --, [ro].[has_execution_plan_issue]
 , [ro].[is_repo_managed]
 --, [ro].[modify_dt]
 , [ro].[has_different_sys_names]
 , [ro].[RepoObject_fullname]
 , [ro].[SysObject_fullname]
 , [referenced].[referencing_minor_id] AS [referencing_minor_id]
 , [referenced].[referenced_server_name] COLLATE database_default AS [referenced_server_name]
 , [referenced].[referenced_database_name] COLLATE database_default AS [referenced_database_name]
 , [referenced].[referenced_schema_name] COLLATE database_default AS [referenced_schema_name]
 , [referenced].[referenced_entity_name] COLLATE database_default AS [referenced_entity_name]
 , [referenced].[referenced_minor_name] COLLATE database_default AS [referenced_minor_name]
 , [referenced].[referenced_id] AS [referenced_id]
 , [referenced].[referenced_minor_id] AS [referenced_minor_id]
 , [referenced].[referenced_class] AS [referenced_class]
 , [referenced].[referenced_class_desc] COLLATE database_default AS [referenced_class_desc]
 , [referenced].[is_caller_dependent] AS [is_caller_dependent]
 , [referenced].[is_ambiguous] AS [is_ambiguous]
 , [referenced].[is_selected] AS [is_selected]
 , [referenced].[is_updated] AS [is_updated]
 , [referenced].[is_select_all] AS [is_select_all]
 , [referenced].[is_all_columns_found] AS [is_all_columns_found]
 , [referenced].[is_insert_all] AS [is_insert_all]
 , [referenced].[is_incomplete] AS [is_incomplete]
FROM repo.RepoObject AS ro
CROSS APPLY sys_dwh.dm_sql_referenced_entities(SysObject_fullname, 'OBJECT') AS referenced
WHERE ISNULL([ro].[has_get_referenced_issue], 0) = 0

```

</details>

[Back to top](#dhw_self)

### repo_sys.RepoObjectReferencing

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| SysObject_id | INT | yes |  |
| SysObject_type | CHAR(2) | yes |  |
| SysObject_modify_date | DATETIME | yes |  |
| is_repo_managed | BIT | yes |  |
| has_different_sys_names | BIT | yes |  |
| RepoObject_fullname | NVARCHAR(261) | no |  |
| SysObject_fullname | NVARCHAR(261) | no |  |
| referencing_schema_name | SYSNAME(128) | yes |  |
| referencing_entity_name | SYSNAME(128) | yes |  |
| referencing_id | INT | no |  |
| referencing_class | TINYINT | yes |  |
| referencing_class_desc | NVARCHAR(60) | yes |  |
| is_caller_dependent | BIT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
this view can be used to check if SysObject renaming is safe or if exists referencing objects and refactoring is required
*/
CREATE VIEW [repo_sys].[RepoObjectReferencing]
AS
--
SELECT [ro].[RepoObject_guid]
 --, [ro].[RepoObject_schema_name]
 --, [ro].[RepoObject_name]
 --, [ro].[RepoObject_type]
 , [ro].[SysObject_id]
 --, [ro].[SysObject_schema_name]
 --, [ro].[SysObject_name]
 , [ro].[SysObject_type]
 , [ro].[SysObject_modify_date]
 --, [ro].[has_execution_plan_issue]
 , [ro].[is_repo_managed]
 --, [ro].[modify_dt]
 , [ro].[has_different_sys_names]
 , [ro].[RepoObject_fullname]
 , [ro].[SysObject_fullname]
 , [referencing].[referencing_schema_name]
 , [referencing].[referencing_entity_name]
 , [referencing].[referencing_id]
 , [referencing].[referencing_class]
 , [referencing].[referencing_class_desc]
 , [referencing].[is_caller_dependent]
FROM repo.RepoObject AS ro
CROSS APPLY sys.dm_sql_referencing_entities(SysObject_fullname, 'OBJECT') AS referencing

```

</details>

[Back to top](#dhw_self)

### repo_sys.sql_expression_dependencies

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| referencing_id | INT | no |  |
| referencing_minor_id | INT | no |  |
| referenced_class | TINYINT | yes |  |
| referenced_id | INT | yes |  |
| referenced_minor_id | INT | no |  |
| referencing_schema_name | NVARCHAR(128) | yes |  |
| referencing_entity_name | NVARCHAR(128) | yes |  |
| referencing_column_name | SYSNAME(128) | yes |  |
| referencing_type | CHAR(2) | yes |  |
| referencing_type_desciption | NVARCHAR(60) | yes |  |
| referencing_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| referencing_class | TINYINT | yes |  |
| referencing_class_desc | NVARCHAR(60) | yes |  |
| referenced_server_name | NVARCHAR(128) | yes |  |
| referenced_database_name | NVARCHAR(128) | yes |  |
| referenced_schema_name | NVARCHAR(128) | yes |  |
| referenced_entity_name | NVARCHAR(128) | yes |  |
| referenced_column_name | SYSNAME(128) | yes |  |
| referenced_class_desc | NVARCHAR(60) | yes |  |
| referenced_type | CHAR(2) | yes |  |
| referenced_type_desciption | NVARCHAR(60) | yes |  |
| referenced_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| referenced_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| is_schema_bound_reference | BIT | no |  |
| is_caller_dependent | BIT | no |  |
| is_ambiguous | BIT | no |  |
| is_computed | BIT | yes |  |
| definition | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
ATTENTION:
[SysObject_RepoObject_guid] has prefix SysObject, because it it the RepoObject_guid stored in repo_sys.extended_properties
but some objects havn't extended properties, for example Triggers
These objects have RepoObject_guid only in [repo].[RepoObject].RepoObject_guid, but they have no SysObject_RepoObject_guid

if we would need RepoObject_guid for these objects (triggers, ...), we would need to change this view somehow join RepoObject_guid
But for now we don't wan't to do.
*/
CREATE VIEW [repo_sys].[sql_expression_dependencies]
AS
--
SELECT [sed].[referencing_id]
 , [sed].[referencing_minor_id]
 , [sed].[referenced_class]
 , [sed].[referenced_id]
 , [sed].[referenced_minor_id]
 , OBJECT_SCHEMA_NAME([sed].[referencing_id], [db].[dwh_database_id]) AS [referencing_schema_name]
 , OBJECT_NAME([sed].[referencing_id], [db].[dwh_database_id]) AS [referencing_entity_name]
 --, COL_NAME([sed].[referencing_id] , [sed].[referencing_minor_id]) AS [referencing_column_name]
 , [ssc].[SysObject_column_name] AS [referencing_column_name]
 , [so].[type] AS [referencing_type]
 , [so].[type_desc] AS [referencing_type_desciption]
 , [so].[SysObject_RepoObject_guid] AS [referencing_RepoObject_guid]
 , [ssc].[SysObject_RepoObjectColumn_guid] AS [referencing_RepoObjectColumn_guid]
 , [sed].[referencing_class]
 , [sed].[referencing_class_desc]
 , [sed].[referenced_server_name]
 , [sed].[referenced_database_name] COLLATE database_default AS [referenced_database_name]
 , [sed].[referenced_schema_name] COLLATE database_default AS [referenced_schema_name]
 , [sed].[referenced_entity_name] COLLATE database_default AS [referenced_entity_name]
 --, COL_NAME([sed].[referenced_id] , [sed].[referenced_minor_id]) AS   [referenced_column_name]
 , [ssc2].[SysObject_column_name] AS [referenced_column_name]
 , [sed].[referenced_class_desc]
 , [so2].[type] AS [referenced_type]
 , [so2].[type_desc] AS [referenced_type_desciption]
 , [so2].[SysObject_RepoObject_guid] AS [referenced_RepoObject_guid]
 , [ssc2].[SysObject_RepoObjectColumn_guid] AS [referenced_RepoObjectColumn_guid]
 , [sed].[is_schema_bound_reference]
 , [sed].[is_caller_dependent]
 , [sed].[is_ambiguous]
 --table columns can be is_computed = 1, these columns should also have a defintion
 , [ssc].[is_computed]
 , [ssc].[definition]
FROM sys_dwh.sql_expression_dependencies AS sed
INNER JOIN repo_sys.SysObject AS so
 ON sed.referencing_id = so.SysObject_id
LEFT JOIN repo_sys.SysObject AS so2
 ON sed.referenced_id = so2.SysObject_id
LEFT JOIN repo_sys.SysColumn AS ssc
 ON sed.referencing_id = ssc.SysObject_id
  AND sed.referencing_minor_id = ssc.SysObject_column_id
LEFT JOIN repo_sys.SysColumn AS ssc2
 ON sed.referenced_id = ssc2.SysObject_id
  AND sed.referenced_minor_id = ssc2.SysObject_column_id
--
CROSS APPLY repo.ftv_dwh_database() AS db
```

</details>

[Back to top](#dhw_self)

### repo_sys.SysColumn

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_id | INT | no |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| SysObject_column_id | INT | no |  |
| SysObject_column_name | SYSNAME(128) | yes |  |
| SysObject_type | CHAR(2) | yes |  |
| SysObject_type_desc | NVARCHAR(60) | yes |  |
| SysObject_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| SysObject_RepoObjectColumn_guid | UNIQUEIDENTIFIER | yes |  |
| system_type_id | TINYINT | no |  |
| user_type_id | INT | no |  |
| user_type_name | SYSNAME(128) | yes |  |
| user_type_fullname | NVARCHAR(182) | yes |  |
| max_length | SMALLINT | no |  |
| precision | TINYINT | no |  |
| scale | TINYINT | no |  |
| collation_name | SYSNAME(128) | yes |  |
| is_nullable | BIT | yes |  |
| is_ansi_padded | BIT | no |  |
| is_rowguidcol | BIT | no |  |
| is_identity | BIT | no |  |
| is_computed | BIT | no |  |
| is_filestream | BIT | no |  |
| is_replicated | BIT | yes |  |
| is_non_sql_subscribed | BIT | yes |  |
| is_merge_published | BIT | yes |  |
| is_dts_replicated | BIT | yes |  |
| is_xml_document | BIT | no |  |
| xml_collection_id | INT | no |  |
| default_object_id | INT | no |  |
| rule_object_id | INT | no |  |
| is_sparse | BIT | yes |  |
| is_column_set | BIT | yes |  |
| generated_always_type | TINYINT | yes |  |
| generated_always_type_desc | NVARCHAR(60) | yes |  |
| encryption_type | INT | yes |  |
| encryption_type_desc | NVARCHAR(64) | yes |  |
| encryption_algorithm_name | SYSNAME(128) | yes |  |
| column_encryption_key_id | INT | yes |  |
| column_encryption_key_database_name | SYSNAME(128) | yes |  |
| is_hidden | BIT | yes |  |
| is_masked | BIT | no |  |
| graph_type | INT | yes |  |
| graph_type_desc | NVARCHAR(60) | yes |  |
| definition | NVARCHAR(MAX) | yes |  |
| is_persisted | BIT | yes |  |
| uses_database_collation | BIT | yes |  |
| default_definition | NVARCHAR(MAX) | yes |  |
| default_is_system_named | BIT | yes |  |
| default_name | SYSNAME(128) | yes |  |
| default_parent_column_id | INT | yes |  |
| seed_value | SQL_VARIANT | yes |  |
| increment_value | SQL_VARIANT | yes |  |
| last_value | SQL_VARIANT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [repo_sys].[SysColumn]
AS
--
SELECT [sc].object_id AS [SysObject_id]
 , OBJECT_SCHEMA_NAME([sc].object_id, [db].[dwh_database_id]) AS [SysObject_schema_name]
 , OBJECT_NAME([sc].object_id, [db].[dwh_database_id]) AS [SysObject_name]
 , [sc].[column_id] AS [SysObject_column_id]
 , [sc].[name] COLLATE database_default AS [SysObject_column_name]
 , [so].[type] AS [SysObject_type]
 , [so].[type_desc] AS [SysObject_type_desc]
 , TRY_CAST([ep].[property_value] AS UNIQUEIDENTIFIER) AS [SysObject_RepoObject_guid]
 , TRY_CAST([ep2].[property_value] AS UNIQUEIDENTIFIER) AS [SysObject_RepoObjectColumn_guid]
 , [sc].[system_type_id]
 , [sc].[user_type_id]
 -- code for [user_type_name]: https://stackoverflow.com/questions/9179990/where-do-i-find-sql-server-metadata-for-column-datatypes
 , [user_type_name] = [tp].[name] COLLATE database_default
 , [user_type_fullname] = CASE 
  WHEN [tp].[name] IN (
    'varchar'
    , 'char'
    , 'varbinary'
    , 'binary'
    )
   THEN [tp].[name] + '(' + IIF([sc].[max_length] = - 1, 'max', CAST([sc].[max_length] AS VARCHAR(25))) + ')'
  WHEN [tp].[name] IN (
    'nvarchar'
    , 'nchar'
    )
   THEN [tp].[name] + '(' + IIF([sc].[max_length] = - 1, 'max', CAST([sc].[max_length] / 2 AS VARCHAR(25))) + ')'
  WHEN [tp].[name] IN (
    'decimal'
    , 'numeric'
    )
   THEN [tp].[name] + '(' + CAST([sc].[precision] AS VARCHAR(25)) + ', ' + CAST([sc].[scale] AS VARCHAR(25)) + ')'
  WHEN [tp].[name] IN ('datetime2')
   THEN [tp].[name] + '(' + CAST([sc].[scale] AS VARCHAR(25)) + ')'
  ELSE [tp].[name]
  END COLLATE database_default
 , [sc].[max_length]
 , [sc].[precision]
 , [sc].[scale]
 , [sc].[collation_name]
 , [sc].[is_nullable]
 , [sc].[is_ansi_padded]
 , [sc].[is_rowguidcol]
 , [sc].[is_identity]
 , [sc].[is_computed]
 , [sc].[is_filestream]
 , [sc].[is_replicated]
 , [sc].[is_non_sql_subscribed]
 , [sc].[is_merge_published]
 , [sc].[is_dts_replicated]
 , [sc].[is_xml_document]
 , [sc].[xml_collection_id]
 , [sc].[default_object_id]
 , [sc].[rule_object_id]
 , [sc].[is_sparse]
 , [sc].[is_column_set]
 , [sc].[generated_always_type]
 , [sc].[generated_always_type_desc]
 , [sc].[encryption_type]
 , [sc].[encryption_type_desc]
 , [sc].[encryption_algorithm_name]
 , [sc].[column_encryption_key_id]
 , [sc].[column_encryption_key_database_name]
 , [sc].[is_hidden]
 , [sc].[is_masked]
 , [sc].[graph_type]
 , [sc].[graph_type_desc]
 , [scc].[definition] COLLATE database_default AS [definition]
 , [scc].[is_persisted]
 , [scc].[uses_database_collation]
 , [sdc].[definition] COLLATE database_default AS [default_definition]
 , [sdc].[is_system_named] AS [default_is_system_named]
 , [sdc].[name] COLLATE database_default AS [default_name]
 , [sdc].[parent_column_id] AS [default_parent_column_id]
 , [sic].[seed_value]
 , [sic].[increment_value]
 , [sic].last_value
--, [sic].[is_not_for_replication]
--, CAST(CASE
--           WHEN [sc].[name] = 'SysStartTime'
--                AND [tp].[name] = 'datetime2'
--           THEN 1
--           WHEN [sc].[name] = 'SysEndTime'
--                AND [tp].[name] = 'datetime2'
--           THEN 2
--       END AS TINYINT) AS                                        [temporal_column_type]
FROM sys_dwh.columns AS sc
LEFT OUTER JOIN repo_sys.[ExtendedProperties] AS ep
 ON ep.major_id = sc.object_id
  AND ep.minor_id = 0
  AND ep.property_name = N'RepoObject_guid'
LEFT OUTER JOIN repo_sys.[ExtendedProperties] AS ep2
 ON ep2.major_id = sc.object_id
  AND ep2.minor_id = sc.column_id
  AND ep2.property_name = N'RepoObjectColumn_guid'
LEFT OUTER JOIN repo_sys.SysObject AS so
 ON so.SysObject_id = sc.object_id
LEFT OUTER JOIN sys_dwh.types AS tp
 ON sc.user_type_id = tp.user_type_id
LEFT OUTER JOIN sys_dwh.computed_columns AS scc
 ON scc.object_id = sc.object_id
  AND scc.[column_id] = sc.[column_id]
LEFT OUTER JOIN sys_dwh.default_constraints AS sdc
 ON sc.default_object_id = sdc.object_id
LEFT OUTER JOIN [sys_dwh].identity_columns AS sic
 ON sic.object_id = sc.object_id
  AND sic.[column_id] = sc.[column_id]
--
CROSS APPLY repo.ftv_dwh_database() AS db
WHERE OBJECT_SCHEMA_NAME([sc].object_id, [db].[dwh_database_id]) <> 'sys'
```

</details>

[Back to top](#dhw_self)

### repo_sys.SysObject

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| SysObject_id | INT | no |  |
| SysObject_schema_name | SYSNAME(128) | yes |  |
| SysObject_name | SYSNAME(128) | no |  |
| SysObject_fullname | NVARCHAR(517) | no |  |
| SysObject_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| principal_id | INT | yes |  |
| schema_id | INT | no |  |
| parent_object_id | INT | no |  |
| type | CHAR(2) | yes |  |
| type_desc | NVARCHAR(60) | yes |  |
| create_date | DATETIME | no |  |
| modify_date | DATETIME | no |  |
| is_ms_shipped | BIT | no |  |
| is_published | BIT | no |  |
| is_schema_published | BIT | no |  |
| temporal_type | TINYINT | yes |  |
| temporal_type_desc | NVARCHAR(60) | yes |  |
| history_table_id | INT | yes |  |
| max_column_id_used | INT | yes |  |
| sql_modules_definition | NVARCHAR(MAX) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
ATTENTION:
[SysObject_RepoObject_guid] has prefix SysObject, because it it the RepoObject_guid stored in repo_sys.extended_properties
but some objects havn't extended properties, for example Triggers
These objects have RepoObject_guid only in [repo].[RepoObject].RepoObject_guid, but they have no SysObject_RepoObject_guid

ATTENTION:
when using synonyms
SCHEMA_NAME([so].schema_id) doesn't return the original schema_name but it runs in the current database 

OBJECT_SCHEMA_NAME muss verwendet werden und die database_id der DWH-Datenbank muss verwendet werden
oder über synonym [sys_dwh].schemas
*/
CREATE VIEW [repo_sys].[SysObject]
AS
--
SELECT [so].object_id AS [SysObject_id]
 , [sch].[name] COLLATE database_default AS [SysObject_schema_name]
 --, OBJECT_SCHEMA_NAME([so].object_id) AS [SysObject_schema_name_]
 , [so].[name] COLLATE database_default AS [SysObject_name]
 , [SysObject_fullname] = CONCAT (
  QUOTENAME([sch].[name])
  , '.'
  , QUOTENAME([so].[name])
  ) COLLATE database_default
 , TRY_CAST([ep].[property_value] AS UNIQUEIDENTIFIER) AS [SysObject_RepoObject_guid]
 , [so].[principal_id]
 , [so].schema_id
 , [so].[parent_object_id]
 , [so].[type] COLLATE database_default AS [type]
 , [so].[type_desc]
 , [so].[create_date]
 , [so].[modify_date]
 , [so].[is_ms_shipped]
 , [so].[is_published]
 , [so].[is_schema_published]
 , [st].[temporal_type]
 , [st].[temporal_type_desc]
 , [st].[history_table_id]
 , [st].[max_column_id_used]
 , [sm].[definition] AS [sql_modules_definition]
FROM sys_dwh.objects AS so
LEFT OUTER JOIN [sys_dwh].schemas AS sch
 ON sch.schema_id = [so].schema_id
LEFT OUTER JOIN repo_sys.[ExtendedProperties] AS ep
 ON ep.major_id = so.object_id
  AND ep.minor_id = 0
  AND ep.property_name = N'RepoObject_guid'
LEFT OUTER JOIN sys_dwh.tables AS st
 ON st.object_id = so.object_id
LEFT OUTER JOIN [sys_dwh].[sql_modules] AS sm
 ON sm.object_id = so.object_id
WHERE [sch].[name] <> 'sys'
```

</details>

[Back to top](#dhw_self)

### sys_self.ExtendedProperties

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| class | TINYINT | no |  |
| major_id | INT | no |  |
| minor_id | INT | no |  |
| property_name | SYSNAME(128) | no |  |
| class_desc | NVARCHAR(60) | yes |  |
| property_value | SQL_VARIANT | yes |  |
| SysObject_schema_name | NVARCHAR(128) | yes |  |
| SysObject_name | NVARCHAR(128) | yes |  |
| minor_name | NVARCHAR(128) | yes |  |
| entity_column_name | NVARCHAR(128) | yes |  |
| entity_parameter_name | NVARCHAR(128) | yes |  |
| entity_index_name | NVARCHAR(128) | yes |  |
| level2type | VARCHAR(9) | yes |  |
| property_basetype | SQL_VARIANT | yes |  |
| property_nvarchar | NVARCHAR(4000) | yes |  |
| parent_object_id | INT | yes |  |
| parent_name | SYSNAME(128) | yes |  |
| parent_type | CHAR(2) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [sys_self].[ExtendedProperties]
AS
--
SELECT [sep].[class]
 , [sep].[major_id]
 , [sep].[minor_id]
 , [sep].[name] COLLATE database_default AS [property_name]
 , [sep].[class_desc]
 , [sep].value AS [property_value]
 , CASE 
  WHEN [sep].[class] IN (
    1
    , 2
    , 7
    )
   THEN OBJECT_SCHEMA_NAME([sep].[major_id] /*, [db].[dwh_database_id]*/)
  END AS [SysObject_schema_name]
 , CASE 
  WHEN [sep].[class] IN (
    1
    , 2
    , 7
    )
   THEN OBJECT_NAME([sep].[major_id] /*, [db].[dwh_database_id]*/)
  END AS [SysObject_name]
 , CASE [sep].[class]
  WHEN 1
   THEN [sc].[name]
  WHEN 2
   THEN [sp].[name]
  WHEN 3
   THEN [si].[name]
  END COLLATE database_default AS [minor_name]
 , CASE 
  WHEN [sep].[class] = 1
   THEN [sc].[name]
  END COLLATE database_default AS [entity_column_name]
 , CASE 
  WHEN [sep].[class] = 2
   THEN [sp].[name]
  END COLLATE database_default AS [entity_parameter_name]
 , CASE 
  WHEN [sep].[class] = 7
   THEN [si].[name]
  END COLLATE database_default AS [entity_index_name]
 , [level2type] = CASE 
  WHEN [sep].[class] = 1
   AND [sep].[minor_id] > 0
   THEN 'COLUMN'
  WHEN [sep].[class] = 2
   AND [sep].[minor_id] > 0
   THEN 'PARAMETER'
  WHEN [sep].[class] = 7
   AND [sep].[minor_id] > 0
   THEN 'INDEX'
  END
 , [property_basetype] = SQL_VARIANT_PROPERTY([sep].value, 'BaseType')
 , [property_nvarchar] = TRY_CAST([sep].value AS NVARCHAR(4000))
 , [so].[parent_object_id]
 , [parent_name] = [parent].[name]
 , [parent_type] = [parent].[type]
-- Explicit conversion from data type int to uniqueidentifier is not allowed.
--, [property_value_uniqueidentifier] = TRY_CAST([sep].value As UniqueIdentifier)
FROM sys.extended_properties AS sep
LEFT OUTER JOIN sys.columns AS sc
 ON sep.major_id = sc.object_id
  AND sep.minor_id = sc.column_id
LEFT OUTER JOIN sys.parameters AS sp
 ON sep.major_id = sp.object_id
  AND sep.minor_id = sp.parameter_id
LEFT OUTER JOIN sys.indexes AS si
 ON sep.major_id = si.object_id
  AND sep.minor_id = si.index_id
LEFT OUTER JOIN sys.objects AS so
 ON sep.major_id = so.object_id
LEFT OUTER JOIN sys.objects AS parent
 ON parent.object_id = so.parent_object_id
  ----
  --CROSS APPLY
  --repo.ftv_dwh_database() AS db
```

</details>

[Back to top](#dhw_self)

### sys_self.ExtendedProperties_ParameterForAddUpdateDrop

| Column | Type | Null | MS_Description |
| --- | ---| --- | --- |
| property_name | SYSNAME(128) | no |  |
| property_value | SQL_VARIANT | yes |  |
| level0type | VARCHAR(6) | no |  |
| level0name | NVARCHAR(128) | yes |  |
| level1type | VARCHAR(9) | yes |  |
| level1name | NVARCHAR(128) | yes |  |
| level2type | VARCHAR(10) | yes |  |
| level2name | NVARCHAR(128) | yes |  |
| minor_id | INT | no |  |
| class | TINYINT | no |  |
| class_desc | NVARCHAR(60) | yes |  |
| type | CHAR(2) | yes |  |
| type_level1type | VARCHAR(9) | yes |  |
| type_level2type | VARCHAR(10) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE VIEW [sys_self].[ExtendedProperties_ParameterForAddUpdateDrop]
AS
--
SELECT [sep].[property_name]
 , [sep].[property_value]
 , 'SCHEMA' AS [level0type]
 , [sep].[SysObject_schema_name] AS [level0name]
 , [level1type] = IIF([stl].[level2type] = 'CONSTRAINT', 'TABLE', [stl].[level1type])
 , [level1name] = IIF([stl].[level2type] = 'CONSTRAINT', [sep].[parent_name], [sep].[SysObject_name])
 , [level2type] = IIF([stl].[level2type] = 'CONSTRAINT', [stl].[level2type], [sep].[level2type])
 , [level2name] = IIF([stl].[level2type] = 'CONSTRAINT', [sep].[SysObject_name], [sep].[minor_name])
 , [sep].[minor_id]
 , [sep].[class]
 , [sep].[class_desc]
 , [so].[type]
 , [type_level1type] = [stl].[level1type]
 , [type_level2type] = [stl].[level2type]
FROM sys_self.[ExtendedProperties] AS sep
INNER JOIN sys.objects AS so
 ON sep.major_id = so.object_id
INNER JOIN repo.[type_level1type_level2type] AS stl
 ON so.type COLLATE database_default = stl.type
```

</details>

[Back to top](#dhw_self)

</details>

## Stored Procedures

<details><summary>Click to expand</summary>

* [dbo.sp_alterdiagram](#dbosp_alterdiagram)
* [dbo.sp_creatediagram](#dbosp_creatediagram)
* [dbo.sp_dropdiagram](#dbosp_dropdiagram)
* [dbo.sp_helpdiagramdefinition](#dbosp_helpdiagramdefinition)
* [dbo.sp_helpdiagrams](#dbosp_helpdiagrams)
* [dbo.sp_renamediagram](#dbosp_renamediagram)
* [dbo.sp_upgraddiagrams](#dbosp_upgraddiagrams)
* [graph.usp_PERSIST_ProcedureInstance](#graphusp_persist_procedureinstance)
* [graph.usp_PERSIST_RepoObject](#graphusp_persist_repoobject)
* [graph.usp_PERSIST_RepoObjectColumn](#graphusp_persist_repoobjectcolumn)
* [repo.LONGPRINT](#repolongprint)
* [repo.usp_connect_database](#repousp_connect_database)
* [repo.usp_ExecutionLog_insert](#repousp_executionlog_insert)
* [repo.usp_generate_merge](#repousp_generate_merge)
* [repo.usp_GeneratorUsp_insert_update_persistence](#repousp_generatorusp_insert_update_persistence)
* [repo.usp_Index_finish](#repousp_index_finish)
* [repo.usp_Index_ForeignKey](#repousp_index_foreignkey)
* [repo.usp_index_inheritance](#repousp_index_inheritance)
* [repo.usp_Index_Settings](#repousp_index_settings)
* [repo.usp_Index_virtual_InsertUpdate](#repousp_index_virtual_insertupdate)
* [repo.usp_init_parameter](#repousp_init_parameter)
* [repo.usp_init_spt_values](#repousp_init_spt_values)
* [repo.usp_main](#repousp_main)
* [repo.usp_parameter_insert_update](#repousp_parameter_insert_update)
* [repo.usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T](#repousp_persist_indexcolumn_referencedreferencing_hasfullcolumnsinreferencing_t)
* [repo.usp_PERSIST_RepoObject_SqlModules_41_from_T](#repousp_persist_repoobject_sqlmodules_41_from_t)
* [repo.usp_PERSIST_RepoObject_SqlModules_61_SelectIdentifier_Union_T](#repousp_persist_repoobject_sqlmodules_61_selectidentifier_union_t)
* [repo.usp_persistence_insert_update](#repousp_persistence_insert_update)
* [repo.usp_RepoObject_Inheritance](#repousp_repoobject_inheritance)
* [repo.usp_RepoObject_update_SysObjectQueryPlan](#repousp_repoobject_update_sysobjectqueryplan)
* [repo.usp_RepoObjectColumn_Inheritance](#repousp_repoobjectcolumn_inheritance)
* [repo.usp_RepoObjectColumn_update_RepoObjectColumn_column_id](#repousp_repoobjectcolumn_update_repoobjectcolumn_column_id)
* [repo.usp_RepoObjectSource_FirstResultSet](#repousp_repoobjectsource_firstresultset)
* [repo.usp_RepoObjectSource_QueryPlan](#repousp_repoobjectsource_queryplan)
* [repo.usp_sync_ExtendedProperties_Repo2Sys_Delete](#repousp_sync_extendedproperties_repo2sys_delete)
* [repo.usp_sync_ExtendedProperties_Repo2Sys_InsertUpdate](#repousp_sync_extendedproperties_repo2sys_insertupdate)
* [repo.usp_sync_ExtendedProperties_Sys2Repo_InsertUpdate](#repousp_sync_extendedproperties_sys2repo_insertupdate)
* [repo.usp_sync_guid](#repousp_sync_guid)
* [repo.usp_sync_guid_RepoObject](#repousp_sync_guid_repoobject)
* [repo.usp_sync_guid_RepoObjectColumn](#repousp_sync_guid_repoobjectcolumn)
* [repo.usp_update_Referencing_Count](#repousp_update_referencing_count)
* [repo_sys.usp_AddOrUpdateExtendedProperty](#repo_sysusp_addorupdateextendedproperty)
* [repo_sys.usp_dropextendedproperty_level_1](#repo_sysusp_dropextendedproperty_level_1)
* [repo_sys.usp_dropextendedproperty_level_2](#repo_sysusp_dropextendedproperty_level_2)
* [sys_self.usp_dropextendedproperty_level_1](#sys_selfusp_dropextendedproperty_level_1)
* [sys_self.usp_dropextendedproperty_level_2](#sys_selfusp_dropextendedproperty_level_2)

### dbo.sp_alterdiagram

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @diagramname | SYSNAME(128) | no |  |
| @owner_id | INT | no |  |
| @version | INT | no |  |
| @definition | VARBINARY(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_alterdiagram
	(
		@diagramname 	sysname,
		@owner_id	int	= null,
		@version 	int,
		@definition 	varbinary(max)
	)
	WITH EXECUTE AS 'dbo'
	AS
	BEGIN
		set nocount on
	
		declare @theId 			int
		declare @retval 		int
		declare @IsDbo 			int
		
		declare @UIDFound 		int
		declare @DiagId			int
		declare @ShouldChangeUID	int
	
		if(@diagramname is null)
		begin
			RAISERROR ('Invalid ARG', 16, 1)
			return -1
		end
	
		execute as caller;
		select @theId = DATABASE_PRINCIPAL_ID();	 
		select @IsDbo = IS_MEMBER(N'db_owner'); 
		if(@owner_id is null)
			select @owner_id = @theId;
		revert;
	
		select @ShouldChangeUID = 0
		select @DiagId = diagram_id, @UIDFound = principal_id from dbo.sysdiagrams where principal_id = @owner_id and name = @diagramname 
		
		if(@DiagId IS NULL or (@IsDbo = 0 and @theId <> @UIDFound))
		begin
			RAISERROR ('Diagram does not exist or you do not have permission.', 16, 1);
			return -3
		end
	
		if(@IsDbo <> 0)
		begin
			if(@UIDFound is null or USER_NAME(@UIDFound) is null) -- invalid principal_id
			begin
				select @ShouldChangeUID = 1 ;
			end
		end

		-- update dds data			
		update dbo.sysdiagrams set definition = @definition where diagram_id = @DiagId ;

		-- change owner
		if(@ShouldChangeUID = 1)
			update dbo.sysdiagrams set principal_id = @theId where diagram_id = @DiagId ;

		-- update dds version
		if(@version is not null)
			update dbo.sysdiagrams set version = @version where diagram_id = @DiagId ;

		return 0
	END
	
```

</details>

[Back to top](#dhw_self)

### dbo.sp_creatediagram

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @diagramname | SYSNAME(128) | no |  |
| @owner_id | INT | no |  |
| @version | INT | no |  |
| @definition | VARBINARY(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_creatediagram
	(
		@diagramname 	sysname,
		@owner_id		int	= null, 	
		@version 		int,
		@definition 	varbinary(max)
	)
	WITH EXECUTE AS 'dbo'
	AS
	BEGIN
		set nocount on
	
		declare @theId int
		declare @retval int
		declare @IsDbo	int
		declare @userName sysname
		if(@version is null or @diagramname is null)
		begin
			RAISERROR (N'E_INVALIDARG', 16, 1);
			return -1
		end
	
		execute as caller;
		select @theId = DATABASE_PRINCIPAL_ID(); 
		select @IsDbo = IS_MEMBER(N'db_owner');
		revert; 
		
		if @owner_id is null
		begin
			select @owner_id = @theId;
		end
		else
		begin
			if @theId <> @owner_id
			begin
				if @IsDbo = 0
				begin
					RAISERROR (N'E_INVALIDARG', 16, 1);
					return -1
				end
				select @theId = @owner_id
			end
		end
		-- next 2 line only for test, will be removed after define name unique
		if EXISTS(select diagram_id from dbo.sysdiagrams where principal_id = @theId and name = @diagramname)
		begin
			RAISERROR ('The name is already used.', 16, 1);
			return -2
		end
	
		insert into dbo.sysdiagrams(name, principal_id , version, definition)
				VALUES(@diagramname, @theId, @version, @definition) ;
		
		select @retval = @@IDENTITY 
		return @retval
	END
	
```

</details>

[Back to top](#dhw_self)

### dbo.sp_dropdiagram

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @diagramname | SYSNAME(128) | no |  |
| @owner_id | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_dropdiagram
	(
		@diagramname 	sysname,
		@owner_id	int	= null
	)
	WITH EXECUTE AS 'dbo'
	AS
	BEGIN
		set nocount on
		declare @theId 			int
		declare @IsDbo 			int
		
		declare @UIDFound 		int
		declare @DiagId			int
	
		if(@diagramname is null)
		begin
			RAISERROR ('Invalid value', 16, 1);
			return -1
		end
	
		EXECUTE AS CALLER;
		select @theId = DATABASE_PRINCIPAL_ID();
		select @IsDbo = IS_MEMBER(N'db_owner'); 
		if(@owner_id is null)
			select @owner_id = @theId;
		REVERT; 
		
		select @DiagId = diagram_id, @UIDFound = principal_id from dbo.sysdiagrams where principal_id = @owner_id and name = @diagramname 
		if(@DiagId IS NULL or (@IsDbo = 0 and @UIDFound <> @theId))
		begin
			RAISERROR ('Diagram does not exist or you do not have permission.', 16, 1)
			return -3
		end
	
		delete from dbo.sysdiagrams where diagram_id = @DiagId;
	
		return 0;
	END
	
```

</details>

[Back to top](#dhw_self)

### dbo.sp_helpdiagramdefinition

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @diagramname | SYSNAME(128) | no |  |
| @owner_id | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_helpdiagramdefinition
	(
		@diagramname 	sysname,
		@owner_id	int	= null 		
	)
	WITH EXECUTE AS N'dbo'
	AS
	BEGIN
		set nocount on

		declare @theId 		int
		declare @IsDbo 		int
		declare @DiagId		int
		declare @UIDFound	int
	
		if(@diagramname is null)
		begin
			RAISERROR (N'E_INVALIDARG', 16, 1);
			return -1
		end
	
		execute as caller;
		select @theId = DATABASE_PRINCIPAL_ID();
		select @IsDbo = IS_MEMBER(N'db_owner');
		if(@owner_id is null)
			select @owner_id = @theId;
		revert; 
	
		select @DiagId = diagram_id, @UIDFound = principal_id from dbo.sysdiagrams where principal_id = @owner_id and name = @diagramname;
		if(@DiagId IS NULL or (@IsDbo = 0 and @UIDFound <> @theId ))
		begin
			RAISERROR ('Diagram does not exist or you do not have permission.', 16, 1);
			return -3
		end

		select version, definition FROM dbo.sysdiagrams where diagram_id = @DiagId ; 
		return 0
	END
	
```

</details>

[Back to top](#dhw_self)

### dbo.sp_helpdiagrams

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @diagramname | SYSNAME(128) | no |  |
| @owner_id | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_helpdiagrams
	(
		@diagramname sysname = NULL,
		@owner_id int = NULL
	)
	WITH EXECUTE AS N'dbo'
	AS
	BEGIN
		DECLARE @user sysname
		DECLARE @dboLogin bit
		EXECUTE AS CALLER;
			SET @user = USER_NAME();
			SET @dboLogin = CONVERT(bit,IS_MEMBER('db_owner'));
		REVERT;
		SELECT
			[Database] = DB_NAME(),
			[Name] = name,
			[ID] = diagram_id,
			[Owner] = USER_NAME(principal_id),
			[OwnerID] = principal_id
		FROM
			sysdiagrams
		WHERE
			(@dboLogin = 1 OR USER_NAME(principal_id) = @user) AND
			(@diagramname IS NULL OR name = @diagramname) AND
			(@owner_id IS NULL OR principal_id = @owner_id)
		ORDER BY
			4, 5, 1
	END
	
```

</details>

[Back to top](#dhw_self)

### dbo.sp_renamediagram

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @diagramname | SYSNAME(128) | no |  |
| @owner_id | INT | no |  |
| @new_diagramname | SYSNAME(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_renamediagram
	(
		@diagramname 		sysname,
		@owner_id		int	= null,
		@new_diagramname	sysname
	
	)
	WITH EXECUTE AS 'dbo'
	AS
	BEGIN
		set nocount on
		declare @theId 			int
		declare @IsDbo 			int
		
		declare @UIDFound 		int
		declare @DiagId			int
		declare @DiagIdTarg		int
		declare @u_name			sysname
		if((@diagramname is null) or (@new_diagramname is null))
		begin
			RAISERROR ('Invalid value', 16, 1);
			return -1
		end
	
		EXECUTE AS CALLER;
		select @theId = DATABASE_PRINCIPAL_ID();
		select @IsDbo = IS_MEMBER(N'db_owner'); 
		if(@owner_id is null)
			select @owner_id = @theId;
		REVERT;
	
		select @u_name = USER_NAME(@owner_id)
	
		select @DiagId = diagram_id, @UIDFound = principal_id from dbo.sysdiagrams where principal_id = @owner_id and name = @diagramname 
		if(@DiagId IS NULL or (@IsDbo = 0 and @UIDFound <> @theId))
		begin
			RAISERROR ('Diagram does not exist or you do not have permission.', 16, 1)
			return -3
		end
	
		-- if((@u_name is not null) and (@new_diagramname = @diagramname))	-- nothing will change
		--	return 0;
	
		if(@u_name is null)
			select @DiagIdTarg = diagram_id from dbo.sysdiagrams where principal_id = @theId and name = @new_diagramname
		else
			select @DiagIdTarg = diagram_id from dbo.sysdiagrams where principal_id = @owner_id and name = @new_diagramname
	
		if((@DiagIdTarg is not null) and  @DiagId <> @DiagIdTarg)
		begin
			RAISERROR ('The name is already used.', 16, 1);
			return -2
		end		
	
		if(@u_name is null)
			update dbo.sysdiagrams set [name] = @new_diagramname, principal_id = @theId where diagram_id = @DiagId
		else
			update dbo.sysdiagrams set [name] = @new_diagramname where diagram_id = @DiagId
		return 0
	END
	
```

</details>

[Back to top](#dhw_self)

### dbo.sp_upgraddiagrams

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE PROCEDURE dbo.sp_upgraddiagrams
	AS
	BEGIN
		IF OBJECT_ID(N'dbo.sysdiagrams') IS NOT NULL
			return 0;
	
		CREATE TABLE dbo.sysdiagrams
		(
			name sysname NOT NULL,
			principal_id int NOT NULL,	-- we may change it to varbinary(85)
			diagram_id int PRIMARY KEY IDENTITY,
			version int,
	
			definition varbinary(max)
			CONSTRAINT UK_principal_name UNIQUE
			(
				principal_id,
				name
			)
		);


		/* Add this if we need to have some form of extended properties for diagrams */
		/*
		IF OBJECT_ID(N'dbo.sysdiagram_properties') IS NULL
		BEGIN
			CREATE TABLE dbo.sysdiagram_properties
			(
				diagram_id int,
				name sysname,
				value varbinary(max) NOT NULL
			)
		END
		*/

		IF OBJECT_ID(N'dbo.dtproperties') IS NOT NULL
		begin
			insert into dbo.sysdiagrams
			(
				[name],
				[principal_id],
				[version],
				[definition]
			)
			select	 
				convert(sysname, dgnm.[uvalue]),
				DATABASE_PRINCIPAL_ID(N'dbo'),			-- will change to the sid of sa
				0,							-- zero for old format, dgdef.[version],
				dgdef.[lvalue]
			from dbo.[dtproperties] dgnm
				inner join dbo.[dtproperties] dggd on dggd.[property] = 'DtgSchemaGUID' and dggd.[objectid] = dgnm.[objectid]	
				inner join dbo.[dtproperties] dgdef on dgdef.[property] = 'DtgSchemaDATA' and dgdef.[objectid] = dgnm.[objectid]
				
			where dgnm.[property] = 'DtgSchemaNAME' and dggd.[uvalue] like N'_EA3E6268-D998-11CE-9454-00AA00A3F36E_' 
			return 2;
		end
		return 1;
	END
	
```

</details>

[Back to top](#dhw_self)

### graph.usp_PERSIST_ProcedureInstance

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [graph].[usp_PERSIST_ProcedureInstance]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[graph].[usp_PERSIST_ProcedureInstance]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":500,"Name":"delete persistence target missing in source","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[ProcedureInstance_S]","log_target_object":"[graph].[ProcedureInstance]","log_flag_InsertUpdateDelete":"D"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',11,';',500,';',NULL);

DELETE T
FROM [graph].[ProcedureInstance] AS T
WHERE
NOT EXISTS
(SELECT 1 FROM [graph].[ProcedureInstance_S] AS S
WHERE
T.[Procedure_RepoObject_guid] = S.[Procedure_RepoObject_guid]
AND T.[Instance] = S.[Instance]
)
 

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'delete persistence target missing in source'
SET @source_object = '[graph].[ProcedureInstance_S]'
SET @target_object = '[graph].[ProcedureInstance]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":600,"Name":"update changed","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[ProcedureInstance_S]","log_target_object":"[graph].[ProcedureInstance]","log_flag_InsertUpdateDelete":"U"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',11,';',600,';',NULL);

UPDATE T
SET
  T.[Instance] = S.[Instance]
, T.[Procedure_fullname] = S.[Procedure_fullname]
, T.[Procedure_RepoObject_guid] = S.[Procedure_RepoObject_guid]

FROM [graph].[ProcedureInstance] AS T
INNER JOIN [graph].[ProcedureInstance_S] AS S
ON
T.[Procedure_RepoObject_guid] = S.[Procedure_RepoObject_guid]
AND T.[Instance] = S.[Instance]

WHERE
   T.[Instance] <> S.[Instance]
OR T.[Procedure_fullname] <> S.[Procedure_fullname]
OR T.[Procedure_RepoObject_guid] <> S.[Procedure_RepoObject_guid]


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'update changed'
SET @source_object = '[graph].[ProcedureInstance_S]'
SET @target_object = '[graph].[ProcedureInstance]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":700,"Name":"insert missing","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[ProcedureInstance_S]","log_target_object":"[graph].[ProcedureInstance]","log_flag_InsertUpdateDelete":"I"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',11,';',700,';',NULL);

INSERT INTO 
 [graph].[ProcedureInstance]
 (
  [Instance]
, [Procedure_fullname]
, [Procedure_RepoObject_guid]
)
SELECT
  [Instance]
, [Procedure_fullname]
, [Procedure_RepoObject_guid]

FROM [graph].[ProcedureInstance_S] AS S
WHERE
NOT EXISTS
(SELECT 1
FROM [graph].[ProcedureInstance] AS T
WHERE
T.[Procedure_RepoObject_guid] = S.[Procedure_RepoObject_guid]
AND T.[Instance] = S.[Instance]
)

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'insert missing'
SET @source_object = '[graph].[ProcedureInstance_S]'
SET @target_object = '[graph].[ProcedureInstance]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , 
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### graph.usp_PERSIST_RepoObject

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [graph].[usp_PERSIST_RepoObject]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[graph].[usp_PERSIST_RepoObject]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":100,"Name":"check for empty source","has_logging":0,"is_condition":1,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObject_S]"}]}*/
IF (SELECT count(*) FROM [graph].[RepoObject_S]) = 0

/*{"ReportUspStep":[{"Number":110,"Parent_Number":100,"Name":"ERROR 50110: persistence source is empty","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":0}]}*/
BEGIN
PRINT CONCAT('usp_id;Number;Parent_Number: ',9,';',110,';',100);

 THROW 50110
  , 'persistence source is empty: [graph].[RepoObject_S]'
  , 1;

END;

/*{"ReportUspStep":[{"Number":500,"Name":"delete persistence target missing in source","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObject_S]","log_target_object":"[graph].[RepoObject]","log_flag_InsertUpdateDelete":"D"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',9,';',500,';',NULL);

DELETE T
FROM [graph].[RepoObject] AS T
WHERE
NOT EXISTS
(SELECT 1 FROM [graph].[RepoObject_S] AS S
WHERE
T.[RepoObject_guid] = S.[RepoObject_guid]
)
 

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'delete persistence target missing in source'
SET @source_object = '[graph].[RepoObject_S]'
SET @target_object = '[graph].[RepoObject]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":600,"Name":"update changed","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObject_S]","log_target_object":"[graph].[RepoObject]","log_flag_InsertUpdateDelete":"U"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',9,';',600,';',NULL);

UPDATE T
SET
  T.[RepoObject_fullname] = S.[RepoObject_fullname]
, T.[RepoObject_guid] = S.[RepoObject_guid]
, T.[RepoObject_type] = S.[RepoObject_type]

FROM [graph].[RepoObject] AS T
INNER JOIN [graph].[RepoObject_S] AS S
ON
T.[RepoObject_guid] = S.[RepoObject_guid]

WHERE
   T.[RepoObject_fullname] <> S.[RepoObject_fullname]
OR T.[RepoObject_guid] <> S.[RepoObject_guid]
OR T.[RepoObject_type] <> S.[RepoObject_type]


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'update changed'
SET @source_object = '[graph].[RepoObject_S]'
SET @target_object = '[graph].[RepoObject]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":700,"Name":"insert missing","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObject_S]","log_target_object":"[graph].[RepoObject]","log_flag_InsertUpdateDelete":"I"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',9,';',700,';',NULL);

INSERT INTO 
 [graph].[RepoObject]
 (
  [RepoObject_fullname]
, [RepoObject_guid]
, [RepoObject_type]
)
SELECT
  [RepoObject_fullname]
, [RepoObject_guid]
, [RepoObject_type]

FROM [graph].[RepoObject_S] AS S
WHERE
NOT EXISTS
(SELECT 1
FROM [graph].[RepoObject] AS T
WHERE
T.[RepoObject_guid] = S.[RepoObject_guid]
)

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'insert missing'
SET @source_object = '[graph].[RepoObject_S]'
SET @target_obje
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### graph.usp_PERSIST_RepoObjectColumn

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [graph].[usp_PERSIST_RepoObjectColumn]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[graph].[usp_PERSIST_RepoObjectColumn]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":100,"Name":"check for empty source","has_logging":0,"is_condition":1,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObjectColumn_S]"}]}*/
IF (SELECT count(*) FROM [graph].[RepoObjectColumn_S]) = 0

/*{"ReportUspStep":[{"Number":110,"Parent_Number":100,"Name":"ERROR 50110: persistence source is empty","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":0}]}*/
BEGIN
PRINT CONCAT('usp_id;Number;Parent_Number: ',10,';',110,';',100);

 THROW 50110
  , 'persistence source is empty: [graph].[RepoObjectColumn_S]'
  , 1;

END;

/*{"ReportUspStep":[{"Number":500,"Name":"delete persistence target missing in source","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObjectColumn_S]","log_target_object":"[graph].[RepoObjectColumn]","log_flag_InsertUpdateDelete":"D"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',10,';',500,';',NULL);

DELETE T
FROM [graph].[RepoObjectColumn] AS T
WHERE
NOT EXISTS
(SELECT 1 FROM [graph].[RepoObjectColumn_S] AS S
WHERE
T.[RepoObjectColumn_guid] = S.[RepoObjectColumn_guid]
)
 

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'delete persistence target missing in source'
SET @source_object = '[graph].[RepoObjectColumn_S]'
SET @target_object = '[graph].[RepoObjectColumn]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":600,"Name":"update changed","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[graph].[RepoObjectColumn_S]","log_target_object":"[graph].[RepoObjectColumn]","log_flag_InsertUpdateDelete":"U"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',10,';',600,';',NULL);

UPDATE T
SET
  T.[RepoObject_fullname] = S.[RepoObject_fullname]
, T.[RepoObject_guid] = S.[RepoObject_guid]
, T.[RepoObject_type] = S.[RepoObject_type]
, T.[RepoObjectColumn_fullname] = S.[RepoObjectColumn_fullname]
, T.[RepoObjectColumn_guid] = S.[RepoObjectColumn_guid]
, T.[RepoObjectColumn_name] = S.[RepoObjectColumn_name]
, T.[RepoObjectColumn_type] = S.[RepoObjectColumn_type]

FROM [graph].[RepoObjectColumn] AS T
INNER JOIN [graph].[RepoObjectColumn_S] AS S
ON
T.[RepoObjectColumn_guid] = S.[RepoObjectColumn_guid]

WHERE
   T.[RepoObject_fullname] <> S.[RepoObject_fullname]
OR T.[RepoObject_guid] <> S.[RepoObject_guid]
OR T.[RepoObject_type] <> S.[RepoObject_type]
OR T.[RepoObjectColumn_fullname] <> S.[RepoObjectColumn_fullname]
OR T.[RepoObjectColumn_guid] <> S.[RepoObjectColumn_guid]
OR T.[RepoObjectColumn_name] <> S.[RepoObjectColumn_name]
OR T.[RepoObjectColumn_type] <> S.[RepoObjectColumn_type] OR (S.[RepoObjectColumn_type] IS NULL AND NOT T.[RepoObjectColumn_type] IS NULL) OR (NOT S.[RepoObjectColumn_type] IS NULL AND T.[RepoObjectColumn_type] IS NULL)


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'update changed'
SET @source_object = '[graph].[RepoObjectColumn_S]'
SET @target_object = '[graph].[RepoObjectColumn]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":700,"Name":"insert missing","has_l
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.LONGPRINT

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @Sql | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

create PROCEDURE repo.[LONGPRINT] @Sql nvarchar(max) AS
BEGIN
	DECLARE
		@len int,
		@CRpos int,
		@SqlOut nvarchar(4000)

	SET @len =2000
	WHILE @Sql IS NOT NULL
	BEGIN
		IF LEN(@SQL) <= @len
		BEGIN
			PRINT @SQL
			BREAK
		END ELSE
		BEGIN
			SET @CRpos = CHARINDEX(CHAR(10), @Sql, @len)
			IF @CRpos - @len < 2000
				SET @SqlOut = LEFT(@Sql, @CRpos)
			ELSE BEGIN
				RAISERROR ('OOPS! The game is over :(', 16, 1)
			END
			PRINT @SqlOut
			SET @Sql = RIGHT(@Sql, LEN(@Sql) - @CRpos)
		END
	END
END
```

</details>

[Back to top](#dhw_self)

### repo.usp_connect_database

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @dwh_database_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
example

[repo].[usp_connect_database]
@dwh_database_name = 'dwh_PerformanceAnalytics'

[repo].[usp_connect_database]
@dwh_database_name = 'WideWorldImporters-test'


*/
CREATE PROCEDURE [repo].[usp_connect_database] (@dwh_database_name NVARCHAR(128))
AS
--
--ensure existence of required parameters like 'dwh_database_name'
EXEC [repo].[usp_init_parameter]

--ensure [repo].[spt_values] is filled, otherwise extended properties will not be written into database
EXEC [repo].[usp_init_spt_values]

DECLARE @dwh_database_name_old NVARCHAR(128) = (
  SELECT [repo].[fs_dwh_database_name]()
  )

EXEC [repo].[usp_parameter_insert_update] @Parameter_name = 'dwh_database_name'
 , @Parameter_value = @dwh_database_name

--this required every time, in case synonyms are corrupt or new synonyms have been added
--IF @dwh_database_name <> ISNULL(@dwh_database_name_old , '')
BEGIN
 DECLARE @SQLString NVARCHAR(4000)
 DECLARE @ParmDefinition NVARCHAR(500)

 SET @SQLString = 
  '
DROP SYNONYM  IF EXISTS [sys_dwh].[columns]
DROP SYNONYM  IF EXISTS [sys_dwh].[computed_columns]
DROP SYNONYM  IF EXISTS [sys_dwh].[default_constraints]
DROP SYNONYM  IF EXISTS [sys_dwh].[dm_exec_describe_first_result_set]
DROP SYNONYM  IF EXISTS [sys_dwh].[dm_sql_referenced_entities]
DROP SYNONYM  IF EXISTS [sys_dwh].[extended_properties]
DROP SYNONYM  IF EXISTS [sys_dwh].[foreign_key_columns]
DROP SYNONYM  IF EXISTS [sys_dwh].[foreign_keys]
DROP SYNONYM  IF EXISTS [sys_dwh].[identity_columns]
DROP SYNONYM  IF EXISTS [sys_dwh].[indexes]
DROP SYNONYM  IF EXISTS [sys_dwh].[index_columns]
DROP SYNONYM  IF EXISTS [sys_dwh].[objects]
DROP SYNONYM  IF EXISTS [sys_dwh].[parameters]
DROP SYNONYM  IF EXISTS [sys_dwh].[schemas]
DROP SYNONYM  IF EXISTS [sys_dwh].[sp_addextendedproperty]
DROP SYNONYM  IF EXISTS [sys_dwh].[sp_updateextendedproperty]
DROP SYNONYM  IF EXISTS [sys_dwh].[sql_expression_dependencies]
DROP SYNONYM  IF EXISTS [sys_dwh].[sql_modules]
DROP SYNONYM  IF EXISTS [sys_dwh].[tables]
DROP SYNONYM  IF EXISTS [sys_dwh].[types]

CREATE SYNONYM [sys_dwh].[columns] FOR [' 
  + @dwh_database_name + '].[sys].[columns]
CREATE SYNONYM [sys_dwh].[computed_columns] FOR [' + @dwh_database_name + '].[sys].[computed_columns]
CREATE SYNONYM [sys_dwh].[default_constraints] FOR [' + @dwh_database_name + '].[sys].[default_constraints]
CREATE SYNONYM [sys_dwh].[dm_exec_describe_first_result_set] FOR [' + @dwh_database_name + '].[sys].[dm_exec_describe_first_result_set]
CREATE SYNONYM [sys_dwh].[dm_sql_referenced_entities] FOR [' + @dwh_database_name + '].[sys].[dm_sql_referenced_entities]
CREATE SYNONYM [sys_dwh].[extended_properties] FOR [' + @dwh_database_name + '].[sys].[extended_properties]
CREATE SYNONYM [sys_dwh].[foreign_key_columns] FOR [' + @dwh_database_name + '].[sys].[foreign_key_columns]
CREATE SYNONYM [sys_dwh].[foreign_keys] FOR [' + @dwh_database_name + '].[sys].[foreign_keys]
CREATE SYNONYM [sys_dwh].[identity_columns] FOR [' + @dwh_database_name + '].[sys].[identity_columns]
CREATE SYNONYM [sys_dwh].[indexes] FOR [' + @dwh_database_name + '].[sys].[indexes]
CREATE SYNONYM [sys_dwh].[index_columns] FOR [' + @dwh_database_name + '].[sys].[index_columns]
CREATE SYNONYM [sys_dwh].[objects] FOR [' + @dwh_database_name + 
  '].[sys].[objects]
CREATE SYNONYM [sys_dwh].[parameters] FOR [' + @dwh_database_name + '].[sys].[parameters]
CREATE SYNONYM [sys_dwh].[schemas] FOR [' + @dwh_database_name + '].[sys].[schemas]
CREATE SYNONYM [sys_dwh].[sp_addextendedproperty] FOR [' + @dwh_database_name + '].[sp_addextendedproperty]
CREATE SYNONYM [sys_dwh].[sp_updateextendedproperty] FOR [' + @dwh_database_name + '].[sp_updateextendedproperty]
CREATE SYNONYM [sys_dwh].[sql_expression_dependencies] FOR [' + @dwh_database_name + '].[sys].[sql_expression_dependencies]
CREATE SYNONYM [sys_dwh].[sql_modules] FOR [' + @dwh_database_name + '].[sys].[sql_modules]
CREATE SYNONYM [sys_dwh].[tables] FOR [' + @dwh_database_name + '].[sys].[tables]
CREATE SYNONYM [sys_dwh].[types] FOR [' + @dwh_database_name + '].[sys].[types]
'

 EXECUTE sp_executesql @SQLString
END
```

</details>

[Back to top](#dhw_self)

### repo.usp_ExecutionLog_insert

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |
| @current_execution_guid | UNIQUEIDENTIFIER | no |  |
| @proc_id | INT | no |  |
| @proc_schema_name | NVARCHAR(128) | no |  |
| @proc_name | NVARCHAR(128) | no |  |
| @event_info | NVARCHAR(MAX) | no |  |
| @step_id | INT | no |  |
| @step_name | NVARCHAR(1000) | no |  |
| @source_object | NVARCHAR(261) | no |  |
| @target_object | NVARCHAR(261) | no |  |
| @inserted | INT | no |  |
| @updated | INT | no |  |
| @deleted | INT | no |  |
| @info_01 | SQL_VARIANT | no |  |
| @info_02 | SQL_VARIANT | no |  |
| @info_03 | SQL_VARIANT | no |  |
| @info_04 | SQL_VARIANT | no |  |
| @info_05 | SQL_VARIANT | no |  |
| @info_06 | SQL_VARIANT | no |  |
| @info_07 | SQL_VARIANT | no |  |
| @info_08 | SQL_VARIANT | no |  |
| @info_09 | SQL_VARIANT | no |  |
| @parameter_01 | SQL_VARIANT | no |  |
| @parameter_02 | SQL_VARIANT | no |  |
| @parameter_03 | SQL_VARIANT | no |  |
| @parameter_04 | SQL_VARIANT | no |  |
| @parameter_05 | SQL_VARIANT | no |  |
| @parameter_06 | SQL_VARIANT | no |  |
| @parameter_07 | SQL_VARIANT | no |  |
| @parameter_08 | SQL_VARIANT | no |  |
| @parameter_09 | SQL_VARIANT | no |  |
| @parameter_10 | SQL_VARIANT | no |  |
| @parameter_11 | SQL_VARIANT | no |  |
| @parameter_12 | SQL_VARIANT | no |  |
| @parameter_13 | SQL_VARIANT | no |  |
| @parameter_14 | SQL_VARIANT | no |  |
| @parameter_15 | SQL_VARIANT | no |  |
| @parameter_16 | SQL_VARIANT | no |  |
| @parameter_17 | SQL_VARIANT | no |  |
| @parameter_18 | SQL_VARIANT | no |  |
| @parameter_19 | SQL_VARIANT | no |  |
| @parameter_20 | SQL_VARIANT | no |  |
| @execution_log_id | BIGINT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
only insert, no update

to get duration and grouping, use unique combinations of keys,for example

- @execution_instance_guid (which should be unique per execution)
- @ssis_execution_id
- @sub_execution_id
- @proc_id
- @step_id
- @parent_execution_log_id

if a procedure is called several times per ssis_execution, for example the @ssis_execution_id could be used as group and @execution_instance_guid for individual execution

it is also possible to use the @execution_log_id output parameter ad to store it back as @parent_execution_log_id

*/
CREATE PROCEDURE [repo].[usp_ExecutionLog_insert] @execution_instance_guid UNIQUEIDENTIFIER
 , @ssis_execution_id BIGINT = NULL
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
 , @current_execution_guid UNIQUEIDENTIFIER = NULL
 , @proc_id INT = NULL
 , @proc_schema_name NVARCHAR(128) = NULL
 , @proc_name NVARCHAR(128) = NULL
 , @event_info NVARCHAR(MAX) = NULL
 , @step_id INT = NULL
 , @step_name NVARCHAR(1000) = NULL
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @inserted INT = NULL
 , @updated INT = NULL
 , @deleted INT = NULL
 , @info_01 SQL_VARIANT = NULL
 , @info_02 SQL_VARIANT = NULL
 , @info_03 SQL_VARIANT = NULL
 , @info_04 SQL_VARIANT = NULL
 , @info_05 SQL_VARIANT = NULL
 , @info_06 SQL_VARIANT = NULL
 , @info_07 SQL_VARIANT = NULL
 , @info_08 SQL_VARIANT = NULL
 , @info_09 SQL_VARIANT = NULL
 , @parameter_01 SQL_VARIANT = NULL
 , @parameter_02 SQL_VARIANT = NULL
 , @parameter_03 SQL_VARIANT = NULL
 , @parameter_04 SQL_VARIANT = NULL
 , @parameter_05 SQL_VARIANT = NULL
 , @parameter_06 SQL_VARIANT = NULL
 , @parameter_07 SQL_VARIANT = NULL
 , @parameter_08 SQL_VARIANT = NULL
 , @parameter_09 SQL_VARIANT = NULL
 , @parameter_10 SQL_VARIANT = NULL
 , @parameter_11 SQL_VARIANT = NULL
 , @parameter_12 SQL_VARIANT = NULL
 , @parameter_13 SQL_VARIANT = NULL
 , @parameter_14 SQL_VARIANT = NULL
 , @parameter_15 SQL_VARIANT = NULL
 , @parameter_16 SQL_VARIANT = NULL
 , @parameter_17 SQL_VARIANT = NULL
 , @parameter_18 SQL_VARIANT = NULL
 , @parameter_19 SQL_VARIANT = NULL
 , @parameter_20 SQL_VARIANT = NULL
 , @execution_log_id BIGINT = NULL OUTPUT
AS
DECLARE @start_dt DATETIME = GETDATE();

INSERT INTO repo.ExecutionLog (
 [execution_instance_guid]
 , [parent_execution_log_id]
 , [ssis_execution_id]
 , [sub_execution_id]
 , [current_execution_guid]
 , [proc_id]
 , [proc_schema_name]
 , [proc_name]
 , [event_info]
 , [step_id]
 , [step_name]
 , [created_dt]
 , [source_object]
 , [target_object]
 , [inserted]
 , [updated]
 , [deleted]
 , [info_01]
 , [info_02]
 , [info_03]
 , [info_04]
 , [info_05]
 , [info_06]
 , [info_07]
 , [info_08]
 , [info_09]
 , [parameter_01]
 , [parameter_02]
 , [parameter_03]
 , [parameter_04]
 , [parameter_05]
 , [parameter_06]
 , [parameter_07]
 , [parameter_08]
 , [parameter_09]
 , [parameter_10]
 , [parameter_11]
 , [parameter_12]
 , [parameter_13]
 , [parameter_14]
 , [parameter_15]
 , [parameter_16]
 , [parameter_17]
 , [parameter_18]
 , [parameter_19]
 , [parameter_20]
 )
VALUES (
 @execution_instance_guid
 , @parent_execution_log_id
 , @ssis_execution_id
 , @sub_execution_id
 , @current_execution_guid
 , @proc_id
 , @proc_schema_name
 , @proc_name
 , @event_info
 , @step_id
 , @step_name
 , @start_dt
 , @source_object
 , @target_object
 , @inserted
 , @updated
 , @deleted
 , @info_01
 , @info_02
 , @info_03
 , @info_04
 , @info_05
 , @info_06
 , @info_07
 , @info_08
 , @info_09
 , @parameter_01
 , @parameter_02
 , @parameter_03
 , @parameter_04
 , @parameter_05
 , @parameter_06
 , @parameter_07
 , @parameter_08
 , @parameter_09
 , @parameter_10
 , @parameter_11
 , @parameter_12
 , @parameter_13
 , @parameter_14
 , @parameter_15
 , @parameter_16
 , @parameter_17
 , @parameter_18
 , @parameter_19
 , @parameter_20
 );

SET @execution_log_id = SCOPE_IDENTITY();
```

</details>

[Back to top](#dhw_self)

### repo.usp_generate_merge

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
create the procedure sp_generate_merge in master database
details: https://github.com/readyroll/generate-sql-merge

issue in orignal procedure with sql_variant content!

this will create sql statements to merge data into a target table
these scrpits can be included in database projects to use in post deployment scripts in DACPAC

https://documentation.red-gate.com/rr1/key-concepts/data-population/static-data#StaticData-offline

ATTENTION:
for sql_variant type the procedure generates wrong code:
[repo].[Parameter]
[repo].[RepoObjectColumnProperty]
[repo].[RepoObjectProperty]

*/

CREATE   procedure [repo].[usp_generate_merge]
AS

--issues with sql_variant
EXEC sp_generate_merge @table_name = 'Parameter', @schema = 'repo', @debug_mode = 1

EXEC sp_generate_merge @table_name = 'GeneratorUsp', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'GeneratorUspParameter', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'GeneratorUspStep', @schema = 'repo', @debug_mode = 1

--todo: store and get all columns in extended properties
/*
TITLE: Microsoft SQL Server Management Studio
------------------------------

Unable to show XML. The following error happened:
Unexpected end of file while parsing PI has occurred. Line 162, position 154777.

One solution is to increase the number of characters retrieved from the server for XML data. To change this setting, on the Tools menu, click Options.

------------------------------
BUTTONS:

OK
------------------------------


Menu > Tools > Options > Query Results > Results to Grid > XML Data
default is 2 MB, set to unlimited

But this can crash SSMS

*/
EXEC sp_generate_merge @table_name = 'RepoObject', @schema = 'repo', @debug_mode = 1
--todo: store and get all columns in extended properties
EXEC sp_generate_merge @table_name = 'RepoObject_persistence', @schema = 'repo', @debug_mode = 1
-- RepoObject_SqlModules can be easy restored using the python script SqlParser.py
EXEC sp_generate_merge @table_name = 'RepoObject_SqlModules', @schema = 'repo', @debug_mode = 1

----not required, get properties using [repo].[usp_sync_ExtendedProperties_Sys2Repo_InsertUpdate]
----issues with sql_variant
--EXEC sp_generate_merge @table_name = 'RepoObjectProperty', @schema = 'repo', @debug_mode = 1

EXEC sp_generate_merge @table_name = 'RepoObjectColumn', @schema = 'repo', @debug_mode = 1
----not required, get properties using [repo].[usp_sync_ExtendedProperties_Sys2Repo_InsertUpdate]
----issues with sql_variant
--EXEC sp_generate_merge @table_name = 'RepoObjectColumnProperty', @schema = 'repo', @debug_mode = 1

----currently only the SqlParser data is used
--EXEC sp_generate_merge @table_name = 'RepoObjectSource_FirstResultSet', @schema = 'repo', @debug_mode = 1
--EXEC sp_generate_merge @table_name = 'RepoObjectSource_QueryPlan', @schema = 'repo', @debug_mode = 1

EXEC sp_generate_merge @table_name = 'Index_virtual', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'IndexColumn_virtual', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'Index_Settings', @schema = 'repo', @debug_mode = 1

EXEC sp_generate_merge @table_name = 'ProcedureInstance', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'ProcedureInstanceDependency', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'Workflow', @schema = 'repo', @debug_mode = 1
EXEC sp_generate_merge @table_name = 'WorkflowStep', @schema = 'repo', @debug_mode = 1

```

</details>

[Back to top](#dhw_self)

### repo.usp_GeneratorUsp_insert_update_persistence

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_GeneratorUsp_insert_update_persistence]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_GeneratorUsp_insert_update_persistence]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":210,"Name":"delete old usp, which doesn't exist anymore","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObject_gross]","log_target_object":" [repo].[GeneratorUsp]","log_flag_InsertUpdateDelete":"d"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',3,';',210,';',NULL);

--ATTENTION, destructive!
--we should delete only usp definitions for persistence!
DELETE u
FROM [repo].[GeneratorUsp] [u]
WHERE LEFT([u].[usp_name], 12) = 'usp_PERSIST_'
 AND NOT EXISTS (
  SELECT 1
  FROM [repo].[RepoObject_gross] AS [ro]
  WHERE [u].[usp_schema] = [ro].[RepoObject_schema_name]
   AND [u].[usp_name] = [ro].[usp_persistence_name]
  )

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'delete old usp, which doesn''t exist anymore'
SET @source_object = '[repo].[RepoObject_gross]'
SET @target_object = ' [repo].[GeneratorUsp]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":310,"Name":"insert new usp","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObject_gross]","log_target_object":"[repo].[GeneratorUsp]","log_flag_InsertUpdateDelete":"i"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',3,';',310,';',NULL);

INSERT INTO [repo].[GeneratorUsp] (
 [usp_schema]
 , [usp_name]
 , [has_logging]
 )
SELECT [usp_schema] = [RepoObject_schema_name]
 , [usp_name] = [usp_persistence_name]
 , 1
FROM [repo].[RepoObject_gross] AS ro
WHERE [is_persistence] = 1
 AND NOT EXISTS (
  SELECT 1
  FROM [repo].[GeneratorUsp] AS [u]
  WHERE [u].[usp_schema] = [ro].[RepoObject_schema_name]
   AND [u].[usp_name] = [ro].[usp_persistence_name]
  )

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'insert new usp'
SET @source_object = '[repo].[RepoObject_gross]'
SET @target_object = '[repo].[GeneratorUsp]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":510,"Name":"update steps, changed","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[GeneratorUspStep_Persistence]","log_target_object":"[repo].[GeneratorUspStep]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',3,';',510,';',NULL);

UPDATE T
SET [Parent_Number] = [S].[Parent_Number]
 , [Name] = [S].[Name]
 , [has_logging] = [S].[has_logging]
 , [is_condition] = [S].[is_condition]
 , [is_SubProcedure] = [S].[is_SubProcedure]
 , [Statement] = [S].[Statement]
 , [log_source_object] = [S].[log_source_object]
 , [log_target_object] = [S].[log_target_object]
 , [log_flag_InsertUpdateDelete] = [S].[log_flag_InsertUpdateDelete]
FROM [repo].[GeneratorUspStep] [T]
INNER JOIN [repo].[GeneratorUspStep_Persistence] AS [S]
 ON [T].[usp_id] = [S].[usp_id]
  AND [T].[Number] = [S].[Number]
WHERE
 --
 [T].[Parent_Number] <> [S].[Parent_Number]
 OR [T].[Parent_Number] IS NULL
 AND NOT [S].[Parent_Number] IS NULL
 OR NOT [T].[Parent_Number] IS NULL
 AND [S].[Parent_Number] IS NULL
 --
 OR [T].[Name] <> [S].[Name]
 OR [T].[Name] 
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_Index_finish

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_Index_finish]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_Index_finish]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":210,"Name":"[repo].[usp_Index_Settings]","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_Index_Settings]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id


/*{"ReportUspStep":[{"Number":220,"Name":"DELETE [repo].[Index_virtual] without columns","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[IndexColumn_virtual]","log_target_object":"[repo].[Index_virtual]","log_flag_InsertUpdateDelete":"d"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',15,';',220,';',NULL);

DELETE iv
FROM [repo].[Index_virtual] iv
WHERE NOT EXISTS (
  SELECT 1
  FROM [repo].[IndexColumn_virtual] icv
  WHERE icv.index_guid = iv.index_guid
  )


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'DELETE [repo].[Index_virtual] without columns'
SET @source_object = '[repo].[IndexColumn_virtual]'
SET @target_object = '[repo].[Index_virtual]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":410,"Name":"DELETE duplicates by pattern","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[Index_gross]","log_target_object":"[repo].[Index_virtual]","log_flag_InsertUpdateDelete":"d"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',15,';',410,';',NULL);

DELETE iv
FROM [repo].[Index_virtual] [iv]
WHERE EXISTS (
  SELECT 1
  FROM [repo].[Index_gross] AS [ig]
  WHERE [ig].[index_guid] = [iv].[index_guid]
   AND [ig].[RowNumber_PatternPerParentObject] > 1
  )

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'DELETE duplicates by pattern'
SET @source_object = '[repo].[Index_gross]'
SET @target_object = '[repo].[Index_virtual]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":510,"Name":"SET [IndexSemanticGroup] = [TSource].[IndexSemanticGroup] (via [T1].[referenced_index_guid] = [TSource].[index_guid])","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[Index_Settings]","log_target_object":"[repo].[Index_Settings]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',15,';',510,';',NULL);

--ATTENTION:
--repo.Index_IndexSemanticGroup.[IndexSemanticGroup] could also be set to NULL where it was assigned before
--maybe this should be avoided?
--but the strict inheritance is consequent
UPDATE repo.[Index_Settings]
SET [IndexSemanticGroup] = [TSource].[IndexSemanticGroup]
FROM [repo].[Index_virtual] AS [T1]
INNER JOIN [repo].[Index_Settings] AS [TSource]
 ON [T1].[referenced_index_guid] = [TSource].[index_guid]
INNER JOIN [repo].[Index_Settings]
 ON [T1].[index_guid] = [repo].[Index_Settings].[index_guid]
  AND [TSource].[IndexPatternColumnDatatype] = [repo].[Index_Settings].[IndexPatternColumnDatatype]
WHERE ISNULL([repo].[Index_Settings].[IndexSemanticGroup], '') <> ISNULL([TSource].[IndexSemanticGroup], '')



/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_Index_ForeignKey

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_Index_ForeignKey]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_Index_ForeignKey]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":310,"Name":"create missing Index_virtual for ForeignKey","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[ForeignKey_Index_guid]","log_target_object":"[repo].[Index_virtual]"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',18,';',310,';',NULL);

DECLARE fk_cursor CURSOR READ_ONLY
FOR
SELECT [referencing_RepoObject_guid]
 , [referencing_IndexPatternColumnName]
FROM repo.ForeignKey_Index_guid AS fk
WHERE (NOT ([referencing_RepoObject_guid] IS NULL))
 AND ([referencing_index_guid] IS NULL)

UNION

SELECT [referenced_RepoObject_guid]
 , [referenced_IndexPatternColumnName]
FROM repo.ForeignKey_Index_guid AS fk
WHERE (NOT ([referenced_RepoObject_guid] IS NULL))
 AND ([referenced_index_guid] IS NULL)

DECLARE @RepoObject_guid UNIQUEIDENTIFIER
DECLARE @IndexPatternColumnName NVARCHAR(4000)

OPEN fk_cursor

FETCH NEXT
FROM fk_cursor
INTO @RepoObject_guid
 , @IndexPatternColumnName

WHILE (@@fetch_status <> - 1)
BEGIN
 IF (@@fetch_status <> - 2)
 BEGIN
  PRINT @RepoObject_guid
  PRINT @IndexPatternColumnName

  EXEC [repo].[usp_Index_virtual_InsertUpdate] @RepoObject_guid = @RepoObject_guid
   , @IndexPatternColumnName = @IndexPatternColumnName
   , @is_index_disabled = 1
 END

 FETCH NEXT
 FROM fk_cursor
 INTO @RepoObject_guid
  , @IndexPatternColumnName
END

CLOSE fk_cursor

DEALLOCATE fk_cursor


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'create missing Index_virtual for ForeignKey'
SET @source_object = '[repo].[ForeignKey_Index_guid]'
SET @target_object = '[repo].[Index_virtual]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object

-- Logging END --

/*{"ReportUspStep":[{"Number":410,"Name":"[repo].[usp_Index_finish]","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_Index_finish]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id



--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
```

</details>

[Back to top](#dhw_self)

### repo.usp_index_inheritance

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_Index_inheritance]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_Index_inheritance]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":200,"Name":"[repo].[usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id


/*{"ReportUspStep":[{"Number":310,"Name":"DELETE (if it is a referencing index (NOT [referenced_index_guid] IS NULL), but referenced index is missing)","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[IndexReferencedReferencing_HasFullColumnsInReferencing]","log_target_object":"[repo].[Index_virtual]","log_flag_InsertUpdateDelete":"d"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',17,';',310,';',NULL);

DELETE
FROM repo.[Index_virtual]
WHERE NOT [referenced_index_guid] IS NULL
 AND (
  [RowNumberInReferencing] IS NULL
  OR [referenced_index_guid] NOT IN (
   SELECT [source_index_guid] AS [index_guid]
   FROM [repo].[IndexReferencedReferencing_HasFullColumnsInReferencing] AS [T1]
   )
  )

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'DELETE (if it is a referencing index (NOT [referenced_index_guid] IS NULL), but referenced index is missing)'
SET @source_object = '[repo].[IndexReferencedReferencing_HasFullColumnsInReferencing]'
SET @target_object = '[repo].[Index_virtual]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":410,"Name":"INSERT (Index which should be inherited in referenced, but not yet referenced)","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[IndexReferencedReferencing_HasFullColumnsInReferencing]","log_target_object":"[repo].[Index_virtual]","log_flag_InsertUpdateDelete":"i"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',17,';',410,';',NULL);

INSERT INTO repo.[Index_virtual] (
 [parent_RepoObject_guid]
 , [referenced_index_guid]
 , [RowNumberInReferencing]
 , [index_type]
 )
SELECT [referencing_RepoObject_guid]
 , [source_index_guid] AS [index_guid]
 , [RowNumberInReferencing]
 , [source_index_type]
FROM repo.IndexReferencedReferencing_HasFullColumnsInReferencing AS T1
WHERE (
  [referenced_index_guid] IS NULL
  OR [RowNumberInReferencing_Target] IS NULL
  )
 --avoid duplicate index per [IndexPatternColumnGuid] and RepoObject
 AND NOT EXISTS (
  SELECT 1
  FROM [repo].[Index_virtual_IndexPatternColumnGuid] AS [T2]
  WHERE [T2].[parent_RepoObject_guid] = [T1].[referencing_RepoObject_guid]
   AND [T2].[IndexPatternColumnGuid] = [T1].[referencing_IndexPatternColumnGuid]
  )


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'INSERT (Index which should be inherited in referenced, but not yet referenced)'
SET @source_object = '[repo].[IndexReferencedReferencing_HasFullColumnsInReferencing]'
SET @target_object = '[repo].[Index_virtual]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
-- 
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_Index_Settings

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE PROCEDURE [repo].[usp_Index_Settings]
 -- some optional parameters, used for logging
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'

--SET @source_object = NULL
--SET @target_object = NULL
EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT;

--
----START
--
--[repo].[Index_IndexPattern] is based on [repo].[IndexColumn_union]
--Index without colums will be deleted
DELETE T2
FROM [repo].[Index_Settings] [T2]
WHERE NOT EXISTS (
  SELECT [index_guid]
  FROM [repo].[Index_IndexPattern] AS [T1]
  WHERE [T2].[index_guid] = [T1].[index_guid]
  )

SET @rows = @@rowcount;
SET @step_id = @step_id + 1;
SET @step_name = 'DELETE'
SET @source_object = '[repo].[Index_IndexPattern]'
SET @target_object = '[repo].[Index_Settings]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = @rows
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

INSERT INTO repo.[Index_Settings] (
 [index_guid]
 , [IndexPatternColumnName]
 , [IndexPatternColumnDatatype]
 )
SELECT [index_guid]
 , [IndexPatternColumnName]
 , [IndexPatternColumnDatatype]
FROM repo.Index_IndexPattern AS T1
WHERE NOT EXISTS (
  SELECT [index_guid]
  FROM [repo].[Index_Settings] AS [T2]
  WHERE [T2].[index_guid] = [T1].[index_guid]
  )

SET @rows = @@rowcount;
SET @step_id = @step_id + 1;
SET @step_name = 'INSERT'
SET @source_object = '[repo].[Index_IndexPattern]'
SET @target_object = '[repo].[Index_Settings]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

UPDATE repo.[Index_Settings]
SET [IndexPatternColumnName] = [T1].[IndexPatternColumnName]
 , [IndexPatternColumnDatatype] = [T1].[IndexPatternColumnDatatype]
FROM [repo].[Index_Settings] [T2]
LEFT JOIN [repo].[Index_IndexPattern] AS [T1]
 ON [T2].[index_guid] = [T1].[index_guid]
WHERE [T1].[IndexPatternColumnName] <> ISNULL([T2].[IndexPatternColumnName], '')
 OR [T1].[IndexPatternColumnDatatype] <> ISNULL([T2].[IndexPatternColumnDatatype], '')

SET @rows = @@rowcount;
SET @step_id = @step_id + 1;
SET @step_name = 'UPDATE'
SET @source_object = '[repo].[Index_IndexPattern]'
SET @target_object = '[repo].[Index_Settings]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = @rows
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

--
--END
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1;
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
```

</details>

[Back to top](#dhw_self)

### repo.usp_Index_virtual_InsertUpdate

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @RepoObject_fullname | NVARCHAR(261) | no |  |
| @IndexPatternColumnName | NVARCHAR(4000) | no |  |
| @index_name | NVARCHAR(128) | no |  |
| @index_type | TINYINT | no |  |
| @is_index_disabled | BIT | no |  |
| @is_index_primary_key | BIT | no |  |
| @is_index_unique | BIT | no |  |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
Index will be inserted (updated) into repo.[Index_virtual]
but it will not be visible in [repo].[Index_gross]
until it was also included into [repo].[Index_Settings]

run
EXEC [repo].[usp_Index_finish]

--test:
EXEC repo.usp_Index_virtual_InsertUpdate 
 @RepoObject_fullname = '[dbo].[view_1]'
 , @IndexPatternColumnName = 'aaa_id,bbb'

EXEC repo.usp_Index_virtual_InsertUpdate 
 @RepoObject_fullname = '[dbo].[view_1]'
 , @IndexPatternColumnName = 'aaa_id'
 , @is_index_primary_key = 1

EXEC repo.usp_Index_virtual_InsertUpdate 
 @RepoObject_fullname = '[repo].[RepoObjectColumn_gross]'
 , @IndexPatternColumnName = 'RepoObjectColumn_guid'
 , @is_index_primary_key = 1

EXEC repo.usp_Index_virtual_InsertUpdate 
 @RepoObject_fullname = '[graph].[RepoObjectColumn_S]'
 , @IndexPatternColumnName = 'RepoObjectColumn_guid'
 , @is_index_primary_key = 1

EXEC [repo].[usp_Index_finish]



index_type

Type of index:
0 = Heap
1 = Clustered
2 = Nonclustered
3 = XML
4 = Spatial
5 = Clustered columnstore index. Applies to: SQL Server 2014 (12.x) and later.
6 = Nonclustered columnstore index. Applies to: SQL Server 2012 (11.x) and later.
7 = Nonclustered hash index. Applies to: SQL Server 2014 (12.x) and later.
*/
CREATE
 

 PROCEDURE [repo].[usp_Index_virtual_InsertUpdate] @RepoObject_guid UNIQUEIDENTIFIER = NULL --if @RepoObject_guid is NULL, then @RepoObject_fullname is used
 , @RepoObject_fullname NVARCHAR(261) = NULL --will be used to find matching @RepoObject_guid, if @RepoObject_guid is NULL; use [schema].[TableOrView]
 , @IndexPatternColumnName NVARCHAR(4000) = NULL --a semicolon separated list to define the Index, for example 'aaa;bbb;ccc'
 , @index_name NVARCHAR(128) = NULL
 , @index_type TINYINT = 2 --1 Clustered, 2 Nonclustered
 , @is_index_disabled BIT = 0
 , @is_index_primary_key BIT = 0
 , @is_index_unique BIT = 0
 -- some optional parameters, used for logging
 , @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT
 , @parameter_01 = @RepoObject_guid
 , @parameter_02 = @RepoObject_fullname
 , @parameter_03 = @IndexPatternColumnName
 , @parameter_04 = @index_name
 , @parameter_05 = @index_type
 , @parameter_06 = @is_index_disabled
 , @parameter_07 = @is_index_primary_key
 , @parameter_08 = @is_index_unique
 , @parameter_09 = NULL
 , @parameter_10 = NULL
 , @parameter_11 = NULL
 , @parameter_12 = NULL
 , @parameter_13 = NULL

--
----START
--
DECLARE @table TABLE ([guid] UNIQUEIDENTIFIER)
DECLARE @index_guid UNIQUEIDENTIFIER

IF @RepoObject_guid IS NULL
 SET @RepoObject_guid = (
   SELECT RepoObject_guid
   FROM [repo].[RepoObject]
   WHERE [RepoObject_fullname] = @RepoObject_fullname
   )

--check existence of @RepoObject_guid
IF NOT EXISTS (
  SELECT 1
  FROM [repo].[RepoObject]
  WHERE [RepoObject_guid] = @RepoObject_guid
  )
BEGIN
 SET @step_name = CONCAT (
   'RepoObject_guid does not exist;'
   , @RepoObject_guid
   , ';'
   , @RepoObject_fullname
   );

 THROW 51001
  , @step_name
  , 1;
END

--make sure the @table table is empty
DELETE @table

INSERT INTO repo.[Index_virtual] (
 [parent_RepoObject_guid]
 , [index_name]
 , [index_type]
 , [is_index_disabled]
 , [is_index_primary_key]
 , [is_index_unique]
 )
OUTPUT [INSERTED].[index_guid]
INTO @table
SELECT @RepoObject_guid
 , @index_name
 , @index_type
 , @is_index_disabled
 , @is_index_primary_key
 , IIF(@is_index_primary_key = 1, 1, @is_index_unique)

SET @index_guid = (
  SELECT [guid]
  FROM @table
  )

/*
--test to get the string_split in the right order:

DECLARE @IndexPatternColumnName NVARCHAR(max) = 'z; y; aaa;bbb;ccc ddd; eee;fff ;ggg'

--there is no garantee to get the strings in the right order, but "normally" it works
--the result for ASC or DESC is the same
--https://feedback.azure.com/forums/908035-sql-server/suggestions/32902852-add-row-position-column-to-string-split
SELECT TRIM(value) AS index_column_name
 , row_number() OVER (
  ORDER BY (
    SELECT NULL
    )
  ) AS [index_column_id]
FROM STRING_SPLIT(@IndexPatternColumnName, ',')

*/
--todo: concept to insert [is_descending_key]
--or update manually if required
INSERT INTO [repo].[IndexColumn_virtual] (
 [index_guid]
 , [index_column_id]
 , [RepoObjectColumn_guid]
 , [is_descending_key]
 )
SELECT @index_guid
 , ColTable.index_column_id
 , roc.RepoObjectColumn_guid
 , 0
FROM (
 SELECT TRIM(value) AS index_column_name
  , row_number() OVER (
   ORDER BY (
     SELECT NULL
     )
   ) AS [index_column_id]
 FROM STRING_SPLIT(@IndexPatternColumnName, ',')
 ) ColTable
LEFT JOIN [repo].[RepoObjectColumn] roc
 ON roc.RepoObject_guid = @RepoObject_guid
  AND roc.RepoObjectColumn_name = index_column_name

SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1;
SET @step_name = 'INSERT Index Columns'
SET @source_object = '[repo].[RepoObjectColumn]'
SET @target_object = '[repo].[IndexColumn_virtual]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

--
--
--END
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1;
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_exe
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_init_parameter

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE PROCEDURE [repo].[usp_init_parameter]
AS
--
INSERT INTO [repo].[Parameter] (
 [Parameter_name]
 , [sub_Parameter]
 , [Parameter_desciption]
 , [Parameter_default_value]
 )
SELECT [Parameter_name]
 , [sub_Parameter]
 , [Parameter_desciption]
 , [Parameter_default_value]
FROM [repo].[Parameter_default] AS T1
WHERE NOT EXISTS (
  SELECT 1
  FROM [repo].[Parameter] AS [target]
  WHERE [target].[Parameter_name] = [T1].[Parameter_name]
   AND [target].[sub_Parameter] = [T1].[sub_Parameter]
  )

UPDATE T2
SET [T2].[Parameter_desciption] = [source].[Parameter_desciption]
 , [T2].[Parameter_default_value] = [source].[Parameter_default_value]
FROM [repo].[Parameter] AS [T2]
INNER JOIN [repo].[Parameter_default] AS [source]
 ON [source].[Parameter_name] = [T2].[Parameter_name]
  AND [source].[sub_Parameter] = [T2].[sub_Parameter]
WHERE [T2].[Parameter_desciption] <> [source].[Parameter_desciption]
 OR (
  [T2].[Parameter_desciption] IS NULL
  AND NOT [source].[Parameter_desciption] IS NULL
  )
 OR (
  NOT [T2].[Parameter_desciption] IS NULL
  AND [source].[Parameter_desciption] IS NULL
  )
 OR [T2].[Parameter_default_value] <> [source].[Parameter_default_value]
 OR (
  [T2].[Parameter_default_value] IS NULL
  AND NOT [source].[Parameter_default_value] IS NULL
  )
 OR (
  NOT [T2].[Parameter_default_value] IS NULL
  AND [source].[Parameter_default_value] IS NULL
  )
```

</details>

[Back to top](#dhw_self)

### repo.usp_init_spt_values

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE PROCEDURE repo.usp_init_spt_values
AS
--
TRUNCATE TABLE [repo].[spt_values]

-- [noformat] don't want any formatting here, because this is created in ADS

----data script created in Azure Data Studio
--
--create table [#tempspt_values] (
--[name] [nvarchar] (35) NULL,
--[number] [int],
--[type] [nchar] (3),
--[low] [int] NULL,
--[high] [int] NULL,
--[status] [int] NULL);


insert [repo].[spt_values] ([name],[number],[type],[low],[high],[status])
select 'rpc',1,'A  ',NULL,NULL,0 UNION ALL
select 'pub',2,'A  ',NULL,NULL,0 UNION ALL
select 'sub',4,'A  ',NULL,NULL,0 UNION ALL
select 'dist',8,'A  ',NULL,NULL,0 UNION ALL
select 'dpub',16,'A  ',NULL,NULL,0 UNION ALL
select 'rpc out',64,'A  ',NULL,NULL,0 UNION ALL
select 'data access',128,'A  ',NULL,NULL,0 UNION ALL
select 'collation compatible',256,'A  ',NULL,NULL,0 UNION ALL
select 'system',512,'A  ',NULL,NULL,0 UNION ALL
select 'use remote collation',1024,'A  ',NULL,NULL,0 UNION ALL
select 'lazy schema validation',2048,'A  ',NULL,NULL,0 UNION ALL
select 'remote proc transaction promotion',4096,'A  ',NULL,NULL,0 UNION ALL
select 'YES OR NO',-1,'B  ',NULL,NULL,0 UNION ALL
select 'no',0,'B  ',NULL,NULL,0 UNION ALL
select 'yes',1,'B  ',NULL,NULL,0 UNION ALL
select 'none',2,'B  ',NULL,NULL,0 UNION ALL
select 'DATABASE STATUS',0,'D  ',NULL,NULL,0 UNION ALL
select 'autoclose',1,'D  ',NULL,NULL,0 UNION ALL
select 'select into/bulkcopy',4,'D  ',NULL,NULL,0 UNION ALL
select 'trunc. log on chkpt.',8,'D  ',NULL,NULL,0 UNION ALL
select 'torn page detection',16,'D  ',NULL,NULL,0 UNION ALL
select 'loading',32,'D  ',NULL,NULL,0 UNION ALL
select 'pre recovery',64,'D  ',NULL,NULL,0 UNION ALL
select 'recovering',128,'D  ',NULL,NULL,0 UNION ALL
select 'not recovered',256,'D  ',NULL,NULL,0 UNION ALL
select 'offline',512,'D  ',0,1,0 UNION ALL
select 'read only',1024,'D  ',NULL,NULL,0 UNION ALL
select 'dbo use only',2048,'D  ',NULL,NULL,0 UNION ALL
select 'single user',4096,'D  ',NULL,NULL,0 UNION ALL
select 'emergency mode',32768,'D  ',NULL,NULL,0 UNION ALL
select 'missing files',262144,'D  ',NULL,NULL,0 UNION ALL
select 'autoshrink',4194304,'D  ',NULL,NULL,0 UNION ALL
select 'ALL SETTABLE OPTIONS',4202013,'D  ',NULL,NULL,0 UNION ALL
select 'cleanly shutdown',1073741824,'D  ',NULL,NULL,0 UNION ALL
select 'DATABASE OPTIONS',0,'D2 ',NULL,NULL,0 UNION ALL
select 'db chaining',1024,'D2 ',NULL,NULL,0 UNION ALL
select 'numeric roundabort',2048,'D2 ',NULL,NULL,0 UNION ALL
select 'arithabort',4096,'D2 ',NULL,NULL,0 UNION ALL
select 'ANSI padding',8192,'D2 ',NULL,NULL,0 UNION ALL
select 'ANSI null default',16384,'D2 ',NULL,NULL,0 UNION ALL
select 'concat null yields null',65536,'D2 ',NULL,NULL,0 UNION ALL
select 'recursive triggers',131072,'D2 ',NULL,NULL,0 UNION ALL
select 'default to local cursor',1048576,'D2 ',NULL,NULL,0 UNION ALL
select 'quoted identifier',8388608,'D2 ',NULL,NULL,0 UNION ALL
select 'auto create statistics',16777216,'D2 ',NULL,NULL,0 UNION ALL
select 'cursor close on commit',33554432,'D2 ',NULL,NULL,0 UNION ALL
select 'ANSI nulls',67108864,'D2 ',NULL,NULL,0 UNION ALL
select 'ANSI warnings',268435456,'D2 ',NULL,NULL,0 UNION ALL
select 'full text enabled',536870912,'D2 ',NULL,NULL,0 UNION ALL
select 'auto update statistics',1073741824,'D2 ',NULL,NULL,0 UNION ALL
select 'ALL SETTABLE OPTIONS',1469283328,'D2 ',NULL,NULL,0 UNION ALL
select 'DB Owners',16384,'DBR',-1,NULL,0 UNION ALL
select 'DB Access Administrators',16385,'DBR',-1,NULL,0 UNION ALL
select 'DB Security Administrators',16386,'DBR',-1,NULL,0 UNION ALL
select 'DB DDL Administrators',16387,'DBR',-1,NULL,0 UNION ALL
select 'DB Backup Operator',16389,'DBR',-1,NULL,0 UNION ALL
select 'DB Data Reader',16390,'DBR',-1,NULL,0 UNION ALL
select 'DB Data Writer',16391,'DBR',-1,NULL,0 UNION ALL
select 'DB Deny Data Reader',16392,'DBR',-1,NULL,0 UNION ALL
select 'DB Deny Data Writer',16393,'DBR',-1,NULL,0 UNION ALL
select 'DATABASE CATEGORY',0,'DC ',NULL,NULL,0 UNION ALL
select 'published',1,'DC ',NULL,NULL,0 UNION ALL
select 'subscribed',2,'DC ',NULL,NULL,0 UNION ALL
select 'merge publish',4,'DC ',NULL,NULL,0 UNION ALL
select 'ALL SETTABLE OPTIONS',7,'DC ',NULL,NULL,0 UNION ALL
select 'Distributed',16,'DC ',NULL,NULL,0 UNION ALL
select 'SQLSERVER HOST TYPE',0,'E  ',0,NULL,0 UNION ALL
select 'WINDOWS/NT',1,'E  ',8192,NULL,0 UNION ALL
select 'int high bit',2,'E  ',-2147483648,NULL,0 UNION ALL
select 'int4 high byte',3,'E  ',1,NULL,0 UNION ALL
select 'SERVER AUDIT',8257,'EOB',NULL,NULL,0 UNION ALL
select 'CHECK CONSTRAINT',8259,'EOB',NULL,NULL,0 UNION ALL
select 'DEFAULT',8260,'EOB',NULL,NULL,0 UNION ALL
select 'FOREIGN KEY CONSTRAINT',8262,'EOB',NULL,NULL,0 UNION ALL
select 'STORED PROCEDURE',8272,'EOB',NULL,NULL,0 UNION ALL
select 'RULE',8274,'EOB',NULL,NULL,0 UNION ALL
select 'TABLE',8275,'EOB',NULL,NULL,0 UNION ALL
select 'TRIGGER',8276,'EOB',NULL,NULL,0 UNION ALL
select 'TABLE',8277,'EOB',NULL,NULL,0 UNION ALL
select 'VIEW',8278,'EOB',NULL,NULL,0 UNION ALL
select 'STORED PROCEDURE',8280,'EOB',NULL,NULL,0 UNION ALL
select 'DATABASE AUDIT SPECIFICATION',16708,'EOB',NULL,NULL,0 UNION ALL
select 'SERVER AUDIT SPECIFICATION',16723,'EOB',NULL,NULL,0 UNION ALL
select 'TRIGGER',16724,'EOB',NULL,NULL,0 UNION ALL
select 'DATABASE',16964,'EOB',NULL,NULL,0 UNION ALL
select 'OBJECT',16975,'EOB',NULL,NULL,0 UNION ALL
select 'DATABASE SCOPED CREDENTIAL',17220,'EOB',NULL,NULL,0 UNION ALL
select 'EDGE CONSTRAINT',17221,'EOB',NULL,NULL,0 UNION ALL
select 'FULLTEXT CATALOG',17222,'EOB',NULL,NULL,0 UNION ALL
select 'STORED PROCEDURE',17232,'EOB',NULL,NULL,0 UNION ALL
select 'SCHEMA',17235,'EOB',NULL,NULL,0 UNION ALL
select 'CREDENTIAL',17475,'EOB',NULL,NULL,0 UNION ALL
select 'EXTERNAL DATA SOURCE',17477,'EOB',NULL,NULL,0 UNION ALL
select 'EVENT NOTIFICATION',17491,'EOB',NULL,NULL,0 UNION ALL
select 'DATABASE EVENT SESSION',17732,'EOB',NULL,NULL,0 UNION ALL
select 'EVENT SESSION',17747,'EOB',NULL,NULL,0 UNION ALL
select 'AGGREGATE',17985,'EOB',NULL,NULL,0 UNION ALL
select 'EXTERNAL FILE FORMAT',17989,'EOB',NULL,NULL,0 UNION ALL
select 'FUNCTION',17993,'EOB',NULL,NULL,0 UNION ALL
select 'PARTITION FUNCTION',18000,'EOB',NULL,NULL,0 UNION ALL
select 'STORED PROCEDURE',18002,'EOB',NULL,NULL,0 UNION ALL
select 'FUNCTION',18004,'EOB',NULL,NULL,0 UNION ALL
select 'AVAILABILITY GROUP',18241,'EOB',NULL,NULL,0 UNION ALL
select 'RESOURCE GOVERNOR',18258,'EOB',NULL,NULL,0 UNION ALL
select 'SERVER ROLE',18259,'EOB',NULL,NULL,0 UNION ALL
select 'WINDOWS GROUP',18263,'EOB',NULL,NULL,0 UNION ALL
select 'ASYMMETRIC KEY',19265,'EOB',NULL,NULL,0 UNION ALL
select 'COLUMN ENCRYPTION KEY',19267,'EOB',NULL,NULL,0 UNION ALL
select 'DATABASE ENCRYPTION KEY',19268,'EOB',NULL,NULL,0 UNION ALL
select 'MASTER KEY',19277,'EOB',NULL,NULL,0 UNION ALL
select 'PRIMARY KEY',19280,'EOB',NULL,NULL,0 UNION ALL
select 'SYMMETRIC KEY',19283,'EOB',NULL,NULL,0 UNION ALL
select 'ASYMMETRIC KEY LOGIN',19521,'EOB',NULL,NULL,0 UNION ALL
select 'CERTIFICATE LOGIN',19523,'EOB',NULL,NULL,0 UNION ALL
select 'FULLTEXT STOPLIST',19526,'EOB',NULL,NULL,0 UNION ALL
select 'EXTERNAL GROUP LOGIN',19536,'EOB',NULL,NULL,0 UNION ALL
select 'ROLE',19538,'EOB',NULL,NULL,0 UNION ALL
select 'SQL LOGIN',19539,'EOB',NULL,NULL,0 UNION ALL
select 'WINDOWS LOGIN',19543,'EOB',NULL,NULL,0 UNION ALL
select 'EXTERNAL LOGIN',19544,'EOB',NULL,NULL,0 UNION ALL
select 'COLUMN MASTER KEY',19779,'EOB',NULL,NULL,0 UNION ALL
select 'REMOTE SERVICE BINDING',20034,'EOB',NULL,NULL,0 UNION ALL
select 'EVENT NOTIFICATION',20036,'EOB',NULL,NULL,0 UNION ALL
select 'EVENT NOTIFICATION',20037,'EOB',NULL,NULL,0 UNION ALL
select 'FUNCTION',20038,'EOB',NULL,NULL,0 UNION ALL
select 'EVENT NOTIFICATION',20047,'EOB',NULL,NULL,0 UNION ALL
select 'SYNONYM',20051,'EOB',NULL,NULL,0 UNION ALL
select 'SERVER CONFIG',20291,'EOB',NULL,NULL,0 UNION ALL
select 'SEQUENCE OBJECT',20307,'EOB',NULL,NULL,0 UNION ALL
select 'CRYPTOGR
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_main

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_main]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_main]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":210,"Name":"[repo].[usp_sync_guid]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_sync_guid]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id


/*{"ReportUspStep":[{"Number":300,"Name":"(select [repo].[fs_get_parameter_value]('main enable usp_RepoObjectSource_FirstResultSet', DEFAULT)) = 1","has_logging":0,"is_condition":1,"is_inactive":0,"is_SubProcedure":0}]}*/
IF (select [repo].[fs_get_parameter_value]('main enable usp_RepoObjectSource_FirstResultSet', DEFAULT)) = 1

/*{"ReportUspStep":[{"Number":310,"Parent_Number":300,"Name":"[repo].[usp_RepoObjectSource_FirstResultSet]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
BEGIN
EXEC [repo].[usp_RepoObjectSource_FirstResultSet]
--This can take a very long time
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id

END;

/*{"ReportUspStep":[{"Number":400,"Name":"(select [repo].[fs_get_parameter_value]('main enable usp_RepoObject_update_SysObjectQueryPlan', DEFAULT)) = 1","has_logging":0,"is_condition":1,"is_inactive":0,"is_SubProcedure":0}]}*/
IF (select [repo].[fs_get_parameter_value]('main enable usp_RepoObject_update_SysObjectQueryPlan', DEFAULT)) = 1

/*{"ReportUspStep":[{"Number":410,"Parent_Number":400,"Name":"[repo].[usp_RepoObject_update_SysObjectQueryPlan]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
BEGIN
EXEC [repo].[usp_RepoObject_update_SysObjectQueryPlan]
--This can take a very long time
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id

END;

/*{"ReportUspStep":[{"Number":500,"Name":"(select [repo].[fs_get_parameter_value]('main enable usp_RepoObjectSource_QueryPlan', DEFAULT)) = 1","has_logging":0,"is_condition":1,"is_inactive":0,"is_SubProcedure":0}]}*/
IF (select [repo].[fs_get_parameter_value]('main enable usp_RepoObjectSource_QueryPlan', DEFAULT)) = 1

/*{"ReportUspStep":[{"Number":510,"Parent_Number":500,"Name":"[repo].[usp_RepoObjectSource_QueryPlan]\r\n--This can take a very long time","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
BEGIN
EXEC [repo].[usp_RepoObjectSource_QueryPlan]
--This can take a very long time
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id

END;

/*{"ReportUspStep":[{"Number":610,"Name":"[repo].[usp_update_Referencing_Count]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_update_Referencing_Count]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id


/*{"ReportUspStep":[{"Number":710,"Name":"[repo].[usp_index_inheritance]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_index_inheritance]
--todo:
--should or could be executed several times until no new indexes are inherited
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id


/*{"ReportUspStep":[{"Number":720,"Name":"[repo].[usp_Index_ForeignKey]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_Index_ForeignKey]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssi
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_parameter_insert_update

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @Parameter_name | VARCHAR(100) | no |  |
| @sub_Parameter | NVARCHAR(128) | no |  |
| @Parameter_value | SQL_VARIANT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE PROCEDURE [repo].[usp_parameter_insert_update] (
 @Parameter_name VARCHAR(100)
 , @sub_Parameter NVARCHAR(128) = ''
 , @Parameter_value SQL_VARIANT
 )
AS
--
UPDATE p
SET [Parameter_value] = @Parameter_value
FROM [repo].[Parameter] [p]
WHERE [p].[Parameter_name] = @Parameter_name
 AND [p].[sub_Parameter] = @sub_Parameter

--IF NOT EXISTS
--(
--    SELECT
--           [col]
--    FROM
--         [repo].[Parameter] AS p
--    WHERE  [p].[Parameter_name] = @Parameter_name
--           AND [p].[sub_Parameter] = @sub_Parameter
--)
INSERT INTO [repo].[Parameter] (
 [Parameter_name]
 , [sub_Parameter]
 , [Parameter_value]
 )
SELECT @Parameter_name
 , @sub_Parameter
 , @Parameter_value
WHERE NOT EXISTS (
  SELECT 1
  FROM [repo].[Parameter] AS [p]
  WHERE [p].[Parameter_name] = @Parameter_name
   AND [p].[sub_Parameter] = @sub_Parameter
  )
```

</details>

[Back to top](#dhw_self)

### repo.usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":400,"Name":"truncate persistence target","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_target_object":"[repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]","log_flag_InsertUpdateDelete":"D"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',5,';',400,';',NULL);

TRUNCATE TABLE [repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'truncate persistence target'
SET @source_object = NULL
SET @target_object = '[repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":800,"Name":"insert all","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing]","log_target_object":"[repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]","log_flag_InsertUpdateDelete":"I"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',5,';',800,';',NULL);

INSERT INTO 
 [repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]
 (
  [index_column_id]
, [index_guid]
, [is_descending_key]
, [referenced_RepoObject_guid]
, [referenced_RepoObjectColumn_guid]
, [referencing_RepoObject_guid]
, [referencing_RepoObjectColumn_guid]
, [RowNumberInReferencing]
)
SELECT
  [index_column_id]
, [index_guid]
, [is_descending_key]
, [referenced_RepoObject_guid]
, [referenced_RepoObjectColumn_guid]
, [referencing_RepoObject_guid]
, [referencing_RepoObjectColumn_guid]
, [RowNumberInReferencing]

FROM [repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing] AS S

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'insert all'
SET @source_object = '[repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing]'
SET @target_object = '[repo].[IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
-- Logging END --


--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object


```

</details>

[Back to top](#dhw_self)

### repo.usp_PERSIST_RepoObject_SqlModules_41_from_T

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_PERSIST_RepoObject_SqlModules_41_from_T]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_PERSIST_RepoObject_SqlModules_41_from_T]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":400,"Name":"truncate persistence target","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_target_object":"[repo].[RepoObject_SqlModules_41_from_T]","log_flag_InsertUpdateDelete":"D"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',4,';',400,';',NULL);

TRUNCATE TABLE [repo].[RepoObject_SqlModules_41_from_T]

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'truncate persistence target'
SET @source_object = NULL
SET @target_object = '[repo].[RepoObject_SqlModules_41_from_T]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":800,"Name":"insert all","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObject_SqlModules_41_from]","log_target_object":"[repo].[RepoObject_SqlModules_41_from_T]","log_flag_InsertUpdateDelete":"I"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',4,';',800,';',NULL);

INSERT INTO 
 [repo].[RepoObject_SqlModules_41_from_T]
 (
  [children]
, [class]
, [identifier_alias]
, [identifier_name]
, [is_from]
, [is_group]
, [is_join]
, [is_keyword]
, [is_whitespace]
, [join_type]
, [json_key]
, [Min_RowNumber_From]
, [Min_RowNumber_GroupBy]
, [Min_RowNumber_Where]
, [normalized]
, [normalized_PatIndex_Select]
, [normalized_wo_nolock]
, [patindex_nolock]
, [RepoObject_guid]
, [RowNumber_per_Object]
, [SysObject_fullname]
)
SELECT
  [children]
, [class]
, [identifier_alias]
, [identifier_name]
, [is_from]
, [is_group]
, [is_join]
, [is_keyword]
, [is_whitespace]
, [join_type]
, [json_key]
, [Min_RowNumber_From]
, [Min_RowNumber_GroupBy]
, [Min_RowNumber_Where]
, [normalized]
, [normalized_PatIndex_Select]
, [normalized_wo_nolock]
, [patindex_nolock]
, [RepoObject_guid]
, [RowNumber_per_Object]
, [SysObject_fullname]

FROM [repo].[RepoObject_SqlModules_41_from] AS S

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'insert all'
SET @source_object = '[repo].[RepoObject_SqlModules_41_from]'
SET @target_object = '[repo].[RepoObject_SqlModules_41_from_T]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
-- Logging END --


--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object


```

</details>

[Back to top](#dhw_self)

### repo.usp_PERSIST_RepoObject_SqlModules_61_SelectIdentifier_Union_T

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_PERSIST_RepoObject_SqlModules_61_SelectIdentifier_Union_T]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_PERSIST_RepoObject_SqlModules_61_SelectIdentifier_Union_T]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":400,"Name":"truncate persistence target","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_target_object":"[repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T]","log_flag_InsertUpdateDelete":"D"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',7,';',400,';',NULL);

TRUNCATE TABLE [repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T]

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'truncate persistence target'
SET @source_object = NULL
SET @target_object = '[repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":800,"Name":"insert all","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObject_SqlModules_61_SelectIdentifier_Union]","log_target_object":"[repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T]","log_flag_InsertUpdateDelete":"I"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',7,';',800,';',NULL);

INSERT INTO 
 [repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T]
 (
  [alias_QuoteName]
, [class]
, [normalized]
, [RepoObject_guid]
, [RowNumber_per_Object]
, [source_column_QuoteName]
, [source_table_QuoteName]
, [SysObject_fullname]
)
SELECT
  [alias_QuoteName]
, [class]
, [normalized]
, [RepoObject_guid]
, [RowNumber_per_Object]
, [source_column_QuoteName]
, [source_table_QuoteName]
, [SysObject_fullname]

FROM [repo].[RepoObject_SqlModules_61_SelectIdentifier_Union] AS S

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'insert all'
SET @source_object = '[repo].[RepoObject_SqlModules_61_SelectIdentifier_Union]'
SET @target_object = '[repo].[RepoObject_SqlModules_61_SelectIdentifier_Union_T]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
-- Logging END --


--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object


```

</details>

[Back to top](#dhw_self)

### repo.usp_persistence_insert_update

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @source_RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @source_fullname | NVARCHAR(261) | no |  |
| @persistence_RepoObject_guid | UNIQUEIDENTIFIER | yes |  |
| @persistence_table_name | NVARCHAR(128) | no |  |
| @is_persistence_check_for_empty_source | BIT | no |  |
| @is_persistence_truncate | BIT | no |  |
| @is_persistence_delete_missing | BIT | no |  |
| @is_persistence_delete_changed | BIT | no |  |
| @is_persistence_update_changed | BIT | no |  |
| @is_persistence_insert | BIT | no |  |
| @has_history_columns | BIT | no |  |
| @has_history | BIT | no |  |
| @history_schema_name | NVARCHAR(128) | no |  |
| @history_table_name | NVARCHAR(128) | no |  |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
create or update persistence:

create RepoObject for a new persistence table, based on a given source view or table

- source NULL, persistence NULL
  - error
- source NULL, persistence NOT NULL
  - try to get source
	- SET source = [source_RepoObject_guid]
- source NOT NULL, persistence NULL
  - create new persistence
- source not NULL, persistence not NULL
  - insert or update [repo].[RepoObject_persistence] for (target_RepoObject_guid, [source_RepoObject_guid])
update existing RepoObject which is a persistence table


in any case:
- update attributes in [repo].[RepoObject_persistence]
- refresh columns in [repo].[RepoObjectColumn]
- sql for persistence table => repo.RepoObject_SqlCreateTable
- sql for persistence procedure => todo


test

--1)

exec repo.[usp_persistence_insert_update]
--=> error

--2)
--create new default persistence

EXEC repo.[usp_persistence_insert_update]
     @source_fullname = '[dbo].[view_1]'


--3)
--mark a table which exists as RepoObject as persistence of a source
--or update persistence if the entry already exists in [repo].[RepoObject_persistence]

DECLARE
     @source_RepoObject_guid      UNIQUEIDENTIFIER
   , @persistence_RepoObject_guid UNIQUEIDENTIFIER

SET @source_RepoObject_guid =
(
    SELECT
           [RepoObject_guid]
    FROM
         [repo].[RepoObject]
    WHERE  [SysObject_fullname] = '[dbo].[view_1]'
)

PRINT @source_RepoObject_guid

SET @persistence_RepoObject_guid =
(
    SELECT
           [RepoObject_guid]
    FROM
         [repo].[RepoObject]
    WHERE  [RepoObject_fullname] = '[dbo].[view_1_T]'
)

--SET @persistence_RepoObject_guid =
--(
--    SELECT TOP 1
--           [target_RepoObject_guid]
--    FROM
--         [repo].[RepoObject_persistence]
--    WHERE  [source_RepoObject_guid] = @source_RepoObject_guid
--    ORDER BY
--             [target_RepoObject_guid]
--)

PRINT @persistence_RepoObject_guid

EXEC repo.[usp_persistence_insert_update]
     @source_RepoObject_guid = @source_RepoObject_guid
   , @persistence_RepoObject_guid = @persistence_RepoObject_guid
   , @has_history = 1

--4)

DECLARE	@return_value int,
		@persistence_RepoObject_guid uniqueidentifier

EXEC	@return_value = [repo].[usp_persistence_insert_update]
		@source_fullname = N'[graph].[RepoObjectColumn_S]',
		@persistence_RepoObject_guid = @persistence_RepoObject_guid OUTPUT,
		@persistence_table_name = N'RepoObjectColumn',
		@is_persistence_check_for_empty_source = 1,
		@is_persistence_truncate = 0,
		@is_persistence_delete_missing = 1,
		@is_persistence_delete_changed = 0,
		@is_persistence_update_changed = 1,
		@is_persistence_insert = 1

SELECT	@persistence_RepoObject_guid as N'@persistence_RepoObject_guid'

SELECT	'Return Value' = @return_value


*/
--todo: überlegen, ob @source_RepoObject_guid NULL sein darf, wenn @persistence_RepoObject_guid NOT NULL
CREATE PROCEDURE [repo].[usp_persistence_insert_update] @source_RepoObject_guid UNIQUEIDENTIFIER = NULL --
 , @source_fullname NVARCHAR(261) = NULL --it is possible to use @source_RepoObject_guid OR @source_fullname; use: "[schema].[object_name]"
 , @persistence_RepoObject_guid UNIQUEIDENTIFIER = NULL OUTPUT --if this parameter is not null then an existing RepoObject is used to modify, if it is null then a RepoObject will be created, don't use brackts: "object_name_T"
 , @persistence_table_name NVARCHAR(128) = NULL --default: @source_table_name + @persistence_name_suffix; default schema is @source_schema_name
 , @is_persistence_check_for_empty_source BIT = NULL
 , @is_persistence_truncate BIT = NULL
 , @is_persistence_delete_missing BIT = NULL
 , @is_persistence_delete_changed BIT = NULL
 , @is_persistence_update_changed BIT = NULL
 , @is_persistence_insert BIT = NULL
 , @has_history_columns BIT = NULL
 , @has_history BIT = NULL
 , @history_schema_name NVARCHAR(128) = NULL
 , @history_table_name NVARCHAR(128) = NULL
 --todo:
 --think about an additional parameter
 --@is_remove_target_column_not_in_source
 --don't remove: persistence columns, calculated columns
 --but there could be dependencies from these columns
 --these should be checked
 --maybe som kind of maintenance procedure would be better then to integrate this here
 --
 --by default the source schema is used and the source name with prefix '_T' for table
 --todo: use general parameters to define this
 -- some optional parameters, used for logging
 , @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT
 , @parameter_01 = @source_RepoObject_guid
 , @parameter_02 = @source_fullname
 , @parameter_03 = @persistence_RepoObject_guid
 , @parameter_04 = @persistence_table_name
 , @parameter_05 = @is_persistence_check_for_empty_source
 , @parameter_06 = @is_persistence_truncate
 , @parameter_07 = @is_persistence_delete_missing
 , @parameter_08 = @is_persistence_delete_changed
 , @parameter_09 = @is_persistence_update_changed
 , @parameter_10 = @is_persistence_insert
 , @parameter_11 = @has_history_columns
 , @parameter_12 = @has_history
 , @parameter_13 = @history_schema_name
 , @parameter_14 = @history_table_name

--
----START
--
DECLARE @info_01_message NVARCHAR(1000)
--this table is used for OUTPUT to get the new assigned [RepoObject_guid] when inserting new values
DECLARE @table TABLE ([guid] UNIQUEIDENTIFIER)
DECLARE @source_schema_name NVARCHAR(128)
 , @source_table_name NVARCHAR(128)
 , @persistence_schema_name NVARCHAR(128)
 , @persistence_name_suffix NVARCHAR(10)

--   , @new_RepoObject_guid     UNIQUEIDENTIFIER
SET @persistence_name_suffix = (
  SELECT [Parameter_value__result_nvarchar]
  FROM [repo].[Parameter]
  WHERE [Parameter_name] = 'persistence_name_suffix'
  )

----the following should not happen
--SET @persistence_name_suffix = (
--  SELECT ISNULL(@persistence_name_suffix, '_T')
--  )
IF @persistence_name_suffix IS NULL
BEGIN
 THROW 51001
  , '@persistence_name_suffix is null, check repo.Parameter, EXEC [repo].[usp_init_parameter]'
  , 1;
END

IF @source_
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_RepoObject_Inheritance

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE PROCEDURE [repo].[usp_RepoObject_Inheritance]
 ----keep the code between logging parameters and "START" unchanged!
 ---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
 , @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
 , @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
 @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT

----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant
--
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
DECLARE inheritance_cursor CURSOR READ_ONLY
FOR
SELECT [resulting_InheritanceDefinition]
FROM repo.RepoObject_InheritanceType_resulting_InheritanceDefinition
GROUP BY [resulting_InheritanceDefinition]
HAVING (NOT (resulting_InheritanceDefinition IS NULL))

DECLARE @resulting_InheritanceDefinition NVARCHAR(4000)
 , @resulting_InheritanceDefinition_ForSql NVARCHAR(4000)
DECLARE @stmt NVARCHAR(MAX)

OPEN inheritance_cursor

FETCH NEXT
FROM inheritance_cursor
INTO @resulting_InheritanceDefinition

WHILE (@@fetch_status <> - 1)
BEGIN
 IF (@@fetch_status <> - 2)
 BEGIN
  PRINT @resulting_InheritanceDefinition

  --replace "'" by "''" to be used in a string
  SET @resulting_InheritanceDefinition_ForSql = REPLACE(@resulting_InheritanceDefinition, '''', '''''')

  --PRINT @resulting_InheritanceDefinition_ForSql
  TRUNCATE TABLE repo.[RepoObject_Inheritance_temp]

  /*
INSERT INTO [repo].[RepoObject_Inheritance_temp] (
 [RepoObject_guid]
 , [property_name]
 , [property_value]
 , [property_value_new]
 , [InheritanceType]
 , [Inheritance_StringAggSeparatorSql]
 , [is_force_inherit_empty_source]
 , [is_StringAggAllSources]
 , [resulting_InheritanceDefinition]
 , [RowNumberSource]
 , [referenced_RepoObject_guid]
 , [referenced_RepoObject_fullname]
 , [referenced_RepoObject_name]
 , [referencing_RepoObject_fullname]
 , [referencing_RepoObject_name]
 )
SELECT
 --
 [T1].[RepoObject_guid]
 , [T1].[property_name]
 , [T1].[property_value]
 , [property_value_new] = COALESCE([referencing].[Repo_definition], [repo].[fs_get_RepoObjectProperty_nvarchar]([referenced].[RepoObject_guid], 'MS_Description'))
 , [T1].[InheritanceType]
 , [T1].[Inheritance_StringAggSeparatorSql]
 , [T1].[is_force_inherit_empty_source]
 , [T1].[is_StringAggAllSources]
 , [T1].[resulting_InheritanceDefinition]
 , [RowNumberSource] = ROW_NUMBER() OVER (
  PARTITION BY [T1].[RepoObject_guid] ORDER BY [referenced].[RepoObject_fullname]
   , [referenced].[RepoObject_name]
  )
 , [T2].[referenced_RepoObject_guid]
 , [referenced_RepoObject_fullname] = [referenced].[RepoObject_fullname]
 , [referenced_RepoObject_name] = [referenced].[RepoObject_name]
 , [referencing_RepoObject_fullname] = [referencing].[RepoObject_fullname]
 , [referencing_RepoObject_name] = [referencing].[RepoObject_name]
FROM [repo].[RepoObject_InheritanceType_resulting_InheritanceDefinition] AS T1
INNER JOIN [repo].[RepoObject_reference_union] AS T2
 ON T2.[referencing_RepoObject_guid] = T1.[RepoObject_guid]
INNER JOIN [repo].[RepoObject_gross] AS referencing
 ON referencing.[RepoObject_guid] = T1.[RepoObject_guid]
INNER JOIN [repo].[RepoObject_gross] AS referenced
 ON referenced.[RepoObject_guid] = T2.[referenced_RepoObject_guid]
WHERE [T1].[resulting_InheritanceDefinition] = 'COALESCE(referencing.[Repo_definition], repo.fs_get_RepoObjectProperty_nvarchar(referenced.[RepoObject_guid], ''MS_Description''))'

*/
  SET @stmt = '
INSERT INTO [repo].[RepoObject_Inheritance_temp] (
 [RepoObject_guid]
 , [property_name]
 , [property_value]
 , [property_value_new]
 , [InheritanceType]
 , [Inheritance_StringAggSeparatorSql]
 , [is_force_inherit_empty_source]
 , [is_StringAggAllSources]
 , [resulting_InheritanceDefinition]
 , [RowNumberSource]
 , [referenced_RepoObject_guid]
 , [referenced_RepoObject_fullname]
 , [referenced_RepoObject_name]
 , [referencing_RepoObject_fullname]
 , [referencing_RepoObject_name]
 )
SELECT
 --
 [T1].[RepoObject_guid]
 , [T1].[property_name]
 , [T1].[property_value]
 , [property_value_new] = ' + @resulting_InheritanceDefinition + 
   ' 
 , [T1].[InheritanceType]
 , [T1].[Inheritance_StringAggSeparatorSql]
 , [T1].[is_force_inherit_empty_source]
 , [T1].[is_StringAggAllSources]
 , [T1].[resulting_InheritanceDefinition]
 , [RowNumberSource] = ROW_NUMBER() OVER (
  PARTITION BY [T1].[RepoObject_guid] ORDER BY [referenced].[RepoObject_fullname]
  )
 , [T2].[referenced_RepoObject_guid]
 , [referenced_RepoObject_fullname] = [referenced].[RepoObject_fullname]
 , [referenced_RepoObject_name] = [referenced].[RepoObject_name]
 , [referencing_RepoObject_fullname] = [referencing].[RepoObject_fullname]
 , [referencing_RepoObject_name] = [referencing].[RepoObject_name]
FROM [repo].[RepoObject_InheritanceType_resulting_InheritanceDefin
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_RepoObject_update_SysObjectQueryPlan

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
references on column level
target: repo.RepoObjectSource_from_query_plan
source: query plan analysis of the execution of a query like
`Vselect top (1) * into #foo from (SELECT * FROM sss.aaa)`

First update query plan and write them into repo.RepoObject
then analyse the query plans and update results into 

EXEC [repo_sys].[usp_RepoObject_update_SysObjectQueryPlan]
EXEC [repo].[usp_RepoObjectSource_QueryPlan]

some query plans can't be extracted, some can be extracted but not analyzed
in this case mark the RepoObject in repo.RepoObject
SET [has_execution_plan_issue] = 1

*/
CREATE PROCEDURE [repo].[usp_RepoObject_update_SysObjectQueryPlan]
 -- some optional parameters, used for logging
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'

--SET @source_object = NULL
--SET @target_object = NULL
EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT;

--
----START
--
DECLARE @RepoObject_guid UNIQUEIDENTIFIER
 , @SysObject_query_sql NVARCHAR(4000)
 , @SysObject_query_plan XML
 , @SysObject_query_executed_dt DATETIME
 , @select_into_query AS VARCHAR(4000)

DECLARE view_cursor CURSOR
FOR
--
SELECT [ro].[RepoObject_guid]
 , [ro].[SysObject_query_sql]
 , [ro].[SysObject_query_plan]
 , [ro].[SysObject_query_executed_dt]
--, ro.[SysObject_modify_date]
FROM repo.RepoObject_gross AS ro
WHERE
 --   --only views and tables (for calculated columns)
 ----we don't need tables, references for calculated columns we have in [repo].[RepoObjectColumn_reference__sql_expression_dependencies]
 --   [ro].[SysObject_type] IN
 --                            (
 --                            'V' , 'U'
 --                            )
 --only views
 [ro].[SysObject_type] = 'V'
 AND [ro].[SysObject_query_sql] <> ''
 AND (
  [ro].[SysObject_query_plan] IS NULL
  OR [ro].[SysObject_query_executed_dt] IS NULL
  --query plan could be outdated
  OR [ro].[SysObject_query_executed_dt] < [ro].[SysObject_modify_date]
  )
 --we can't catch some issues with sys.dm_exec_query_stats
 --thats why as an workaround we exclude them
 AND ISNULL([ro].[has_execution_plan_issue], 0) = 0
ORDER BY [ro].[RepoObject_guid]

--FOR UPDATE OF [SysObject_query_plan]
-- , [SysObject_query_executed_dt]
OPEN view_cursor

FETCH NEXT
FROM view_cursor
INTO @RepoObject_guid
 , @SysObject_query_sql
 , @SysObject_query_plan
 , @SysObject_query_executed_dt

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  SET @select_into_query = 'select top (1) * into #foo from (' + @SysObject_query_sql + ') as src'

  --information about the current RepoObject in case of error
  --some query plans can't be extracted, some can be extracted but not analyzed
  --in this case mark the RepoObject in repo.RepoObject
  --SET [has_execution_plan_issue] = 1
  PRINT CONCAT (
    @RepoObject_guid
    , ' '
    , @SysObject_query_sql
    )
  PRINT 'if you get issues and TRY CATCH doesn''t solve them, then execute this:'
  PRINT CONCAT (
    'UPDATE [repo].[RepoObject] SET [has_execution_plan_issue] = 1 WHERE [RepoObject_guid] = '''
    , @RepoObject_guid
    , ''''
    )

  DECLARE @xml_plan AS XML = NULL
   , @xml_generation_tries AS TINYINT = 10

  WHILE @xml_plan IS NULL
   AND @xml_generation_tries > 0 -- There is no guaranty that plan will be cached.
  BEGIN
   PRINT @select_into_query;

   EXECUTE (@select_into_query);

   --most time TRY CATCH doesn't work
   --sometimes any select from sys.dm_exec_query_stats results in an error:
   --Msg 681, Level 16, State 3, Line 1
   --Attempting to set a non-NULL-able column's value to NULL.
   --sometimes we get other errors
   BEGIN TRY
    SELECT @xml_plan = [pln].[query_plan]
    FROM sys.dm_exec_query_stats AS qry
    CROSS APPLY sys.dm_exec_sql_text(qry.sql_handle) AS txt
    CROSS APPLY sys.dm_exec_query_plan(qry.plan_handle) AS pln
    WHERE [txt].TEXT = @select_into_query;
   END TRY

   BEGIN CATCH
    PRINT 'Can''t get query_plan'

    UPDATE ro
    SET [has_execution_plan_issue] = 1
    FROM [repo].[RepoObject] AS [ro]
    WHERE [ro].[RepoObject_guid] = @RepoObject_guid
   END CATCH

   SET @xml_generation_tries = @xml_generation_tries - 1
  END

  --PRINT 'IF @xml_plan IS NULL';
  --IF @xml_plan IS NULL
  --    BEGIN
  --        --RAISERROR(N'Can''t extract XML query plan from cache.' , 15 , 0);
  --        RAISERROR(N'Can''t extract XML query plan from cache.' , 10 , 0);
  --        RETURN;
  --END;
  MERGE INTO [repo].[RepoObject_QueryPlan] T
  USING (
   SELECT @RepoObject_guid
    , @xml_plan
   ) AS S(RepoObject_guid, SysObject_query_plan)
   ON S.RepoObject_guid = T.RepoObject_guid
  WHEN MATCHED
   THEN
    UPDATE
    SET [SysObject_query_plan] = [S].[SysObject_query_plan]
     , [SysObject_query_executed_dt] = GETDATE()
  WHEN NOT MATCHED
   THEN
    INSERT (
     [RepoObject_guid]
     , [SysObject_query_plan]
     , [SysObject_query_executed_dt]
     )
    VALUES (
     S.RepoObject_guid
     , S.SysObject_query_plan
     , GETDATE()
     );

  --UPDATE repo.RepoObject
  --SET [SysObject_query_plan] = @xml_plan
  -- , [SysObject_query_executed_dt] = GETDATE()
  --WHERE [RepoObject_guid] = @RepoObject_guid
  SET @rows = @@rowcount;
  SET @step_id = @step_id + 1
  SET @step_name = 'UPDATE SET [SysObject_query_plan] = @xml_plan, [SysObject_query_executed_dt] = GETDATE()'
  SET @source_object = '[repo].[RepoObject]'
  SET @target_object = '[repo].[RepoObject]'

  EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
   , @ssis_execution_id = @ssis_execution_id
   , @sub_execution_id = @sub_execution_id
   , @parent_execution_log_id = @parent_execution_log_id
   , @current_execution_guid = @current_execution_guid
   , @proc_id = @proc_id
   , @proc_schema_name = @proc_schema_name
   , @proc_name = @proc_name
   , @event_info = @event_info
   , @step_id = @step_id
   , @step_name = @step_name
   , @source_object = @source_object
   , @target_object = @target_object
   , @inserted = NULL
   , @updated = @rows
   , @deleted = NULL
   , @info_01 = @RepoObject_guid
   , @info_02 =
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_RepoObjectColumn_Inheritance

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE PROCEDURE [repo].[usp_RepoObjectColumn_Inheritance]
 ----keep the code between logging parameters and "START" unchanged!
 ---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
 , @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
 , @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
 @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT

----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant
--
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
DECLARE inheritance_cursor CURSOR READ_ONLY
FOR
SELECT [resulting_InheritanceDefinition]
FROM repo.RepoObjectColumn_InheritanceType_resulting_InheritanceDefinition
GROUP BY [resulting_InheritanceDefinition]
HAVING (NOT (resulting_InheritanceDefinition IS NULL))

DECLARE @resulting_InheritanceDefinition NVARCHAR(4000)
 , @resulting_InheritanceDefinition_ForSql NVARCHAR(4000)
DECLARE @stmt NVARCHAR(MAX)

OPEN inheritance_cursor

FETCH NEXT
FROM inheritance_cursor
INTO @resulting_InheritanceDefinition

WHILE (@@fetch_status <> - 1)
BEGIN
 IF (@@fetch_status <> - 2)
 BEGIN
  PRINT @resulting_InheritanceDefinition

  --replace "'" by "''" to be used in a string
  SET @resulting_InheritanceDefinition_ForSql = REPLACE(@resulting_InheritanceDefinition, '''', '''''')

  --PRINT @resulting_InheritanceDefinition_ForSql
  TRUNCATE TABLE repo.[RepoObjectColumn_Inheritance_temp]

  /*
INSERT INTO [repo].[RepoObjectColumn_Inheritance_temp] (
 [RepoObjectColumn_guid]
 , [property_name]
 , [property_value]
 , [property_value_new]
 , [InheritanceType]
 , [Inheritance_StringAggSeparatorSql]
 , [is_force_inherit_empty_source]
 , [is_StringAggAllSources]
 , [resulting_InheritanceDefinition]
 , [RowNumberSource]
 , [referenced_RepoObjectColumn_guid]
 , [referenced_RepoObject_fullname]
 , [referenced_RepoObjectColumn_name]
 , [referencing_RepoObject_fullname]
 , [referencing_RepoObjectColumn_name]
 )
SELECT
 --
 [T1].[RepoObjectColumn_guid]
 , [T1].[property_name]
 , [T1].[property_value]
 , [property_value_new] = COALESCE([referencing].[Repo_definition], [repo].[fs_get_RepoObjectColumnProperty_nvarchar]([referenced].[RepoObjectColumn_guid], 'MS_Description'))
 , [T1].[InheritanceType]
 , [T1].[Inheritance_StringAggSeparatorSql]
 , [T1].[is_force_inherit_empty_source]
 , [T1].[is_StringAggAllSources]
 , [T1].[resulting_InheritanceDefinition]
 , [RowNumberSource] = ROW_NUMBER() OVER (
  PARTITION BY [T1].[RepoObjectColumn_guid] ORDER BY [referenced].[RepoObject_fullname]
   , [referenced].[RepoObjectColumn_name]
  )
 , [T2].[referenced_RepoObjectColumn_guid]
 , [referenced_RepoObject_fullname] = [referenced].[RepoObject_fullname]
 , [referenced_RepoObjectColumn_name] = [referenced].[RepoObjectColumn_name]
 , [referencing_RepoObject_fullname] = [referencing].[RepoObject_fullname]
 , [referencing_RepoObjectColumn_name] = [referencing].[RepoObjectColumn_name]
FROM [repo].[RepoObjectColumn_InheritanceType_resulting_InheritanceDefinition] AS T1
INNER JOIN [repo].[RepoObjectColumn_reference_union] AS T2
 ON T2.[referencing_RepoObjectColumn_guid] = T1.[RepoObjectColumn_guid]
INNER JOIN [repo].[RepoObjectColumn_gross] AS referencing
 ON referencing.[RepoObjectColumn_guid] = T1.[RepoObjectColumn_guid]
INNER JOIN [repo].[RepoObjectColumn_gross] AS referenced
 ON referenced.[RepoObjectColumn_guid] = T2.[referenced_RepoObjectColumn_guid]
WHERE [T1].[resulting_InheritanceDefinition] = 'COALESCE(referencing.[Repo_definition], repo.fs_get_RepoObjectColumnProperty_nvarchar(referenced.[RepoObjectColumn_guid], ''MS_Description''))'

*/
  SET @stmt = '
INSERT INTO [repo].[RepoObjectColumn_Inheritance_temp] (
 [RepoObjectColumn_guid]
 , [property_name]
 , [property_value]
 , [property_value_new]
 , [InheritanceType]
 , [Inheritance_StringAggSeparatorSql]
 , [is_force_inherit_empty_source]
 , [is_StringAggAllSources]
 , [resulting_InheritanceDefinition]
 , [RowNumberSource]
 , [referenced_RepoObjectColumn_guid]
 , [referenced_RepoObject_fullname]
 , [referenced_RepoObjectColumn_name]
 , [referencing_RepoObject_fullname]
 , [referencing_RepoObjectColumn_name]
 )
SELECT
 --
 [T1].[RepoObjectColumn_guid]
 , [T1].[property_name]
 , [T1].[property_value]
 , [property_value_new] = ' + @resulting_InheritanceDefinition + 
   ' 
 , [T1].[InheritanceType]
 , [T1].[Inheritance_StringAggSeparatorSql]
 , [T1].[is_force_inherit_empty_source]
 , [T1].[is_StringAggAllSources]
 , [T1].[resulting_InheritanceDefinition]
 , [RowNumberSource] = ROW_NUMBER() OVER (
  PARTITION BY [T1].[RepoObjectColumn_guid] ORDER BY [referenced].[RepoObject_fullname]
   , [referenced].[RepoObjectColumn_name]
  )
 , [T2].[referenced_RepoObjectColumn_guid]
 , [referenced_RepoObject_fullname] = [referenced].[RepoObject_fullname]
 , [r
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_RepoObjectColumn_update_RepoObjectColumn_column_id

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
exec repo.usp_RepoObjectColumn__update_RepoObjectColumn_column_id

exec repo.usp_RepoObjectColumn__update_RepoObjectColumn_column_id
@RepoObject_guid = '7E756329-D857-EB11-84D8-A81E8446D5B0'

*/
--if @RepoObject_guid = NULL then all RepoObject will be updated
--@OrderBy is defined by a parameter: 'RepoObjectColumn_column_id_OrderBy'
CREATE PROCEDURE [repo].[usp_RepoObjectColumn_update_RepoObjectColumn_column_id]
 --
 @RepoObject_guid UNIQUEIDENTIFIER = NULL
 ,
 -- some optional parameters, used for logging
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
 --, @debug                   BIT              = 0
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT;

--
----START
--
DECLARE @OrderBy NVARCHAR(1000)
DECLARE @sqlCommand NVARCHAR(4000)

--set @RepoObject_guid = '7E756329-D857-EB11-84D8-A81E8446D5B0'
SET @OrderBy = CAST((
   SELECT [repo].[fs_get_parameter_value]('RepoObjectColumn_column_id_OrderBy', DEFAULT)
   ) AS NVARCHAR(1000))
--'
--[roc].[Repo_is_identity]
--, [roc].[Repo_is_computed]
--, ISNULL([ic].[index_column_id] , 99999) --ensure PK index is sorted before other columns
--, [roc].[Repo_generated_always_type]
--, [roc].[RepoObjectColumn_name]
--'
--	SET @sqlCommand = '
--SELECT
--     [roc].[RepoObjectColumn_guid]
--     ,  [RepoObjectColumn_column_id_setpoint] = ROW_NUMBER() OVER(PARTITION BY [roc].[RepoObject_guid]
--       ORDER BY
--       --
--' + @OrderBy + '
--       --
--       )
--     , [roc].[RepoObjectColumn_column_id]
--     , [roc].[RepoObject_guid]
--     , [roc].[Repo_is_identity]
--     , [roc].[Repo_is_computed]
--     , [ic].[index_column_id]
--     , [ic].[is_index_primary_key]
--     , [roc].[Repo_generated_always_type]
--     , [roc].[SysObjectColumn_column_id]
--     , [roc].[RepoObjectColumn_name]
--FROM
--     [repo].[RepoObjectColumn] AS roc
--     LEFT JOIN
--     [repo].[IndexColumn_union] AS ic
--     ON ic.RepoObjectColumn_guid = roc.RepoObjectColumn_guid
--        AND ic.[is_index_primary_key] = 1
--WHERE
----not [is_query_plan_expression]
--[is_query_plan_expression] IS NULL
----we need the datatype
--AND NOT [Repo_user_type_fullname] IS NULL
--'
--	IF NOT @RepoObject_guid IS NULL
--		SET @sqlCommand = @sqlCommand + '
--AND [roc].[RepoObject_guid] = @RepoObject_guid
--'
SET @sqlCommand = CONCAT (
  '
UPDATE roc
SET [RepoObjectColumn_column_id] = rocg.[RepoObjectColumn_column_id_setpoint]
FROM repo.RepoObjectColumn roc
LEFT JOIN (
 SELECT [roc].[RepoObjectColumn_guid]
  , [RepoObjectColumn_column_id_setpoint] = ROW_NUMBER() OVER (
   PARTITION BY [roc].[RepoObject_guid] ORDER BY
       --
'
  , @OrderBy
  , '
       --
   )
  , [roc].[RepoObjectColumn_column_id]
  , [roc].[RepoObject_guid]
  , [roc].[Repo_is_identity]
  , [roc].[Repo_is_computed]
  , [ic].[index_column_id]
  , [ic].[is_index_primary_key]
  , [roc].[Repo_generated_always_type]
  , [roc].[SysObjectColumn_column_id]
  , [roc].[RepoObjectColumn_name]
 FROM [repo].[RepoObjectColumn] AS roc
 LEFT JOIN [repo].[IndexColumn_union] AS ic
  ON ic.RepoObjectColumn_guid = roc.RepoObjectColumn_guid
   AND ic.[is_index_primary_key] = 1
 WHERE
  --not [is_query_plan_expression]
  [is_query_plan_expression] IS NULL
  --we need the datatype
  AND NOT [roc].[Repo_user_type_fullname] IS NULL
'
  , CASE 
   WHEN NOT @RepoObject_guid IS NULL
    THEN ' AND [roc].[RepoObject_guid] = @RepoObject_guid
'
   END
  , ' ) rocg
 ON rocg.[RepoObjectColumn_guid] = roc.RepoObjectColumn_guid
WHERE rocg.[RepoObjectColumn_column_id_setpoint] <> ISNULL(roc.RepoObjectColumn_column_id, 0)
'
  )

PRINT @sqlCommand

--EXECUTE sp_executesql @sqlCommand
EXECUTE sp_executesql @sqlCommand
 , N'@RepoObject_guid uniqueidentifier'
 , @RepoObject_guid = @RepoObject_guid

--
--END
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1;
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
```

</details>

[Back to top](#dhw_self)

### repo.usp_RepoObjectSource_FirstResultSet

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
references on column level
target: repo.RepoObjectSource
source: sys.dm_exec_describe_first_result_set


sometimes required
truncate table [repo].[RepoObjectSource__dm_exec_describe_first_result_set]
*/
CREATE PROCEDURE [repo].[usp_RepoObjectSource_FirstResultSet]
 -- some optional parameters, used for logging
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'

--SET @source_object = NULL
--SET @target_object = NULL
EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT;

--
----START
--
----Make sure that the metadata is up to date
--EXEC repo.usp_sync_guid
--     @execution_instance_guid = @execution_instance_guid
--   , @ssis_execution_id = @ssis_execution_id
--   , @sub_execution_id = @sub_execution_id
--   , @parent_execution_log_id = @current_execution_log_id
--delete FROM repo.RepoObjectSource where query_sql was updated
DELETE
FROM repo.RepoObjectSource_FirstResultSet
FROM [repo].[RepoObjectSource_FirstResultSet]
LEFT OUTER JOIN [repo].[RepoObject] AS [ro]
 ON [repo].[RepoObjectSource_FirstResultSet].[RepoObject_guid] = [ro].[RepoObject_guid]
WHERE [repo].[RepoObjectSource_FirstResultSet].[created_dt] < [ro].[SysObject_modify_date]
 OR [ro].[SysObject_modify_date] IS NULL
 --wrong inserts from prev execution
 OR [target_column_name] IS NULL

SET @rows = @@rowcount;
SET @step_id = @step_id + 1
SET @step_name = 'DELETE modified after last created:dt'
SET @source_object = NULL
SET @target_object = '[repo].[RepoObjectSource_FirstResultSet]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = @rows
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

INSERT INTO repo.RepoObjectSource_FirstResultSet (
 [RepoObject_guid]
 , [column_ordinal]
 , [target_column_name]
 , [system_type_id]
 , [system_type_name]
 , [source_server_name]
 , [source_database_name]
 , [source_schema_name]
 , [source_table_name]
 , [source_column_name]
 , [is_hidden]
 , [created_dt]
 )
SELECT [ro_filtered].[RepoObject_guid]
 , [ref].[column_ordinal]
 , [ref].[name]
 , [ref].[system_type_id]
 , [ref].[system_type_name]
 , [ref].[source_server]
 , [ref].[source_database]
 , [ref].[source_schema]
 , [ref].[source_table]
 , [ref].[source_column]
 , [ref].[is_hidden]
 , GETDATE() AS [created_dt]
FROM (
 SELECT [ro].[RepoObject_guid]
  , [ro].[SysObject_query_sql]
 FROM repo.RepoObject_gross AS ro
 LEFT JOIN (
  SELECT [RepoObject_guid]
   , MIN([created_dt]) AS [created_dt_min]
  FROM repo.RepoObjectSource_FirstResultSet AS ros
  GROUP BY [RepoObject_guid]
  ) AS ros
  ON ro.RepoObject_guid = ros.RepoObject_guid
 WHERE NOT [ro].[SysObject_query_sql] IS NULL
  --only tables and views
  AND [ro].[SysObject_type] IN (
   'U'
   , 'V'
   )
  AND (
   [ros].[created_dt_min] IS NULL
   OR [ro].[SysObject_modify_date] IS NULL
   OR [ros].[created_dt_min] < [ro].[SysObject_modify_date]
   )
 ) AS ro_filtered
CROSS APPLY
 --schema sys should be OK here because SysObject_query_sql has a full qualified query including database_name 
 sys.dm_exec_describe_first_result_set(ro_filtered.SysObject_query_sql, NULL, 1) AS ref
WHERE
 --skip invalid entries
 NOT [ref].[name] IS NULL

SET @rows = @@rowcount;
SET @step_id = @step_id + 1
SET @step_name = 'CROSS APPLY sys.dm_exec_describe_first_result_set(ro_filtered.SysObject_query_sql , NULL , 1)'
SET @source_object = '[repo].[RepoObject]'
SET @target_object = '[repo].[RepoObjectSource_FirstResultSet]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

--
--END
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1;
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
```

</details>

[Back to top](#dhw_self)

### repo.usp_RepoObjectSource_QueryPlan

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
references on column level
target: repo.RepoObjectSource__QueryPlan
source: query plan analysis of the execution of a query like
`Vselect top (1) * into #foo from (SELECT * FROM sss.aaa)`

First update query plan and write them into repo.RepoObject_QueryPlan
then analyse the query plans and update results into 

EXEC [repo].[usp_RepoObject__update_SysObject_query_plan]
EXEC [repo].[usp_RepoObjectSource_from_query_plan__update]

some query plans can't be extracted, some can be extracted but not analyzed
in this case mark the RepoObject in repo.RepoObject
SET [has_execution_plan_issue] = 1

*/
CREATE PROCEDURE [repo].[usp_RepoObjectSource_QueryPlan]
 -- some optional parameters, used for logging
 @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, but other any other guid
 , @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix
 , @sub_execution_id INT = NULL
 , @parent_execution_log_id BIGINT = NULL
AS
DECLARE @current_execution_log_id BIGINT
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID()
 , @source_object NVARCHAR(261) = NULL
 , @target_object NVARCHAR(261) = NULL
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid)
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = NULL
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL
 , @execution_log_id = @current_execution_log_id OUTPUT

--
----START
--
DECLARE @message NVARCHAR(1000)

-- delete outdated entries, which need to be analyzed again
DELETE
FROM repo.RepoObjectSource_QueryPlan
FROM [repo].[RepoObject_gross] AS [ro]
INNER JOIN [repo].[RepoObjectSource_QueryPlan]
 ON [ro].[RepoObject_guid] = [repo].[RepoObjectSource_QueryPlan].[RepoObject_guid]
  AND [ro].[SysObject_query_executed_dt] > [repo].[RepoObjectSource_QueryPlan].[SysObject_query_executed_dt]

SET @rows = @@rowcount;
SET @step_id = @step_id + 1
SET @step_name = 'DELETE outdated entries, which need to be analyzed again'
SET @source_object = '[repo].[RepoObject]'
SET @target_object = '[repo].[RepoObjectSource__query_plan]'

EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = NULL
 , @updated = NULL
 , @deleted = @rows
 , @info_01 = NULL
 , @info_02 = NULL
 , @info_03 = NULL
 , @info_04 = NULL
 , @info_05 = NULL
 , @info_06 = NULL
 , @info_07 = NULL
 , @info_08 = NULL
 , @info_09 = NULL

DECLARE object_cursor CURSOR READ_ONLY
FOR
--
SELECT [ro].[RepoObject_guid]
 , [ro].[SysObject_fullname]
--, [ro].[SysObject_query_executed_dt]
--, [ro].SysObject_query_plan
FROM repo.RepoObject_gross AS ro
WHERE NOT [ro].[SysObject_query_plan] IS NULL
 --only views
 AND [ro].[SysObject_type] = 'V'
 --exclude objects with has_execution_plan_issue
 AND ISNULL([ro].[has_execution_plan_issue], 0) = 0
 AND NOT EXISTS (
  SELECT [RepoObject_guid]
  FROM [repo].[RepoObjectSource_QueryPlan] AS [TFilter]
  WHERE [ro].[RepoObject_guid] = [TFilter].[RepoObject_guid]
   AND [ro].[SysObject_query_executed_dt] = [TFilter].[SysObject_query_executed_dt]
  )
ORDER BY [ro].[RepoObject_guid]

DECLARE @RepoObject_guid UNIQUEIDENTIFIER
 , @SysObject_fullname NVARCHAR(500)

--, @SysObject_query_executed_dt datetime
--, @SysObject_query_plan xml
OPEN object_cursor

FETCH NEXT
FROM object_cursor
INTO @RepoObject_guid
 , @SysObject_fullname

--, @SysObject_query_executed_dt, @SysObject_query_plan
WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  --information about the current RepoObject in case of error
  --some query plans can't be extracted, some can be extracted but not analyzed
  --in this case mark the RepoObject in repo.RepoObject
  --SET [has_execution_plan_issue] = 1
  PRINT CONCAT (
    @RepoObject_guid
    , ' '
    , @SysObject_fullname
    )

  BEGIN TRY
   INSERT INTO repo.RepoObjectSource_QueryPlan (
    [RepoObject_guid]
    , [SysObject_query_executed_dt]
    , [target_column_name]
    , [source_server_name]
    , [source_database_name]
    , [source_schema_name]
    , [source_table_name]
    , [source_column_name]
    , [const_value]
    , [target_column_info]
    , [source_column_info]
    , [const_info]
    )
   SELECT [ro].[RepoObject_guid]
    , [ro].[SysObject_query_executed_dt]
    , [sc].[target_column_name]
    , [sc].[source_server_name]
    , [sc].[source_database_name]
    , [sc].[source_schema_name]
    , [sc].[source_table_name]
    , [sc].[source_column_name]
    , [sc].[const_value]
    , [sc].[target_column_info]
    , [sc].[source_column_info]
    , [sc].[const_info]
   FROM repo.RepoObject_gross AS ro
   CROSS APPLY repo.ftv_query_plan_extract_source(SysObject_query_plan) AS sc
   WHERE [ro].[RepoObject_guid] = @RepoObject_guid
   OPTION (MAXRECURSION 100)

   --WHERE  NOT [ro].[SysObject_query_plan] IS NULL
   --       AND NOT EXISTS
   --(
   --    SELECT
   --           [RepoObject_guid]
   --    FROM
   --         [repo].[RepoObjectSource_from_query_plan] AS [TFilter]
   --    WHERE  [ro].[RepoObject_guid] = [TFilter].[RepoObject_guid]
   --           AND [ro].[SysObject_query_executed_dt] = [TFilter].[SysObject_query_executed_dt]
   --) OPTION(
   --         MAXRECURSION 20)
   SET @rows = @@rowcount;
   SET @message = NULL
  END TRY

  BEGIN CATCH
   SET @rows = 0;
   SET @message = 'CATCH - can not analyze query plan'

   UPDATE ro
   SET [has_execution_plan_issue] = 1
   FROM [repo].[RepoObject] AS [ro]
   WHERE [ro].[RepoObject_guid] = @RepoObject_guid
  END CATCH

  SET @step_id = @step_id + 1
  SET @step_name = 'CROSS APPLY repo.ftv_query_plan_extract_source(SysObject_query_plan)'
  SET @source_object = '[repo].[RepoObject]'
  SET @target_object = '[repo].[RepoObjectSource__query_plan]'

  EXEC repo.usp_ExecutionLog_insert @execution_instance_guid = @execution_instance_guid
   , @ssis_execution_id = @ssis_execution_id
   , @sub_execution_id = @sub_execution_id
   , @parent_execution_log_id = @parent_execution_log_id
   , @current_execution_guid = @current_execution_guid
   , @proc_id = @proc_id
   , @proc_schema_name = @proc_schema_name
   , @proc_name = @proc_name
   , @event_info = @event_info
   , @step_id = @step_id

/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_sync_ExtendedProperties_Repo2Sys_Delete

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_sync_ExtendedProperties_Repo2Sys_Delete]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_sync_ExtendedProperties_Repo2Sys_Delete]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":100,"Name":"DECLARE","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":0}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',14,';',100,';',NULL);

DECLARE
 --
 @property_name NVARCHAR(128)
 , @property_value SQL_VARIANT
 , @schema_name NVARCHAR(128)
 , @level0type VARCHAR(128)
 , @level0name NVARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name NVARCHAR(128)
 , @level2type VARCHAR(128)
 , @level2name NVARCHAR(128)

/*{"ReportUspStep":[{"Number":410,"Name":"Level1-Properties - DROP","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[ExtendedProperty_Repo2Sys_level1]","log_target_object":"[sys].[sp_dropextendedproperty]","log_flag_InsertUpdateDelete":"d"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',14,';',410,';',NULL);

DECLARE property_cursor CURSOR READ_ONLY
FOR
--
--level 1 extended properties
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM [repo_sys].[ExtendedProperties_ParameterForAddUpdateDrop] AS [T]
WHERE NOT [T].[property_name] = 'RepoObject_guid'
 AND NOT [T].[property_name] = 'RepoObjectColumn_guid'
 AND [T].[level2type] IS NULL
 AND [T].[level2name] IS NULL
 AND NOT EXISTS (
  SELECT 1
  FROM [repo].[ExtendedProperty_Repo2Sys_level1] AS [S]
  WHERE [T].[property_name] = [S].[property_name]
   AND [T].[level0type] = [S].[level0type]
   AND [T].[level0name] = [S].[level0name]
   AND [T].[level1type] = [S].[level1type]
   AND [T].[level1name] = [S].[level1name]
   AND [S].[level2type] IS NULL
   AND [S].[level2name] IS NULL
  )

--DECLARE @property_name NVARCHAR(128)
-- , @property_value SQL_VARIANT
-- , @schema_name NVARCHAR(128)
-- , @level0type VARCHAR(128)
-- , @level0name NVARCHAR(128)
-- , @level1type VARCHAR(128)
-- , @level1name NVARCHAR(128)
-- , @level2type VARCHAR(128)
-- , @level2name NVARCHAR(128)

SET @rows = 0;

OPEN property_cursor;

FETCH NEXT
FROM property_cursor
INTO @property_name
 , @property_value
 , @level0type
 , @level0name
 , @level1type
 , @level1name
 , @level2type
 , @level2name

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  EXEC sys.sp_dropextendedproperty @name = @property_name
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name
   , @level2type = @level2type
   , @level2name = @level2name

  SET @rows = @rows + 1;
 END;

 FETCH NEXT
 FROM property_cursor
 INTO @property_name
  , @property_value
  , @level0type
  , @level0name
  , @level1type
  , @level1name
  , @level2type
  , @level2name
END

CLOSE property_cursor;

DEALLOCATE property_cursor

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'Level1-Properties - DROP'
SET @source_object = '[repo].[ExtendedProperty_Repo2Sys_level1]'
SET @target_object = '[sys].[sp_dropextendedproperty]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @deleted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":420,"Name":"Level2-Properties - DROP","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[ExtendedProperty_Repo2Sys_level2_Union]","log_target_object":"[sys].[sp_dropextendedproperty]","log_flag_InsertUpdateDelete":"d"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',14,';',420,';',NULL);

DECLARE property_cursor CURSOR READ_ONLY
FOR
--
--level 2 extended properties
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM [rep
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_sync_ExtendedProperties_Repo2Sys_InsertUpdate

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_sync_ExtendedProperties_Repo2Sys_InsertUpdate]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_sync_ExtendedProperties_Repo2Sys_InsertUpdate]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":100,"Name":"DECLARE","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":0}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',13,';',100,';',NULL);

DECLARE
 --
 @property_name NVARCHAR(128)
 , @property_value SQL_VARIANT
 , @schema_name NVARCHAR(128)
 , @level0type VARCHAR(128)
 , @level0name NVARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name NVARCHAR(128)
 , @level2type VARCHAR(128)
 , @level2name NVARCHAR(128)

/*{"ReportUspStep":[{"Number":310,"Name":"Level1-Properties - INSERT + UPDATE","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[ExtendedProperty_Repo2Sys_level1]","log_target_object":"[repo_sys].[usp_AddOrUpdateExtendedProperty]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',13,';',310,';',NULL);

DECLARE property_cursor CURSOR READ_ONLY
FOR
--
--level 1 extended properties
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM [repo].[ExtendedProperty_Repo2Sys_level1] AS S
--do not change extended properties with exact match
WHERE NOT EXISTS (
  SELECT 1
  FROM [repo_sys].[ExtendedProperties_ParameterForAddUpdateDrop] AS [T]
  WHERE [T].[property_name] = [S].[property_name]
   AND [T].[property_value] = [S].[property_value]
   AND [T].[level0type] = [S].[level0type]
   AND [T].[level0name] = [S].[level0name]
   AND [T].[level1type] = [S].[level1type]
   AND [T].[level1name] = [S].[level1name]
   AND [T].[level2type] IS NULL
   AND [T].[level2name] IS NULL
  )

--DECLARE @property_name NVARCHAR(128)
-- , @property_value SQL_VARIANT
-- , @schema_name NVARCHAR(128)
-- , @level0type VARCHAR(128)
-- , @level0name NVARCHAR(128)
-- , @level1type VARCHAR(128)
-- , @level1name NVARCHAR(128)
-- , @level2type VARCHAR(128)
-- , @level2name NVARCHAR(128)

SET @rows = 0;

OPEN property_cursor;

FETCH NEXT
FROM property_cursor
INTO @property_name
 , @property_value
 , @level0type
 , @level0name
 , @level1type
 , @level1name
 , @level2type
 , @level2name

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  EXEC repo_sys.[usp_AddOrUpdateExtendedProperty] @name = @property_name
   , @value = @property_value
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name
   , @level2type = @level2type
   , @level2name = @level2name

  SET @rows = @rows + 1;
 END;

 FETCH NEXT
 FROM property_cursor
 INTO @property_name
  , @property_value
  , @level0type
  , @level0name
  , @level1type
  , @level1name
  , @level2type
  , @level2name
END

CLOSE property_cursor;

DEALLOCATE property_cursor

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'Level1-Properties - INSERT + UPDATE'
SET @source_object = '[repo].[ExtendedProperty_Repo2Sys_level1]'
SET @target_object = '[repo_sys].[usp_AddOrUpdateExtendedProperty]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":320,"Name":"Level2-Properties - INSERT + UPDATE","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[ExtendedProperty_Repo2Sys_level2_Union]","log_target_object":"[repo_sys].[usp_AddOrUpdateExtendedProperty]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',13,';',320,';',NULL);

DECLARE property_cursor CURSOR READ_ONLY
FOR
--
--level 2 extended properties
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1t
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_sync_ExtendedProperties_Sys2Repo_InsertUpdate

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_sync_ExtendedProperties_Sys2Repo_InsertUpdate]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_sync_ExtendedProperties_Sys2Repo_InsertUpdate]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":100,"Name":"DECLARE","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":0}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',12,';',100,';',NULL);

DECLARE
 --
 @property_name NVARCHAR(128)
 , @property_value SQL_VARIANT
 , @schema_name NVARCHAR(128)
 , @level0type VARCHAR(128)
 , @level0name NVARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name NVARCHAR(128)
 , @level2type VARCHAR(128)
 , @level2name NVARCHAR(128)

/*{"ReportUspStep":[{"Number":310,"Name":"repo.RepoObjectProperty - INSERT","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObjectProperty_sys_repo]","log_target_object":"[repo].[RepoObjectProperty]","log_flag_InsertUpdateDelete":"i"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',12,';',310,';',NULL);

INSERT INTO repo.RepoObjectProperty (
 [RepoObject_guid]
 , [property_name]
 , [property_value]
 )
SELECT DISTINCT [RepoObject_guid]
 , [property_name]
 , [property_value]
FROM repo.RepoObjectProperty_sys_repo AS T1
WHERE [RepoObjectProperty_id] IS NULL

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'repo.RepoObjectProperty - INSERT'
SET @source_object = '[repo].[RepoObjectProperty_sys_repo]'
SET @target_object = '[repo].[RepoObjectProperty]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @inserted = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":320,"Name":"repo.RepoObjectProperty - UPDATE","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObjectProperty_sys_repo]","log_target_object":"[repo].[RepoObjectProperty]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',12,';',320,';',NULL);

--update table [repo].[RepoObjectProperty] via view
UPDATE repo.RepoObjectProperty_sys_repo
SET [RepoObjectProperty_property_value] = [property_value]
WHERE NOT [RepoObjectProperty_id] IS NULL
 AND [RepoObjectProperty_property_value] <> [property_value]

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'repo.RepoObjectProperty - UPDATE'
SET @source_object = '[repo].[RepoObjectProperty_sys_repo]'
SET @target_object = '[repo].[RepoObjectProperty]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":410,"Name":"repo.RepoObjectColumnProperty - INSERT","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObjectColumnProperty_sys_repo]","log_target_object":"[repo].[RepoObjectColumnProperty]","log_flag_InsertUpdateDelete":"i"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',12,';',410,';',NULL);

INSERT INTO repo.RepoObjectColumnProperty (
 [RepoObjectColumn_guid]
 , [property_name]
 , [property_value]
 )
SELECT DISTINCT [RepoObjectColumn_guid]
 , [property_name]
 , [property_value]
FROM repo.RepoObjectColumnProperty_sys_repo AS T1
WHERE [RepoObjectColumnProperty_id] IS NULL

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'repo.RepoObjectColumnProperty - INSERT'
SET @source_object = '[repo].[RepoObjectColumnProper
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_sync_guid

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_sync_guid]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_sync_guid]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":210,"Name":"[repo].[usp_sync_guid_RepoObject]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_sync_guid_RepoObject]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id


/*{"ReportUspStep":[{"Number":310,"Name":"[repo].[usp_sync_guid_RepoObjectColumn]","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":1}]}*/
EXEC [repo].[usp_sync_guid_RepoObjectColumn]
--add your own parameters
--logging parameters
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @current_execution_log_id



--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object


```

</details>

[Back to top](#dhw_self)

### repo.usp_sync_guid_RepoObject

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_sync_guid_RepoObject]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_sync_guid_RepoObject]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":210,"Name":"SET several RepoObject_SysObject_...","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo_sys].[SysObject]","log_target_object":"[repo].[RepoObject]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',8,';',210,';',NULL);

/*
use objects with [RepoObject_guid] stored in extended properties
	
- SysObject could be renamed after previous sync
	- => update SysObject properties in RepoObject
	- don't change RepoObject names
*/
UPDATE repo.SysObject_RepoObject_via_guid
SET [RepoObject_SysObject_id] = [SysObject_id]
 , [RepoObject_SysObject_schema_name] = [SysObject_schema_name]
 , [RepoObject_SysObject_name] = [SysObject_name]
 , [RepoObject_SysObject_type] = [SysObject_type]
 , [RepoObject_SysObject_modify_date] = [modify_date]
 , [RepoObject_SysObject_parent_object_id] = [parent_object_id]
 , [RepoObject_is_SysObject_missing] = NULL
WHERE NOT [RepoObject_guid] IS NULL
 AND (
  [RepoObject_SysObject_id] <> [SysObject_id]
  OR [RepoObject_SysObject_id] IS NULL
  OR [RepoObject_SysObject_schema_name] <> [SysObject_schema_name]
  OR [RepoObject_SysObject_name] <> [SysObject_name]
  OR [RepoObject_SysObject_type] <> [SysObject_type]
  OR [RepoObject_SysObject_modify_date] <> [modify_date]
  OR [RepoObject_SysObject_modify_date] IS NULL
  OR [RepoObject_SysObject_parent_object_id] <> [parent_object_id]
  --
  )

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'SET several RepoObject_SysObject_...'
SET @source_object = '[repo_sys].[SysObject]'
SET @target_object = '[repo].[RepoObject]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":310,"Name":"SET [SysObject_name] = [repo].[RepoObject].[RepoObject_guid]","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo_sys].[SysObject]","log_target_object":"[repo].[RepoObject]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',8,';',310,';',NULL);

/*
in case of possible conflict when inserting missing guid because auf [UK_RepoObject__SysNames] conflicting entries get 
[SysObject_name] = [repo].[RepoObject].[RepoObject_guid]
this will allow INSERT in the next step without issues
*/
UPDATE repo.RepoObject
SET [SysObject_name] = [repo].[RepoObject].[RepoObject_guid]
FROM [repo].[RepoObject]
INNER JOIN (
 SELECT [SysObject_id]
  , [SysObject_RepoObject_guid]
  , [SysObject_schema_name]
  , [SysObject_name]
 FROM [repo].[SysObject_RepoObject_via_guid]
 WHERE
  --SysObject, which exists in database and have a RepoObject_guid assigned in extended properties 
  NOT [SysObject_RepoObject_guid] IS NULL
  --but the have not yet a RepoObject_guid assigned in [repo].[RepoObject] 
  AND [RepoObject_guid] IS NULL
 ) AS [missing_guid]
 ON [repo].[RepoObject].[SysObject_schema_name] = [missing_guid].[SysObject_schema_name]
  AND [repo].[RepoObject].[SysObject_name] = [missing_guid].[SysObject_name]

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'SET [SysObject_name] = [repo].[RepoObject].[RepoObject_guid]'
SET @source_object = '[repo_sys].[SysObject]'
SET @target_object = '[repo].[RepoObject]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_i
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_sync_guid_RepoObjectColumn

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_sync_guid_RepoObjectColumn]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_sync_guid_RepoObjectColumn]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":100,"Name":"intro","has_logging":0,"is_condition":0,"is_inactive":0,"is_SubProcedure":0}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',6,';',100,';',NULL);

/*
ATTENTION!
Column guid syncronization requires existing RepoObject guid synchronization (all RepoObject in the database need a RepoObject_guid)
because RepoObject_guid is used to join
	
=>
[repo_sys].[usp_sync_guid_RepoObject]
must be executed _before_ to ensure all RepoObject guid are synchronized
*/

/*{"ReportUspStep":[{"Number":210,"Name":"UPDATE repo_sys.SysColumn_RepoObjectColumn_via_RepoObjectColumn_guid","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo_sys].[SysColumn]","log_target_object":"[repo].[RepoObjectColumn]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',6,';',210,';',NULL);

/*
use objects with [RepoObjectColumn_guid] stored in extended properties
	
- SysObjectColumn could be renamed after previous sync
	- => update SysObjectColum properties in RepoObjectColumn
	- don't change RepoObjectColumn names
*/
UPDATE repo.SysColumn_RepoObjectColumn_via_guid
SET [SysObjectColumn_name] = [SysObject_column_name]
 , [SysObjectColumn_column_id] = [SysObject_column_id]
 , [RepoObject_guid] = [SysObject_RepoObject_guid]
WHERE NOT [RepoObjectColumn_guid] IS NULL
 AND (
  --
  [SysObjectColumn_name] <> [SysObject_column_name]
  OR [SysObjectColumn_name] IS NULL
  OR [SysObjectColumn_column_id] <> [SysObject_column_id]
  OR [SysObjectColumn_column_id] IS NULL
  OR [RepoObject_guid] <> [SysObject_RepoObject_guid]
  ----
  );

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'UPDATE repo_sys.SysColumn_RepoObjectColumn_via_RepoObjectColumn_guid'
SET @source_object = '[repo_sys].[SysColumn]'
SET @target_object = '[repo].[RepoObjectColumn]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":310,"Name":"SET [SysObjectColumn_name] = [RepoObjectColumn_guid] (to avoid conflict in the next INSERT step)","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo].[RepoObjectColumn]","log_target_object":"[repo].[RepoObjectColumn]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',6,';',310,';',NULL);

/*
in case of possible conflict when inserting missing guid because auf [UK_RepoObjectColumn__SysNames] conflicting entries get 
[SysObjectColumn_name] = [repo].[RepoObjectColumn].[RepoObjectColumn_guid]
this will allow INSERT in the next step without issues
*/
UPDATE repo.RepoObjectColumn
SET [SysObjectColumn_name] = [repo].[RepoObjectColumn].[RepoObjectColumn_guid]
FROM [repo].[RepoObjectColumn]
INNER JOIN (
 SELECT [SysObject_id]
  , [SysObject_RepoObject_guid]
  , [SysObject_schema_name]
  , [SysObject_name]
  , [SysObject_column_name]
  , [SysObjectColumn_column_id]
  , [SysObject_RepoObjectColumn_guid]
  , [RepoObject_guid]
  , [RepoObjectColumn_guid]
 FROM [repo].[SysColumn_RepoObjectColumn_via_guid]
 WHERE
  --SysObjectColumns, which exists in database and have a RepoObjectColumn_guid assigned in extended properties 
  NOT [SysObject_RepoObjectColumn_guid] IS NULL
  --but the have not yet a RepoObjectColumn_guid assigned in [repo].[RepoObjectColumns] 
  AND [RepoObjectColumn_guid] IS NULL
 ) AS [missing_guid]
 ON [repo].[RepoObjectColumn].[RepoObject_guid] = [missing_guid].[RepoObject_guid]
  AND [repo].[RepoObjectColumn].[SysObjectColumn_name] = [missing_guid].[SysObject_column_name]

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'SET [SysObjectColumn_name] = 
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo.usp_update_Referencing_Count

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @ssis_execution_id | BIGINT | no |  |
| @sub_execution_id | INT | no |  |
| @parent_execution_log_id | BIGINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE   PROCEDURE [repo].[usp_update_Referencing_Count]
----keep the code between logging parameters and "START" unchanged!
---- parameters, used for logging; you don't need to care about them, but you can use them, wenn calling from SSIS or in your workflow to log the context of the procedure call
  @execution_instance_guid UNIQUEIDENTIFIER = NULL --SSIS system variable ExecutionInstanceGUID could be used, any other unique guid is also fine. If NULL, then NEWID() is used to create one
, @ssis_execution_id BIGINT = NULL --only SSIS system variable ServerExecutionID should be used, or any other consistent number system, do not mix different number systems
, @sub_execution_id INT = NULL --in case you log some sub_executions, for example in SSIS loops or sub packages
, @parent_execution_log_id BIGINT = NULL --in case a sup procedure is called, the @current_execution_log_id of the parent procedure should be propagated here. It allowes call stack analyzing
AS
DECLARE
 --
   @current_execution_log_id BIGINT --this variable should be filled only once per procedure call, it contains the first logging call for the step 'start'.
 , @current_execution_guid UNIQUEIDENTIFIER = NEWID() --a unique guid for any procedure call. It should be propagated to sub procedures using "@parent_execution_log_id = @current_execution_log_id"
 , @source_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @target_object NVARCHAR(261) = NULL --use it like '[schema].[object]', this allows data flow vizualizatiuon (include square brackets)
 , @proc_id INT = @@procid
 , @proc_schema_name NVARCHAR(128) = OBJECT_SCHEMA_NAME(@@procid) --schema ande name of the current procedure should be automatically logged
 , @proc_name NVARCHAR(128) = OBJECT_NAME(@@procid)               --schema ande name of the current procedure should be automatically logged
 , @event_info NVARCHAR(MAX)
 , @step_id INT = 0
 , @step_name NVARCHAR(1000) = NULL
 , @rows INT

--[event_info] get's only the information about the "outer" calling process
--wenn the procedure calls sub procedures, the [event_info] will not change
SET @event_info = (
  SELECT [event_info]
  FROM sys.dm_exec_input_buffer(@@spid, CURRENT_REQUEST_ID())
  )

IF @execution_instance_guid IS NULL
 SET @execution_instance_guid = NEWID();
--
--SET @rows = @@ROWCOUNT;
SET @step_id = @step_id + 1
SET @step_name = 'start'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
 --these parameters should be the same for all logging execution
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 --the following parameters are individual for each call
 , @step_id = @step_id --@step_id should be incremented before each call
 , @step_name = @step_name --assign individual step names for each call
 --only the "start" step should return the log id into @current_execution_log_id
 --all other calls should not overwrite @current_execution_log_id
 , @execution_log_id = @current_execution_log_id OUTPUT
----you can log the content of your own parameters, do this only in the start-step
----data type is sql_variant

--
PRINT '[repo].[usp_update_Referencing_Count]'
--keep the code between logging parameters and "START" unchanged!
--
----START
--
----- start here with your own code
--
/*{"ReportUspStep":[{"Number":210,"Name":"SET [RepoObject_Referencing_Count] = [rorc].[Referencing_Count]","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo_sys].[RepoObjectReferencing]","log_target_object":"[repo].[RepoObject]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',19,';',210,';',NULL);

UPDATE repo.RepoObject
SET [RepoObject_Referencing_Count] = [rorc].[Referencing_Count]
FROM [repo].[RepoObject]
LEFT OUTER JOIN (
 SELECT [RepoObject_guid]
  , COUNT(*) AS [Referencing_Count]
 FROM [repo_sys].[RepoObjectReferencing] AS [ror]
 GROUP BY [RepoObject_guid]
 ) AS [rorc]
 ON [repo].[RepoObject].[RepoObject_guid] = [rorc].[RepoObject_guid]
WHERE ISNULL([repo].[RepoObject].[RepoObject_Referencing_Count], 0) <> ISNULL([rorc].[Referencing_Count], 0)

-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'SET [RepoObject_Referencing_Count] = [rorc].[Referencing_Count]'
SET @source_object = '[repo_sys].[RepoObjectReferencing]'
SET @target_object = '[repo].[RepoObject]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --

/*{"ReportUspStep":[{"Number":310,"Name":"SET [Referencing_Count] = [rorc].[Referencing_Count]","has_logging":1,"is_condition":0,"is_inactive":0,"is_SubProcedure":0,"log_source_object":"[repo_sys].[RepoObjectReferenced]","log_target_object":"[repo].[RepoObjectColumn]","log_flag_InsertUpdateDelete":"u"}]}*/
PRINT CONCAT('usp_id;Number;Parent_Number: ',19,';',310,';',NULL);

UPDATE repo.RepoObjectColumn
SET [Referencing_Count] = [rorc].[Referencing_Count]
FROM [repo].[RepoObjectColumn]
LEFT OUTER JOIN [repo].[RepoObject] [ro]
 ON [repo].[RepoObjectColumn].[RepoObject_guid] = [ro].[RepoObject_guid]
LEFT OUTER JOIN (
 SELECT [referenced_schema_name]
  , [referenced_entity_name]
  , [referenced_minor_name]
  , COUNT(DISTINCT [RepoObject_guid]) AS [Referencing_Count]
 FROM [repo_sys].[RepoObjectReferenced] AS [ror]
 WHERE [referenced_database_name] = [repo].[fs_dwh_database_name]()
  OR [referenced_database_name] IS NULL
 GROUP BY [referenced_schema_name]
  , [referenced_entity_name]
  , [referenced_minor_name]
 ) AS [rorc]
 ON [repo].[RepoObjectColumn].[SysObjectColumn_name] = [rorc].[referenced_minor_name]
  AND [ro].[SysObject_name] = [rorc].[referenced_entity_name]
  AND [ro].[SysObject_schema_name] = [referenced_schema_name]
WHERE ISNULL([repo].[RepoObjectColumn].[Referencing_Count], 0) <> ISNULL([rorc].[Referencing_Count], 0)


-- Logging START --
SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'SET [Referencing_Count] = [rorc].[Referencing_Count]'
SET @source_object = '[repo_sys].[RepoObjectReferenced]'
SET @target_object = '[repo].[RepoObjectColumn]'

EXEC repo.usp_ExecutionLog_insert 
 @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @ssis_execution_id
 , @sub_execution_id = @sub_execution_id
 , @parent_execution_log_id = @parent_execution_log_id
 , @current_execution_guid = @current_execution_guid
 , @proc_id = @proc_id
 , @proc_schema_name = @proc_schema_name
 , @proc_name = @proc_name
 , @event_info = @event_info
 , @step_id = @step_id
 , @step_name = @step_name
 , @source_object = @source_object
 , @target_object = @target_object
 , @updated = @rows
-- Logging END --


--
--finish your own code here
--keep the code between "END" and the end of the procedure unchanged!
--
--END
--
--SET @rows = @@ROWCOUNT
SET @step_id = @step_id + 1
SET @step_name = 'end'
SET @source_object = NULL
SET @target_object = NULL

EXEC repo.usp_ExecutionLog_insert
   @execution_instance_guid = @execution_instance_guid
 , @ssis_execution_id = @s
/************************************************************************************************/
/* sp_doc: Max 8000 characters reached. Set @LimitStoredProcLength = 0 to show full definition. */
/************************************************************************************************/
```

</details>

[Back to top](#dhw_self)

### repo_sys.usp_AddOrUpdateExtendedProperty

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @name | SYSNAME(128) | no |  |
| @value | SQL_VARIANT | no |  |
| @level0type | VARCHAR(128) | no |  |
| @level0name | SYSNAME(128) | no |  |
| @level1type | VARCHAR(128) | no |  |
| @level1name | SYSNAME(128) | no |  |
| @level2type | VARCHAR(128) | no |  |
| @level2name | SYSNAME(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
EXEC repo_sys.sp_AddOrUpdateExtendedProperty   
    @name = N'repo_guid'  
    ,@value = N'Employee ID'  
    ,@level0type = N'Schema', @level0name = dbo  
    ,@level1type = N'Table',  @level1name = T1  
    ,@level2type = N'Column', @level2name = id;


sysnonym will not work because sp_updateextendedproperty and sp_addextendedproperty will always use the current datebase context

https://dba.stackexchange.com/questions/136135/how-can-a-database-parameter-be-used-on-sp-addextendedproperty

DECLARE @DbName SYSNAME = 'AdventureWorks2012';
DECLARE @module_name_var NVARCHAR(500) = QUOTENAME(@DbName) + 
                                              '.sys.sp_addextendedproperty';

EXEC @module_name_var
  @name = N'Caption',
  @value = 'AdventureWorks2012 Sample OLTP Database'; 

https://docs.microsoft.com/de-de/sql/t-sql/language-elements/execute-transact-sql?view=sql-server-ver15

module_name

Is the fully qualified or nonfully qualified name of the stored procedure or scalar-valued user-defined function to call. 
Module names must comply with the rules for identifiers. 
The names of extended stored procedures are always case-sensitive, regardless of the collation of the server.

A module that has been created in another database can be executed if the user running the module owns the module or has the appropriate permission to execute it in that database. 
A module can be executed on another server running SQL Server if the user running the module has the appropriate permission to use that server (remote access) and to execute the module in that database. 
If a server name is specified but no database name is specified, the SQL Server Database Engine looks for the module in the default database of the user.

@module_name_var

Is the name of a locally defined variable that represents a module name.

This can be a variable that holds the name of a natively compiled, scalar user-defined function.


immer noch Fehler:

RepoObject_guid;92D613F2-5752-EB11-84D5-A81E8446D5B0;Schema;Warehouse;TABLE;ColdRoomTemperatures;;;
Msg 12320, Level 16, State 80, Procedure WideWorldImporters-test.sys.sp_addextendedproperty, Line 37 [Batch Start Line 2]
Operations that require a change to the schema version, for example renaming, are not supported with memory optimized tables.

=> todo
*/
CREATE PROCEDURE [repo_sys].[usp_AddOrUpdateExtendedProperty] @name SYSNAME
 , @value SQL_VARIANT = NULL
 , @level0type VARCHAR(128) = NULL
 , @level0name SYSNAME = NULL
 , @level1type VARCHAR(128) = NULL
 , @level1name SYSNAME = NULL
 , @level2type VARCHAR(128) = NULL
 , @level2name SYSNAME = NULL
AS
DECLARE @DbName SYSNAME = [repo].[fs_dwh_database_name]()
DECLARE @module_name_var_update NVARCHAR(500) = QUOTENAME(@DbName) + '.sys.sp_updateextendedproperty'
 , @module_name_var_add NVARCHAR(500) = QUOTENAME(@DbName) + '.sys.sp_addextendedproperty'

----DEBUG
--PRINT CONCAT(@name , ';' , CAST(@value AS NVARCHAR(4000)) , ';' , @level0type , ';' , @level0name , ';' , @level1type , ';' , @level1name , ';' , @level2type , ';' , @level2name , ';')
----DEBUG
--
BEGIN TRY
 --EXEC [sys].sp_updateextendedproperty
 EXEC @module_name_var_update @name = @name
  , @value = @value
  , @level0type = @level0type
  , @level0name = @level0name
  , @level1type = @level1type
  , @level1name = @level1name
  , @level2type = @level2type
  , @level2name = @level2name
END TRY

BEGIN CATCH
 BEGIN TRY
  --EXEC [sys].sp_addextendedproperty
  EXEC @module_name_var_add @name = @name
   , @value = @value
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name
   , @level2type = @level2type
   , @level2name = @level2name
 END TRY

 BEGIN CATCH
  PRINT 'Can''t insert extended property:'
  PRINT CONCAT (
    @name
    , ';'
    , CAST(@value AS NVARCHAR(4000))
    , ';'
    , @level0type
    , ';'
    , @level0name
    , ';'
    , @level1type
    , ';'
    , @level1name
    , ';'
    , @level2type
    , ';'
    , @level2name
    , ';'
    )
 END CATCH
END CATCH
```

</details>

[Back to top](#dhw_self)

### repo_sys.usp_dropextendedproperty_level_1

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @name | VARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
-- Create Procedure usp_dropextendedproperty_level_1
/*
this procedure will drop extended property with property_name = @name used in all "level 1 objects"
level 1 objects are:
AGGREGATE, DEFAULT, FUNCTION, LOGICAL FILE NAME, PROCEDURE, QUEUE, RULE, SYNONYM, TABLE, TABLE_TYPE, TYPE, VIEW, XML SCHEMA COLLECTION

for example:
if there are tables, views and ohter level 1 objects containing properties like 'repo_guid' then the following execution will drop them all

EXEC repo_sys.usp_dropextendedproperty_level_1
     @name = 'RepoObject_guid'

*/
CREATE PROCEDURE [repo_sys].[usp_dropextendedproperty_level_1] @name VARCHAR(128)
AS
DECLARE @DbName SYSNAME = [repo].[fs_dwh_database_name]()

PRINT @DbName

DECLARE @module_name_var_drop NVARCHAR(500) = QUOTENAME(@DbName) + '.sys.sp_dropextendedproperty'

DECLARE delete_cursor CURSOR READ_ONLY
FOR
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
FROM repo_sys.[ExtendedProperties_ParameterForAddUpdateDrop]
WHERE [property_name] = @name
 AND NOT [level1type] IS NULL
 AND NOT [level1name] IS NULL
 AND [level2type] IS NULL
 AND [level2name] IS NULL

DECLARE @property_name VARCHAR(128)
 , @property_value SQL_VARIANT
 , @level0type VARCHAR(128)
 , @level0name VARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name VARCHAR(128)

OPEN delete_cursor

FETCH NEXT
FROM delete_cursor
INTO @property_name
 , @property_value
 , @level0type
 , @level0name
 , @level1type
 , @level1name

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  --EXEC sp_dropextendedproperty
  EXEC @module_name_var_drop @name = @property_name
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name

  PRINT CONCAT (
    @module_name_var_drop
    , ';'
    , @name
    , ';'
    , @level0type
    , ';'
    , @level0name
    , ';'
    , @level1type
    , ';'
    , @level1name
    )
 END

 FETCH NEXT
 FROM delete_cursor
 INTO @property_name
  , @property_value
  , @level0type
  , @level0name
  , @level1type
  , @level1name
END

CLOSE delete_cursor

DEALLOCATE delete_cursor
```

</details>

[Back to top](#dhw_self)

### repo_sys.usp_dropextendedproperty_level_2

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @name | VARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
EXEC [repo_sys].usp_dropextendedproperty_level_2
     @name = 'RepoObject_guid'

EXEC [repo_sys].usp_dropextendedproperty_level_2
     @name = 'RepoObjectColumn_guid'
*/
CREATE PROCEDURE repo_sys.[usp_dropextendedproperty_level_2] @name VARCHAR(128)
AS
DECLARE @DbName SYSNAME = [repo].[fs_dwh_database_name]()

PRINT @DbName

DECLARE @module_name_var_drop NVARCHAR(500) = QUOTENAME(@DbName) + '.sys.sp_dropextendedproperty'

PRINT @module_name_var_drop

DECLARE delete_cursor CURSOR READ_ONLY
FOR
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM sys_self.[ExtendedProperties_ParameterForAddUpdateDrop]
WHERE [property_name] = @name
 AND NOT [level1type] IS NULL
 AND NOT [level1name] IS NULL
 AND NOT [level2type] IS NULL
 AND NOT [level2name] IS NULL

DECLARE @property_name VARCHAR(128)
 , @property_value SQL_VARIANT
 , @level0type VARCHAR(128)
 , @level0name VARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name VARCHAR(128)
 , @level2type VARCHAR(128)
 , @level2name VARCHAR(128)

OPEN delete_cursor

FETCH NEXT
FROM delete_cursor
INTO @property_name
 , @property_value
 , @level0type
 , @level0name
 , @level1type
 , @level1name
 , @level2type
 , @level2name

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  PRINT CONCAT (
    @module_name_var_drop
    , ';'
    , @name
    , ';'
    , @level0type
    , ';'
    , @level0name
    , ';'
    , @level1type
    , ';'
    , @level1name
    , ';'
    , @level2type
    , ';'
    , @level2name
    )

  --EXEC sp_dropextendedproperty
  EXEC @module_name_var_drop @name = @property_name
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name
   , @level2type = @level2type
   , @level2name = @level2name
 END

 FETCH NEXT
 FROM delete_cursor
 INTO @property_name
  , @property_value
  , @level0type
  , @level0name
  , @level1type
  , @level1name
  , @level2type
  , @level2name
END

CLOSE delete_cursor

DEALLOCATE delete_cursor
```

</details>

[Back to top](#dhw_self)

### sys_self.usp_dropextendedproperty_level_1

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @name | VARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
EXEC [sys_self].usp_dropextendedproperty_level_1
     @name = 'RepoObject_guid'
*/
CREATE PROCEDURE [sys_self].[usp_dropextendedproperty_level_1] @name VARCHAR(128)
AS
DECLARE @DbName SYSNAME = DB_NAME()

PRINT @DbName

DECLARE @module_name_var_drop NVARCHAR(500) = QUOTENAME(@DbName) + '.sys.sp_dropextendedproperty'

PRINT @module_name_var_drop

DECLARE delete_cursor CURSOR READ_ONLY
FOR
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
FROM sys_self.[ExtendedProperties_ParameterForAddUpdateDrop]
WHERE [property_name] = @name
 AND NOT [level1type] IS NULL
 AND NOT [level1name] IS NULL
 AND [level2type] IS NULL
 AND [level2name] IS NULL

DECLARE @property_name VARCHAR(128)
 , @property_value SQL_VARIANT
 , @level0type VARCHAR(128)
 , @level0name VARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name VARCHAR(128)

OPEN delete_cursor

FETCH NEXT
FROM delete_cursor
INTO @property_name
 , @property_value
 , @level0type
 , @level0name
 , @level1type
 , @level1name

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  PRINT CONCAT (
    @module_name_var_drop
    , ';'
    , @name
    , ';'
    , @level0type
    , ';'
    , @level0name
    , ';'
    , @level1type
    , ';'
    , @level1name
    )

  --EXEC sp_dropextendedproperty
  EXEC @module_name_var_drop @name = @property_name
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name
 END

 FETCH NEXT
 FROM delete_cursor
 INTO @property_name
  , @property_value
  , @level0type
  , @level0name
  , @level1type
  , @level1name
END

CLOSE delete_cursor

DEALLOCATE delete_cursor
```

</details>

[Back to top](#dhw_self)

### sys_self.usp_dropextendedproperty_level_2

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @name | VARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
EXEC [sys_self].usp_dropextendedproperty_level_2
     @name = 'RepoObject_guid'

EXEC [sys_self].usp_dropextendedproperty_level_2
     @name = 'RepoObjectColumn_guid'
*/
CREATE PROCEDURE [sys_self].[usp_dropextendedproperty_level_2] @name VARCHAR(128)
AS
DECLARE @DbName SYSNAME = DB_NAME()

PRINT @DbName

DECLARE @module_name_var_drop NVARCHAR(500) = QUOTENAME(@DbName) + '.sys.sp_dropextendedproperty'

PRINT @module_name_var_drop

DECLARE delete_cursor CURSOR READ_ONLY
FOR
SELECT [property_name]
 , [property_value]
 , [level0type]
 , [level0name]
 , [level1type]
 , [level1name]
 , [level2type]
 , [level2name]
FROM sys_self.[ExtendedProperties_ParameterForAddUpdateDrop]
WHERE [property_name] = @name
 AND NOT [level1type] IS NULL
 AND NOT [level1name] IS NULL
 AND NOT [level2type] IS NULL
 AND NOT [level2name] IS NULL

DECLARE @property_name VARCHAR(128)
 , @property_value SQL_VARIANT
 , @level0type VARCHAR(128)
 , @level0name VARCHAR(128)
 , @level1type VARCHAR(128)
 , @level1name VARCHAR(128)
 , @level2type VARCHAR(128)
 , @level2name VARCHAR(128)

OPEN delete_cursor

FETCH NEXT
FROM delete_cursor
INTO @property_name
 , @property_value
 , @level0type
 , @level0name
 , @level1type
 , @level1name
 , @level2type
 , @level2name

WHILE @@fetch_status <> - 1
BEGIN
 IF @@fetch_status <> - 2
 BEGIN
  PRINT CONCAT (
    @module_name_var_drop
    , ';'
    , @name
    , ';'
    , @level0type
    , ';'
    , @level0name
    , ';'
    , @level1type
    , ';'
    , @level1name
    , ';'
    , @level2type
    , ';'
    , @level2name
    )

  --EXEC sp_dropextendedproperty
  EXEC @module_name_var_drop @name = @property_name
   , @level0type = @level0type
   , @level0name = @level0name
   , @level1type = @level1type
   , @level1name = @level1name
   , @level2type = @level2type
   , @level2name = @level2name
 END

 FETCH NEXT
 FROM delete_cursor
 INTO @property_name
  , @property_value
  , @level0type
  , @level0name
  , @level1type
  , @level1name
  , @level2type
  , @level2name
END

CLOSE delete_cursor

DEALLOCATE delete_cursor
```

</details>

[Back to top](#dhw_self)

</details>

## Scalar Functions

<details><summary>Click to expand</summary>

* [dbo.fn_diagramobjects](#dbofn_diagramobjects)
* [repo.fs_dwh_database_name](#repofs_dwh_database_name)
* [repo.fs_get_parameter_value](#repofs_get_parameter_value)
* [repo.fs_get_RepoObjectColumnProperty_nvarchar](#repofs_get_repoobjectcolumnproperty_nvarchar)
* [repo.fs_get_RepoObjectProperty_nvarchar](#repofs_get_repoobjectproperty_nvarchar)

### dbo.fn_diagramobjects

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| *Output* | INT | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

	CREATE FUNCTION dbo.fn_diagramobjects() 
	RETURNS int
	WITH EXECUTE AS N'dbo'
	AS
	BEGIN
		declare @id_upgraddiagrams		int
		declare @id_sysdiagrams			int
		declare @id_helpdiagrams		int
		declare @id_helpdiagramdefinition	int
		declare @id_creatediagram	int
		declare @id_renamediagram	int
		declare @id_alterdiagram 	int 
		declare @id_dropdiagram		int
		declare @InstalledObjects	int

		select @InstalledObjects = 0

		select 	@id_upgraddiagrams = object_id(N'dbo.sp_upgraddiagrams'),
			@id_sysdiagrams = object_id(N'dbo.sysdiagrams'),
			@id_helpdiagrams = object_id(N'dbo.sp_helpdiagrams'),
			@id_helpdiagramdefinition = object_id(N'dbo.sp_helpdiagramdefinition'),
			@id_creatediagram = object_id(N'dbo.sp_creatediagram'),
			@id_renamediagram = object_id(N'dbo.sp_renamediagram'),
			@id_alterdiagram = object_id(N'dbo.sp_alterdiagram'), 
			@id_dropdiagram = object_id(N'dbo.sp_dropdiagram')

		if @id_upgraddiagrams is not null
			select @InstalledObjects = @InstalledObjects + 1
		if @id_sysdiagrams is not null
			select @InstalledObjects = @InstalledObjects + 2
		if @id_helpdiagrams is not null
			select @InstalledObjects = @InstalledObjects + 4
		if @id_helpdiagramdefinition is not null
			select @InstalledObjects = @InstalledObjects + 8
		if @id_creatediagram is not null
			select @InstalledObjects = @InstalledObjects + 16
		if @id_renamediagram is not null
			select @InstalledObjects = @InstalledObjects + 32
		if @id_alterdiagram  is not null
			select @InstalledObjects = @InstalledObjects + 64
		if @id_dropdiagram is not null
			select @InstalledObjects = @InstalledObjects + 128
		
		return @InstalledObjects 
	END
	
```

</details>

[Back to top](#dhw_self)

### repo.fs_dwh_database_name

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| *Output* | NVARCHAR(128) | yes |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE FUNCTION [repo].[fs_dwh_database_name] ()
RETURNS NVARCHAR(128)
AS
BEGIN
 RETURN (
   SELECT CAST([Parameter_value__result_nvarchar] AS NVARCHAR(128)) AS [dwh_database_name]
   FROM [repo].[Parameter]
   WHERE [Parameter_name] = 'dwh_database_name'
    AND [sub_Parameter] = ''
   )
END
```

</details>

[Back to top](#dhw_self)

### repo.fs_get_parameter_value

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| *Output* | NVARCHAR(4000) | yes |  |
| @Parameter_name | VARCHAR(100) | no |  |
| @sub_Parameter | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE FUNCTION [repo].[fs_get_parameter_value] (
 @Parameter_name VARCHAR(100)
 , @sub_Parameter NVARCHAR(128) = N''
 )
RETURNS nvarchar(4000)
AS
BEGIN
 RETURN (
   SELECT [Parameter_value__result_nvarchar]
   FROM [repo].[Parameter]
   WHERE [Parameter_name] = @Parameter_name
    AND [sub_Parameter] = @sub_Parameter
   )
END
```

</details>

[Back to top](#dhw_self)

### repo.fs_get_RepoObjectColumnProperty_nvarchar

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| *Output* | NVARCHAR(4000) | yes |  |
| @RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| @property_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE FUNCTION [repo].fs_get_RepoObjectColumnProperty_nvarchar (
 @RepoObjectColumn_guid uniqueidentifier
 , @property_name NVARCHAR(128)
 )
RETURNS nvarchar(4000)
AS
BEGIN
 RETURN (
   SELECT [property_nvarchar]
   FROM [repo].[RepoObjectColumnProperty]
   WHERE [RepoObjectColumn_guid] = @RepoObjectColumn_guid
    AND [property_name] = @property_name
   )
END

```

</details>

[Back to top](#dhw_self)

### repo.fs_get_RepoObjectProperty_nvarchar

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| *Output* | NVARCHAR(4000) | yes |  |
| @RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @property_name | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE FUNCTION [repo].fs_get_RepoObjectProperty_nvarchar (
 @RepoObject_guid uniqueidentifier
 , @property_name NVARCHAR(128)
 )
RETURNS nvarchar(4000)
AS
BEGIN
 RETURN (
   SELECT [property_nvarchar]
   FROM [repo].[RepoObjectProperty]
   WHERE [RepoObject_guid] = @RepoObject_guid
    AND [property_name] = @property_name
   )
END

```

</details>

[Back to top](#dhw_self)

</details>

## Table Functions

<details><summary>Click to expand</summary>

* [repo.ftv_dwh_database](#repoftv_dwh_database)
* [repo.ftv_ExecutionLog_tree](#repoftv_executionlog_tree)
* [repo.ftv_GeneratorUspStep_sql](#repoftv_generatoruspstep_sql)
* [repo.ftv_GeneratorUspStep_tree](#repoftv_generatoruspstep_tree)
* [repo.ftv_get_parameter_value](#repoftv_get_parameter_value)
* [repo.ftv_query_plan_extract_source](#repoftv_query_plan_extract_source)
* [repo.ftv_RepoObject_ColumReferenceRepoObject](#repoftv_repoobject_columreferencerepoobject)
* [repo.ftv_RepoObject_DbmlColumnRelation](#repoftv_repoobject_dbmlcolumnrelation)
* [repo.ftv_RepoObject_ReferenceTree](#repoftv_repoobject_referencetree)
* [repo.ftv_RepoObject_ReferenceTree_via_fullname](#repoftv_repoobject_referencetree_via_fullname)
* [repo.ftv_RepoObjectColumn_ReferenceTree](#repoftv_repoobjectcolumn_referencetree)
* [repo.ftv_sqlparse](#repoftv_sqlparse)
* [repo.ftv_sqlparse_children_pivot](#repoftv_sqlparse_children_pivot)
* [repo.ftv_sqlparse_IdentifierList__TestOnly](#repoftv_sqlparse_identifierlist__testonly)
* [repo.ftv_sqlparse_with_some_children](#repoftv_sqlparse_with_some_children)

### repo.ftv_dwh_database

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE FUNCTION [repo].[ftv_dwh_database] ()
 --returns nvarchar(128)
RETURNS TABLE
AS
RETURN (
  SELECT CAST([Parameter_value__result_nvarchar] AS NVARCHAR(128)) AS [dwh_database_name]
   , DB_ID(CAST([Parameter_value__result_nvarchar] AS NVARCHAR(128))) AS [dwh_database_id]
  FROM [repo].[Parameter]
  WHERE [Parameter_name] = 'dwh_database_name'
   AND [sub_Parameter] = N''
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_ExecutionLog_tree

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @execution_instance_guid | UNIQUEIDENTIFIER | no |  |
| @parent_execution_log_id | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*

resulting PlantUML

@startsalt
{
{T
'Procedure
+ [repo].[usp_main]
++ [repo].[usp_sync_guid]
+++ [repo].[usp_sync_guid_RepoObject]
++++ [graph].[usp_PERSIST_RepoObject]
++++ [graph].[usp_PERSIST_ProcedureInstance]
+++ [repo].[usp_sync_guid_RepoObjectColumn]
++++ [graph].[usp_PERSIST_RepoObjectColumn]
++ [repo].[usp_update_Referencing_Count]
++ [repo].[usp_index_inheritance]
+++ [repo].[usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]
+++ [repo].[usp_Index_Settings]
++ [repo].[usp_RepoObjectColumn_update_RepoObjectColumn_column_id]
++ [repo].[usp_GeneratorUsp_insert_update_persistence]
}
}
@endsalt

or as table with duration

@startsalt
{
{T
Procedure  |  Duration
+ [repo].[usp_main]  |  62
++ [repo].[usp_sync_guid]  |  10
+++ [repo].[usp_sync_guid_RepoObject]  |  1
++++ [graph].[usp_PERSIST_RepoObject]  |  0
++++ [graph].[usp_PERSIST_ProcedureInstance]  |  0
+++ [repo].[usp_sync_guid_RepoObjectColumn]  |  5
++++ [graph].[usp_PERSIST_RepoObjectColumn]  |  0
++ [repo].[usp_update_Referencing_Count]  |  6
++ [repo].[usp_index_inheritance]  |  8
+++ [repo].[usp_PERSIST_IndexColumn_ReferencedReferencing_HasFullColumnsInReferencing_T]  |  2
+++ [repo].[usp_Index_Settings]  |  1
++ [repo].[usp_RepoObjectColumn_update_RepoObjectColumn_column_id]  |  1
++ [repo].[usp_GeneratorUsp_insert_update_persistence]  |  4
}
}
@endsalt


select
*
from
[repo].[ftv_ExecutionLog_tree] (DEFAULT, DEFAULT)
order by 
id

*/
CREATE FUNCTION [repo].[ftv_ExecutionLog_tree] (
 @execution_instance_guid UNIQUEIDENTIFIER = NULL
 , @parent_execution_log_id INT = NULL
 )
RETURNS TABLE
AS
RETURN (
  WITH tree AS
   --tree is recursive to solve parent child hierarchies
   (
    SELECT [execution_instance_guid]
     , [id]
     , [parent_execution_log_id]
     , 1 AS [Depth]
     , [proc_schema_name]
     , [proc_name]
     , [step_id]
     , [duration__current_execution_guid]
    FROM [repo].[ExecutionLog_gross]
    WHERE (
      [id] = @parent_execution_log_id
      OR @parent_execution_log_id IS NULL
      AND [parent_execution_log_id] IS NULL
      )
     AND (
      [execution_instance_guid] = @execution_instance_guid
      OR @execution_instance_guid IS NULL
      )
     AND [step_id] = 1
    
    UNION ALL
    
    SELECT [child].[execution_instance_guid]
     , [child].[id]
     , [child].[parent_execution_log_id]
     , [parent].[Depth] + 1
     , [child].[proc_schema_name]
     , [child].[proc_name]
     , [child].[step_id]
     , [child].[duration__current_execution_guid]
    FROM [repo].[ExecutionLog_gross] AS child
    INNER JOIN tree AS parent
     ON child.[parent_execution_log_id] = parent.[id]
    WHERE
     --
     [child].[execution_instance_guid] = [parent].[execution_instance_guid]
     AND [child].[step_id] = 1
    )
  SELECT
   --
   *
   , PlantUmlTree = CONCAT (
    REPLICATE('+', Depth)
    , ' '
    , QUOTENAME([proc_schema_name])
    , '.'
    , QUOTENAME([proc_name])
    )
   , PlantUmlTreeTable = CONCAT (
    REPLICATE('+', Depth)
    , ' '
    , QUOTENAME([proc_schema_name])
    , '.'
    , QUOTENAME([proc_name])
    , '  |  '
    , [duration__current_execution_guid]
    )
  FROM tree
  )

```

</details>

[Back to top](#dhw_self)

### repo.ftv_GeneratorUspStep_sql

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @usp_id | INT | no |  |
| @number | INT | no |  |
| @usp_has_logging | TINYINT | no |  |
| @required_Begin_count | INT | no |  |
| @required_End_count | INT | no |  |
| @is_required_ELSE | TINYINT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE FUNCTION [repo].[ftv_GeneratorUspStep_sql] (
 @usp_id INT
 , @number INT
 , @usp_has_logging TINYINT = 0
 , @required_Begin_count INT = 0 --how many "BEGIN" should be added in front of statement (required in condition blocks)
 , @required_End_count INT = 0 --how many "END" should be added at the of statement (required in condition blocks)
 , @is_required_ELSE TINYINT = 0 --"ELSE" should be added in front of statement (required in condition blocks)
 )
RETURNS TABLE
AS
RETURN (
  SELECT
   --
   SqlStep =
   --
   CONCAT (
    CAST('' AS NVARCHAR(max))
    , '/*'
    , (
     SELECT [Number]
      , [Parent_Number]
      , [Name]
      , [has_logging]
      , [is_condition]
      , [is_inactive]
      , [is_SubProcedure]
      , [log_source_object]
      , [log_target_object]
      , [log_flag_InsertUpdateDelete]
      , [info_01]
      , [info_02]
      , [info_03]
      , [info_04]
      , [info_05]
      , [info_06]
      , [info_07]
      , [info_08]
      , [info_09]
     FOR json path
      , ROOT('ReportUspStep')
     )
    , '*/'
    , CHAR(13)
    , CHAR(10)
    , CASE @is_required_ELSE
     WHEN 1
      THEN 'ELSE' + CHAR(13) + CHAR(10)
     END
    , REPLICATE('BEGIN' + CHAR(13) + CHAR(10), @required_Begin_count)
    , CASE 
     WHEN [is_SubProcedure] = 1
      THEN
       --no logging
       CONCAT (
        'EXEC '
        , [Statement]
        , CHAR(13)
        , CHAR(10)
        , '--add your own parameters'
        , CASE 
         WHEN NOT [info_01] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , '@'
            , [info_01]
            )
         END
        , CASE 
         WHEN NOT [info_02] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_02]
            )
         END
        , CASE 
         WHEN NOT [info_03] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_03]
            )
         END
        , CASE 
         WHEN NOT [info_04] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_04]
            )
         END
        , CASE 
         WHEN NOT [info_05] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_05]
            )
         END
        , CASE 
         WHEN NOT [info_06] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_06]
            )
         END
        , CASE 
         WHEN NOT [info_07] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_07]
            )
         END
        , CASE 
         WHEN NOT [info_08] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_08]
            )
         END
        , CASE 
         WHEN NOT [info_09] IS NULL
          THEN CONCAT (
            CHAR(13)
            , CHAR(10)
            , '  '
            , ','
            , '@'
            , [info_09]
            )
         END
        , CASE 
         WHEN @usp_has_logging = 1
          THEN CONCAT (
            ''
            , CASE 
             WHEN NOT [info_01] IS NULL
              OR NOT [info_02] IS NULL
              OR NOT [info_03] IS NULL
              OR NOT [info_04] IS NULL
              OR NOT [info_05] IS NULL
              OR NOT [info_06] IS NULL
              OR NOT [info_07] IS NULL
              OR NOT [info_08] IS NULL
              OR NOT [info_09] IS NULL
              THEN CONCAT (
                CHAR(13)
                , CHAR(10)
                , ','
                )
             END
            , CHAR(13)
            , CHAR(10)
            , '--logging parameters'
            , CHAR(13)
            , CHAR(10)
            , ' @execution_instance_guid = @execution_instance_guid'
            , CHAR(13)
            , CHAR(10)
            , ' , @ssis_execution_id = @ssis_execution_id'
            , CHAR(13)
            , CHAR(10)
            , ' , @sub_execution_id = @sub_execution_id'
            , CHAR(13)
            , CHAR(10)
            , ' , @parent_execution_log_id = @current_execution_log_id'
            )
         END
        , CHAR(13)
        , CHAR(10)
        )
     WHEN [is_condition] = 1
      THEN
       --no logging
       CONCAT (
        'IF '
        , [Statement]
        )
     ELSE
      --other statements
      CONCAT (
       ''
       , 'PRINT CONCAT(''usp_id;Number;Parent_Number: '','
       , [usp_id]
       , ','';'','
       , [Number]
       , ','';'','
       , CASE 
        WHEN NOT [Parent_Number] IS NULL
         THEN CAST([Parent_Number] AS VARCHAR(50))
        ELSE 'NULL'
        END
       , ');'
       , CHAR(13)
       , CHAR(10)
       , CHAR(13)
       , CHAR(10)
       , [Statement]
       --logging depending on parameter @usp_has_logging
       , CASE 
        WHEN @usp_has_logging = 1
         AND [has_logging] = 1
         THEN CONCAT (
           ''
           , CHAR(13)
           , CHAR(10)
           , CHAR(13)
           , CHAR(10)
           , '-- Logging START --'
           , CHAR(13)
           , CHAR(10)
           , 'SET @rows = @@ROWCOUNT'
           , CHAR(13)
           , CHAR(10)
           , 'SET @step_id = @step_id + 1'
           --, char(13), char(10), 'SET @step_name = ''', [Name], ''''
           , CHAR(13)
           , CHAR(10)
           , 'SET @step_name = '
           , CASE 
            WHEN NOT [Name] IS NULL
             THEN '''' + REPLACE([Name], '''', '''''') + ''''
            ELSE 'NULL'
            END
           , CHAR(13)
           , CHAR(10)
           , 'SET @source_object = '
           , CASE 
            WHEN NOT [log_source_object] IS NULL
             THEN '''' + [log_source_object] + ''''
            ELSE 'NULL'
            END
           , CHAR(13)
           , CHAR(10)
           , 'SET @target_object = '
           , CASE 
            WHEN NOT [log_target_object] IS NULL
             THEN '''' + [log_target_object] + ''''
            ELSE 'NULL'
            END
           , CHAR(13)
           , CHAR(10)
           , CHAR(13)
           , CHAR(10)
           , 'EXEC repo.usp_ExecutionLog_insert '
           , CHAR(13)
           , CHAR(10)
           , ' @execution_instance_guid = @execution_instance_guid'
           , CHAR(13)
           , CHAR(10)
           , ' , @ssis_execution_id = @ssis_execution_id'
           , CHAR(13)
           , CHAR(10)
           , ' , @sub_execution_id = @sub_execution_id'
           , CHAR(13)
           , CHAR(10)
           , ' , @parent_execution_log_id = @parent_execution_log_id'
           , CHAR(13)
           , CHAR(10)
           , ' , @current_execution_guid = @current_execution_guid'
           , CHAR(13)
           , CHAR(10)
           , ' , @proc_id = @proc_id'
           , CHAR(13)
           , CHAR(10)
           , ' , @proc_schema_name = @proc_schema_name'
           , CHAR(13)
           , CHAR(10)
           , ' , @proc_name = @proc_name'
           , CHAR(13)
           , CHAR(10)
           , ' , @event_info = @event_info'
           , CHAR(13)
           , CHAR(10)
           , ' , @step_id = @step_id'
           , CHAR(13)
           , CHAR(10)
           , ' , @step_name = @step_name'
           , CHAR(13)
           , CHAR(10)
           , ' , @source_object = @source_object'
           , CHAR(13)
           , CHAR(10)
           , ' , @target_object = @target_object'
           , CHAR(13)
           , CHAR(10)
           , CASE [log_flag_InsertUpdateDelete]
            WHEN 'I'
             THEN ' , @inserted = @rows'
            WHEN 'U'
             THEN ' , @updated = @rows'
            WHEN 'D'
             THEN ' , @deleted = @rows'
            END
           , CASE 
            WHEN NOT [info_01] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_01]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_02] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_02]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_03] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_03]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_04] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_04]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_05] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_05]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_06] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_06]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_07] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_07]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_08] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_08]
               , ''''
               )
            END
           , CASE 
            WHEN NOT [info_09] IS NULL
             THEN CONCAT (
               CHAR(13)
               , CHAR(10)
               , ' , @info_01 = '''
               , [info_09]
               , ''''
               )
            END
           , CHAR(13)
           , CHAR(10)
           , '-- Logging END --'
           --, char(13), char(10)
           )
        END
       )
     END
    , REPLICATE(CHAR(13) + CHAR(10) + 'END;', @required_End_count)
    , CHAR(13)
    , CHAR(10)
    )
   , Number
   , [Statement]
  FROM [repo].[GeneratorUspStep] s
  WHERE s.[usp_id] = @usp_id
   AND s.Number = @number
  )

```

</details>

[Back to top](#dhw_self)

### repo.ftv_GeneratorUspStep_tree

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @usp_id | INT | no |  |
| @Parent_Number | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

/*
[repo].[GeneratorUspStep] has a parent child structure
here we try to get the numbers in the right order

it is not perfect if the tree is to deep and some "deep" numbers are lower
check the result per [usp_id]
and if it not fits try to use better sorted numbers


----usage
----and how to get required_Begin_count and required_Begin_count for conditions
--
--get all steps per Usp, recursively:
SELECT u.*
 , t.*
FROM [repo].[GeneratorUsp] u
CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([id], NULL) t
ORDER BY [u].id
 , t.[RowNumber_PerUsp]

----and now about conditions
----all this is done because we need to encapsulate condition THEN and ELSE statement in BEGIN...END blocks
----but need to explore the first and last step per condition THEN- or ELSE-block
--
--get all (is_condition = 1) statements and their recursive children
SELECT [s].[usp_id]
 , [s].[Number] AS [Condition_Number]
 --, [s].[Parent_Number]
 --, [s].[Name]
 --, [s].[has_logging]
 --, [s].[is_condition]
 --, [s].[is_inactive]
 --, [s].[is_SubProcedure]
 --, [s].[Statement]
 --, [s].[log_source_object]
 --, [s].[log_target_object]
 --, [s].[log_flag_InsertUpdateDelete]
 --, [s].[info_01]
 --, [s].[info_02]
 --, [s].[info_03]
 --, [s].[info_04]
 --, [s].[info_05]
 --, [s].[info_06]
 --, [s].[info_07]
 --, [s].[info_08]
 --, [s].[info_09]
 --, [t].[usp_id]
 , [t].[child_PerParent]
 , [t].[RowNumber_PerUsp] AS [RowNumber_PerUspAndCondition]
 , [t].[Number]
 , [t].[Asc_PerParentChild]
 , [t].[Desc_PerParentChild]
 , [t].[is_required_ELSE]
--, [t].[Depth]
--, [t].[is_condition]
--, [t].[Root_Sort]
--, [t].[Parent_Number]
--, [t].[Parent_Sort]
--, [t].[Sort]
FROM [repo].[GeneratorUspStep] AS s
CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([usp_id], [Number]) AS t
WHERE [s].[is_condition] = 1
ORDER BY [s].[usp_id]
 , [Condition_Number]
 , [t].[child_PerParent]
 , [RowNumber_PerUspAndCondition]


--evaluate the count and place of BEGIN and END for condition statements:
--t: all recursive children of any step which is a condition
--this should also work for recursive conditions, because ([s].[is_condition] = 1) will filter any conditions
--([t].[Asc_PerParentChild] = 1) indicates a required BEGIN, these are first children of conditions
--([t].[Desc_PerParentChild] = 1) indicates a required BEGIN, these are last children of condition steps

SELECT [s].[usp_id]
 , [t].[Number]
 , required_Begin_count = SUM(IIF([t].[Asc_PerParentChild] = 1, 1, 0))
 , required_End_count = sum(iif([t].[Desc_PerParentChild] = 1, 1, 0))
 , [is_required_ELSE] = MAX([t].[is_required_ELSE])
FROM [repo].[GeneratorUspStep] AS s
CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([usp_id], [Number]) AS t
WHERE [s].[is_condition] = 1
GROUP BY [s].[usp_id]
 , [t].[Number]


 --combine all active steps per usp with required_Begin_count and required_End_count:

SELECT [u].[id]
 --, [u].[usp_schema]
 --, [u].[usp_name]
 , [u].[has_logging]
 --, [u].[usp_Comment]
 , [u].[usp_fullname]
 --, [t].[usp_id]
 , [t].[Number]
 , [t].[RowNumber_PerUsp]
 , [t].[Depth]
 , [t].[is_condition]
 , [t].[Root_Sort]
 --, [t].[Parent_Number]
 --, [t].[Parent_Sort]
 --, [t].[Sort]
 --, [t].[child_PerParent]
 --, [t].[Asc_PerParentChild]
 --, [t].[Desc_PerParentChild]
 , [BeginEnd].[required_Begin_count]
 , [BeginEnd].[required_End_count]
 , [BeginEnd].[is_required_ELSE]
FROM [repo].[GeneratorUsp] AS u
CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([id], NULL) AS t
LEFT JOIN (
 SELECT [s].[usp_id]
  , [t].[Number]
  , [required_Begin_count] = SUM(IIF([t].[Asc_PerParentChild] = 1, 1, 0))
  , [required_End_count] = SUM(IIF([t].[Desc_PerParentChild] = 1, 1, 0))
  , [is_required_ELSE] = MAX([t].[is_required_ELSE])
 FROM [repo].[GeneratorUspStep] AS s
 CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([usp_id], [Number]) AS t
 WHERE [s].[is_condition] = 1
 GROUP BY [s].[usp_id]
  , [t].[Number]
 ) AS BeginEnd
 ON BeginEnd.usp_id = u.id
  AND BeginEnd.Number = t.Number
ORDER BY [u].[id]
 , [t].[RowNumber_PerUsp]

--and finaly use [repo].[ftv_GeneratorUspStep_sql] to create the statement per step

SELECT [u].[id]
 , [t].[Number]
 , [u].[has_logging]
 , [BeginEnd].[required_Begin_count]
 , [BeginEnd].[required_End_count]
 , [BeginEnd].[is_required_ELSE]
 --only information
 , [u].[usp_fullname]
 , [t].[RowNumber_PerUsp]
 --, [t].[Depth]
 --, [t].[is_condition]
 --, [t].[Root_Sort]
 --, [t].[Parent_Number]
 --, [t].[Parent_Sort]
 --, [t].[Sort]
 --, [t].[child_PerParent]
 --, [t].[Asc_PerParentChild]
 --, [t].[Desc_PerParentChild]
 , sql.SqlStep
FROM [repo].[GeneratorUsp] AS u
CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([id], NULL) AS t
LEFT JOIN (
 SELECT [s].[usp_id]
  , [t].[Number]
  , [required_Begin_count] = SUM(IIF([t].[Asc_PerParentChild] = 1, 1, 0))
  , [required_End_count] = SUM(IIF([t].[Desc_PerParentChild] = 1, 1, 0))
  , [is_required_ELSE] = MAX([t].[is_required_ELSE])
 FROM [repo].[GeneratorUspStep] AS s
 CROSS APPLY [repo].[ftv_GeneratorUspStep_tree]([usp_id], [Number]) AS t
 WHERE [s].[is_condition] = 1
 GROUP BY [s].[usp_id]
  , [t].[Number]
 ) AS BeginEnd
 ON BeginEnd.usp_id = u.id
  AND BeginEnd.Number = t.Number
CROSS APPLY [repo].[ftv_GeneratorUspStep_sql]([u].[id], [t].[Number], [u].[has_logging], [BeginEnd].[required_Begin_count], [BeginEnd].[required_End_count], [BeginEnd].[is_required_ELSE]) sql
ORDER BY [u].[id]
 , [t].[RowNumber_PerUsp]


*/
CREATE FUNCTION [repo].[ftv_GeneratorUspStep_tree] (
 @usp_id INT
 , @Parent_Number INT
 --, @usp_has_logging TINYINT = 0
 )
RETURNS TABLE
AS
RETURN (
  WITH tree AS
   --tree is recursive to solve parent child hierarchies
   (
    SELECT [usp_id]
     , [Number]
     , [Parent_Number]
     , 0 AS [Depth]
     , [Number] AS [Sort]
     , [Number] AS [Parent_Sort]
     , [Number] AS [Root_Sort]
     , [is_condition]
     , [child_PerParent] = IIF(NOT [Parent_Number] IS NULL, ROW_NUMBER() OVER (
       PARTITION BY [usp_id]
       , [Parent_Number] ORDER BY [Number]
       ), NULL)
    --ROW_NUMBER() OVER(Partition by [usp_id], [Parent_Number] ORDER BY [Number])
    FROM [repo].[GeneratorUspStep]
    WHERE
     --
     [usp_id] = @usp_id
     AND [is_inactive] = 0
     AND (
      [Parent_Number] = @Parent_Number
      OR @Parent_Number IS NULL
      AND [Parent_Number] IS NULL
      )
    
    UNION ALL
    
    SELECT [child].[usp_id]
     , [child].[Number]
     , [child].[Parent_Number]
     , [parent].[Depth] + 1
     , [child].[Parent_Number] AS [sort]
     , [parent].[Sort] AS [Parent_sort]
     , [parent].[Root_Sort] AS [Root_Sort]
     , [child].[is_condition]
     , [child_PerParent] = [parent].[child_PerParent]
    FROM [repo].[GeneratorUspStep] AS child
    INNER JOIN tree AS parent
     ON child.[Parent_Number] = parent.Number
    WHERE
     --
     [child].[usp_id] = @usp_id
     AND [child].[is_inactive] = 0
    )
   , tree_2 AS
   --tree_2 is required to calculate the correct step order: [RowNumber_PerUsp]
   (
    SELECT
     --
     [tree].[usp_id]
     , [tree].[Number]
     , [RowNumber_PerUsp] = ROW_NUMBER() OVER (
      PARTITION BY [tree].[usp_id] ORDER BY [tree].[Root_Sort]
       , [tree].[Parent_Number]
       , [tree].[Parent_Sort]
       , [tree].[Sort]
      )
     , [tree].[Depth]
     , [tree].[is_condition]
     , [tree].[Root_Sort]
     , [tree].[Parent_Number]
     , [tree].[Parent_Sort]
     , [tree].[Sort]
     , [tree].[child_PerParent]
    FROM tree
    )
   , tree_3 AS
   --final query is used to calculate Asc_PerParentChild and Desc_PerParentChild
   --Asc_PerParentChild is the first step per [child_PerParent]
   --if the @Parent_Number has [is_condition] = 1
   --then [child_PerParent] = 1 is the THEN block an [child_PerParent] = 2 is the ELSE block
   --to encapsulate THEN and ELSE block:
   --a 'BEGIN' is required before Asc_PerParentChild = 1
   --a 'END' is required after Desc_PerParentChild = 1
   (
    SELECT
     --
     *
     , [Asc_PerParentChild] = ROW_NUMBER() OVER (
      PARTITION BY [usp_id]
      , [child_PerParent] ORDER BY [RowNumber_PerUsp]
      )
     , [Desc_PerParentChild] = ROW_NUMBER() OVER (
      PARTITION BY [usp_id]
      , [child_PerParent] ORDER BY [RowNumber_PerUsp] DESC
      )
    FROM tree_2
    )
  SELECT
   --
   *
   --[child_PerParent] = 2 is the ELSE-block, if the parent is a condition
   --in front of the ELSE block the 'ELSE' is required
   , is_required_ELSE = IIF([child_PerParent] = 2
    AND [Asc_PerParentChild] = 1, 1, 0)
  FROM tree_3
  )

```

</details>

[Back to top](#dhw_self)

### repo.ftv_get_parameter_value

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @Parameter_name | VARCHAR(100) | no |  |
| @sub_Parameter | NVARCHAR(128) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql

CREATE FUNCTION [repo].[ftv_get_parameter_value] (
 @Parameter_name VARCHAR(100)
 , @sub_Parameter NVARCHAR(128) = N''
 )
RETURNS TABLE
AS
RETURN (
  SELECT [Parameter_value__result_nvarchar]
  FROM [repo].[Parameter]
  WHERE [Parameter_name] = @Parameter_name
   AND [sub_Parameter] = @sub_Parameter
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_query_plan_extract_source

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @query_plan | XML | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*

OPTION(MAXRECURSION 100) should be used from outer
it is not possible to include this into the table valued function

example:

SELECT TOP 100
       [ro].[RepoObject_guid]
     , [source_columns].*
FROM
     repo.RepoObject AS ro
     CROSS APPLY
     repo_sys.ftv_query_plan_extract_source(SysObject_query_plan) AS source_columns
WHERE  NOT [ro].[SysObject_query_plan] IS NULL OPTION(
                                                      MAXRECURSION 100)

*/
/*
based on
https://stackoverflow.com/questions/45658957/how-to-get-column-level-dependencies-in-a-view

from:
https://stackoverflow.com/users/8478406/basil-kisel

It is a solution based on query plan. It has some adventages

- almost any select queries can be processed
- no SchemaBinding

and disadventages

- has not been tested properly
- can become broken suddenly if Microsoft change XML query plan.

The core idea is that every column expression inside XML query plan is defined in "DefinedValue" node. 
First subnode of "DefinedValue" is a reference to output column and second one is a expression. 
The expression computes from input columns and constant values. 
As mentioned above It's based only on empirical observation and needs to be tested properly.

*/
CREATE FUNCTION [repo].[ftv_query_plan_extract_source] (@query_plan XML)
RETURNS TABLE
 --RETURNS @retColumnReferences TABLE
 --(
 --     -- columns returned by the function
 --    [target_column_name]   NVARCHAR(4000) NULL
 --   , [source_server_name] NVARCHAR(4000) NULL
 --   , [source_database_name] NVARCHAR(4000) NULL
 --   , [source_schema_name]   NVARCHAR(4000) NULL
 --   , [source_table_name]    NVARCHAR(4000) NULL
 --   , [source_column_name]   NVARCHAR(4000) NULL
 --   , [const_value]          NVARCHAR(4000) NULL
 --   , [target_column_info]   XML NULL
 --   , [source_column_info]   XML NULL
 --   , [const_info]           XML NULL
 --)
AS
RETURN
-- body of the function
--Next is a main query. It's biggest part is recursive common table expression for column extraction.
WITH XMLNAMESPACES(DEFAULT 'http://schemas.microsoft.com/sqlserver/2004/07/showplan', 'http://schemas.microsoft.com/sqlserver/2004/07/showplan' AS shp -- Used in .query() for predictive namespace using. 
 )
 , cte_column_dependencies AS (
  --The seed of recursion is a query that extracts columns for #foo table that store 1 row of interested select query.
  SELECT (
    SELECT [foo_col].[info].[query]('./ColumnReference')
    FOR XML RAW('shp:root')
     , TYPE
    ) -- Becouse .value() can't extract attribute from root node.
   AS [target_column_info]
   , (
    SELECT [foo_col].[info].[query]('./ScalarOperator/Identifier/ColumnReference')
    FOR XML RAW('shp:root')
     , TYPE
    ) AS [source_column_info]
   , CAST(NULL AS XML) AS [const_info]
   , 1 AS [iteration_no]
  FROM @query_plan.nodes('//Update/SetPredicate/ScalarOperator/ScalarExpressionList/ScalarOperator/MultipleAssign/Assign') AS foo_col(info)
  WHERE [foo_col].[info].[exist]('./ColumnReference[@Table="[#foo]"]') = 1
  --The recursive part searches for "DefinedValue" node with depended column and extract all "ColumnReference" and "Const" subnodes that used in column expression. It's over complicated by XML to SQL conversions.
  
  UNION ALL
  
  SELECT (
    SELECT [internal_col].[info].[query]('.')
    FOR XML RAW('shp:root')
     , TYPE
    )
   , [source_info].[column_info]
   , [source_info].[const_info]
   , [prev_dependencies].[iteration_no] + 1
  FROM @query_plan.nodes('//DefinedValue/ColumnReference') AS internal_col(info)
  INNER JOIN cte_column_dependencies AS prev_dependencies -- Filters by depended columns.
   ON prev_dependencies.source_column_info.value('(//ColumnReference/@Column)[1]', 'nvarchar(4000)') = internal_col.info.value('(./@Column)[1]', 'nvarchar(4000)')
    AND EXISTS (
     SELECT [prev_dependencies].[source_column_info].value('(.//@Schema)[1]', 'nvarchar(4000)')
     
     INTERSECT
     
     SELECT [internal_col].[info].value('(./@Schema)[1]', 'nvarchar(4000)')
     )
    AND EXISTS (
     SELECT [prev_dependencies].[source_column_info].value('(.//@Database)[1]', 'nvarchar(4000)')
     
     INTERSECT
     
     SELECT [internal_col].[info].value('(./@Database)[1]', 'nvarchar(4000)')
     )
    AND EXISTS (
     SELECT [prev_dependencies].[source_column_info].value('(.//@Server)[1]', 'nvarchar(4000)')
     
     INTERSECT
     
     SELECT [internal_col].[info].value('(./@Server)[1]', 'nvarchar(4000)')
     )
  CROSS APPLY (
   -- Becouse only column or only constant can be places in result row.
   SELECT (
     SELECT [source_col].[info].[query]('.')
     FOR XML RAW('shp:root')
      , TYPE
     ) AS [column_info]
    , NULL AS [const_info]
   FROM internal_col.info.nodes('..//ColumnReference') AS source_col(info)
   
   UNION ALL
   
   SELECT NULL AS [column_info]
    , (
     SELECT [const].[info].[query]('.')
     FOR XML RAW('shp:root')
      , TYPE
     ) AS [const_info]
   FROM internal_col.info.nodes('..//Const') AS const(info)
   ) AS source_info
  WHERE [source_info].[column_info] IS NULL
   OR -- Except same node selected by '..//ColumnReference' from its sources. Sorry, I'm not so well to check it with XQuery simple.
   [source_info].[column_info].value('(//@Column)[1]', 'nvarchar(4000)') <> [internal_col].[info].value('(./@Column)[1]', 'nvarchar(4000)')
   AND (
    SELECT [source_info].[column_info].value('(//@Schema)[1]', 'nvarchar(4000)')
    
    INTERSECT
    
    SELECT [internal_col].[info].value('(./@Schema)[1]', 'nvarchar(4000)')
    ) IS NULL
   AND (
    SELECT [source_info].[column_info].value('(//@Database)[1]', 'nvarchar(4000)')
    
    INTERSECT
    
    SELECT [internal_col].[info].value('(./@Database)[1]', 'nvarchar(4000)')
    ) IS NULL
   AND (
    SELECT [source_info].[column_info].value('(//@Server)[1]', 'nvarchar(4000)')
    
    INTERSECT
    
    SELECT [internal_col].[info].value('(./@Server)[1]', 'nvarchar(4000)')
    ) IS NULL
  )

----Finally, It's select statement that convert XML to appropriate human text.
--INSERT INTO @retColumnReferences
--(
--     [target_column_name]
--     , [source_server_name]
--     , [source_database_name]
--     , [source_schema_name]
--     , [source_table_name]
--     , [source_column_name]
--     , [const_value]
--     , [target_column_info]
--     , [source_column_info]
--     , [const_info]
--)
SELECT [target_column_name] = [col_dep].[target_column_info].value('(.//shp:ColumnReference/@Column)[1]', 'nvarchar(4000)')
 , [source_server_name] = [col_dep].[source_column_info].value('(.//shp:ColumnReference/@Server)[1]', 'nvarchar(4000)')
 , [source_database_name] = [col_dep].[source_column_info].value('(.//shp:ColumnReference/@Database)[1]', 'nvarchar(4000)')
 , [source_schema_name] = [col_dep].[source_column_info].value('(.//shp:ColumnReference/@Schema)[1]', 'nvarchar(4000)')
 , [source_table_name] = [col_dep].[source_column_info].value('(.//shp:ColumnReference/@Table)[1]', 'nvarchar(4000)')
 , [source_column_name] = [col_dep].[source_column_info].value('(.//shp:ColumnReference/@Column)[1]', 'nvarchar(4000)')
 , [const_value] = [col_dep].[const_info].value('(/shp:root/shp:Const/@ConstValue)[1]', 'nvarchar(4000)')
 , [col_dep].[target_column_info]
 , [col_dep].[source_column_info]
 , [col_dep].[const_info]
--  col_dep.target_column_info
--, col_dep.source_column_info
--, col_dep.const_info
--  coalesce(col_dep.target_column_info.value('(.//shp:ColumnReference/@Server)[1]'   ,'nvarchar(4000)') + '.' ,'')
--+ coalesce(col_dep.target_column_info.value('(.//shp:ColumnReference/@Database)[1]' ,'nvarchar(4000)') + '.' ,'')
--+ coalesce(col_dep.target_column_info.value('(.//shp:ColumnReference/@Schema)[1]'   ,'nvarchar(4000)') + '.' ,'')
--+ col_dep.target_column_info.value('(.//shp:ColumnReference/@Column)[1]' ,'nvarchar(4000)')
--  as target_column_name
--, coalesce(col_dep.source_column_info.value('(.//shp:ColumnReference/@Server)[1]'   ,'nvarchar(4000)') + '.' ,'')
--+ coalesce(col_dep.source_column_info.value('(.//shp:ColumnReference/@Database)[1]' ,'nvarchar(4000)') + '.' ,'')
--+ coalesce(col_dep.source_column_info.value('(.//shp:ColumnReference/@Schema)[1]'   ,'nvarchar(4000)') + '.' ,'')
--+ col_dep.source_column_info.value('(.//shp:ColumnReference/@Column)[1]' ,'nvarchar(4000)')
--  as source_column_name
--
FROM cte_column_dependencies AS col_dep
 --ORDER BY
 --         [col_dep].[iteration_no]
 --       , [target_column_name]
 --       , [source_column_name]
 --
 --/*
 --https://stackoverflow.com/questions/7428669/how-to-set-the-maxrecursion-option-for-a-cte-inside-a-table-valued-function
 --https://social.msdn.microsoft.com/Forums/en-US/7c7d5fea-38ad-4bc5-9038-a157e640561f/using-option-clause-within-create-function-statement-for-inline-table-functions?forum=transactsql
 --[the] OPTION clause can be used only at the statement level
 --So you cannot use it within a query expression inside view definitions or inline TVFs etc.
 --The only way to use it in your case is to create the TVF without the OPTION clause and specify it in the query that uses the TVF. 
 --We have a bug that tracks request for allowing use of OPTION clause inside any query expression (for example, if exists() or CTE or view).
 --You can not change the default value of that option inside a udf. 
 --You will have to do it in the statement referencing the udf.
 --*/
 --
 --OPTION(MAXRECURSION 100) -- It's an assurance from infinite loop.
```

</details>

[Back to top](#dhw_self)

### repo.ftv_RepoObject_ColumReferenceRepoObject

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @Referenced_Depth | INT | no |  |
| @Referencing_Depth | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
--based on [repo].[RepoObjectColumn_ReferenceTree]
--return referenced and referencing RepoObject
--Default:
--@Referenced_Depth = 1
--@Referencing_Depth

DECLARE @RepoObject_guid uniqueidentifier

SET @RepoObject_guid = (SELECT RepoObject_guid from [repo].[RepoObject] where RepoObject_fullname = '[repo].[RepoObject_gross]')

SELECT *
FROM [repo].[ftv_RepoObject_ColumReferenceRepoObject](@RepoObject_guid, DEFAULT, DEFAULT)

SELECT *
FROM [repo].[ftv_RepoObject_ColumReferenceRepoObject](@RepoObject_guid, 1, 1)

*/
CREATE FUNCTION [repo].[ftv_RepoObject_ColumReferenceRepoObject] (
 @RepoObject_guid UNIQUEIDENTIFIER
 , @Referenced_Depth INT = 1
 , @Referencing_Depth INT = 1
 )
RETURNS TABLE
AS
RETURN (
  WITH ro AS (
    --all RepoObject which are [Referenced_RepoObject_guid] or [Referencing_RepoObject_guid]
    SELECT DISTINCT [Referenced_fullname] AS [RepoObject_fullname]
     , [Referenced_RepoObject_guid] AS [RepoObject_guid]
     , [Referenced_type] AS [RepoObject_type]
     , NULL AS [DbmlRelation]
     , @RepoObject_guid AS [Parameter_RepoObject_guid]
    FROM [repo].[RepoObjectColumn_ReferenceTree]
    WHERE [Referenced_RepoObject_guid] = @RepoObject_guid
    
    UNION
    
    SELECT DISTINCT [Referencing_fullname]
     , [Referencing_RepoObject_guid]
     , [Referencing_type]
     , NULL AS [DbmlRelation]
     , @RepoObject_guid
    FROM [repo].[RepoObjectColumn_ReferenceTree]
    WHERE [Referencing_RepoObject_guid] = @RepoObject_guid
    
    UNION
    
    --add all referenced
    SELECT DISTINCT [rt].[Referenced_fullname]
     , [rt].[Referenced_RepoObject_guid]
     , [rt].[Referenced_type]
     , [rs].[DbmlRelation]
     , @RepoObject_guid
    FROM [repo].[RepoObjectColumn_ReferenceTree] AS rt
    LEFT JOIN [repo].[RepoObjectColumn_RelationScript] AS rs
     ON rs.referenced_RepoObject_guid = rt.[Referenced_RepoObject_guid]
      AND rs.referencing_RepoObject_guid = @RepoObject_guid
    WHERE [rt].[Referencing_RepoObject_guid] = @RepoObject_guid
     AND [Referenced_Depth] <= @Referenced_Depth
     AND [Referencing_Depth] = 0
    
    UNION
    
    --add all referenced
    SELECT DISTINCT [rt].[Referencing_fullname]
     , [rt].[Referencing_RepoObject_guid]
     , [rt].[Referencing_type]
     , [rs].[DbmlRelation]
     , @RepoObject_guid
    FROM [repo].[RepoObjectColumn_ReferenceTree] AS rt
    LEFT JOIN [repo].[RepoObjectColumn_RelationScript] AS rs
     ON rs.referenced_RepoObject_guid = @RepoObject_guid
      AND rs.referencing_RepoObject_guid = rt.[Referencing_RepoObject_guid]
    WHERE [rt].[Referenced_RepoObject_guid] = @RepoObject_guid
     AND [Referenced_Depth] = 0
     AND [Referencing_Depth] <= @Referencing_Depth
    )
  --
  SELECT [ro].[RepoObject_fullname]
   , [ro].[RepoObject_guid]
   , [ro].[RepoObject_type]
   , [dbml].[DbmlTable] AS [Dbml]
   , [ro].[Parameter_RepoObject_guid]
  FROM ro
  LEFT JOIN [repo].[RepoObject_SqlCreateTable] AS dbml
   ON dbml.RepoObject_guid = ro.RepoObject_guid
  
  UNION
  
  SELECT NULL
   , [ro].[Parameter_RepoObject_guid]
   , NULL
   , [ro].[DbmlRelation]
   , [ro].[Parameter_RepoObject_guid]
  FROM [ro]
  WHERE NOT [ro].[DbmlRelation] IS NULL
   --
  )

```

</details>

[Back to top](#dhw_self)

### repo.ftv_RepoObject_DbmlColumnRelation

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @Referenced_Depth | INT | no |  |
| @Referencing_Depth | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
Wahrscheinlich unnötig, da auch alle Daten in [repo].[RepoObjectColumn_ReferenceTree] enthalten sind


--Duplicates are possible, if exists alternative path between objects with different depth
--to elimenate them, exclude Referenced_Depth and Referencing_Depth and use DISTINCT


DECLARE @RepoObject_guid uniqueidentifier

SET @RepoObject_guid = (SELECT RepoObject_guid from [repo].[RepoObject] where RepoObject_fullname = '[repo].[RepoObject_gross]')

SELECT *
FROM [repo].[ftv_RepoObject_DbmlColumnRelation](@RepoObject_guid, DEFAULT, DEFAULT)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_DbmlColumnRelation](@RepoObject_guid, 1, 1)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]


*/
CREATE FUNCTION [repo].[ftv_RepoObject_DbmlColumnRelation] (
 @RepoObject_guid uniqueidentifier
 , @Referenced_Depth INT = 1
 , @Referencing_Depth INT = 1
 )
RETURNS TABLE
AS
RETURN (
  --trees are recursive to get parent child relations
  WITH tree_referenced AS (
    SELECT [FirstNode].*
     , 1 AS [Referenced_Depth]
     , 0 AS [Referencing_Depth]
    FROM graph.RepoObjectColumn_ReferencingReferenced AS FirstNode
    WHERE [Referencing_RepoObject_guid] = @RepoObject_guid
     AND 1 <= @Referenced_Depth
    
    UNION ALL
    
    SELECT [child].*
     , [Referenced_Depth] = [parent].[Referenced_Depth] + 1
     , 0
    FROM graph.RepoObjectColumn_ReferencingReferenced AS child
    INNER JOIN tree_referenced AS parent
     ON [child].Referencing_guid = [parent].Referenced_guid
    WHERE [parent].[Referenced_Depth] < @Referenced_Depth
    )
   , tree_referencing AS (
    SELECT [FirstNode].*
     , 0 AS [Referenced_Depth]
     , 1 AS [Referencing_Depth]
    FROM graph.RepoObjectColumn_ReferencingReferenced AS FirstNode
    WHERE [Referenced_guid] = @RepoObject_guid
     AND 1 <= @Referencing_Depth
    
    UNION ALL
    
    SELECT [child].*
     , 0
     , [Referencing_Depth] = [parent].[Referencing_Depth] + 1
    FROM graph.RepoObjectColumn_ReferencingReferenced AS child
    INNER JOIN tree_referencing AS parent
     ON [child].Referenced_guid = [parent].Referencing_guid
    WHERE [parent].[Referencing_Depth] < @Referencing_Depth
    )
  SELECT *
   , @RepoObject_guid AS RepoObject_guid
  FROM tree_referenced
  
  UNION
  
  SELECT *
   , @RepoObject_guid AS RepoObject_guid
  FROM tree_referencing
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_RepoObject_ReferenceTree

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObject_guid | UNIQUEIDENTIFIER | no |  |
| @Referenced_Depth | INT | no |  |
| @Referencing_Depth | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
--Duplicates are possible, if exists alternative path between objects with different depth
--to elimenate them, exclude Referenced_Depth and Referencing_Depth and use DISTINCT


DECLARE @RepoObject_guid uniqueidentifier

SET @RepoObject_guid = (SELECT RepoObject_guid from [repo].[RepoObject] where RepoObject_fullname = '[repo].[RepoObject_gross]')

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree](@RepoObject_guid, DEFAULT, DEFAULT)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree](@RepoObject_guid, 1, 1)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree](@RepoObject_guid, 0, 6)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree](@RepoObject_guid, 100, 100)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]


*/
CREATE FUNCTION [repo].[ftv_RepoObject_ReferenceTree] (
 @RepoObject_guid uniqueidentifier
 , @Referenced_Depth INT = 0
 , @Referencing_Depth INT = 0
 )
RETURNS TABLE
AS
RETURN (
  --trees are recursive to get parent child relations
  WITH tree_referenced AS (
    SELECT [FirstNode].*
     , 1 AS [Referenced_Depth]
     , 0 AS [Referencing_Depth]
    FROM graph.RepoObject_ReferencingReferenced AS FirstNode
    WHERE [Referencing_guid] = @RepoObject_guid
     AND 1 <= @Referenced_Depth
    
    UNION ALL
    
    SELECT [child].*
     , [Referenced_Depth] = [parent].[Referenced_Depth] + 1
     , 0
    FROM graph.RepoObject_ReferencingReferenced_u_v AS child
    INNER JOIN tree_referenced AS parent
     ON [child].Referencing_guid = [parent].Referenced_guid
    WHERE [parent].[Referenced_Depth] < @Referenced_Depth
    )
   , tree_referencing AS (
    SELECT [FirstNode].*
     , 0 AS [Referenced_Depth]
     , 1 AS [Referencing_Depth]
    FROM graph.RepoObject_ReferencingReferenced AS FirstNode
    WHERE [Referenced_guid] = @RepoObject_guid
     AND 1 <= @Referencing_Depth
    
    UNION ALL
    
    SELECT [child].*
     , 0
     , [Referencing_Depth] = [parent].[Referencing_Depth] + 1
    FROM graph.RepoObject_ReferencingReferenced_u_v AS child
    INNER JOIN tree_referencing AS parent
     ON [child].Referenced_guid = [parent].Referencing_guid
    WHERE [parent].[Referencing_Depth] < @Referencing_Depth
    )
  SELECT *
   , @RepoObject_guid AS RepoObject_guid
  FROM tree_referenced
  
  UNION
  
  SELECT *
   , @RepoObject_guid AS RepoObject_guid
  FROM tree_referencing
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_RepoObject_ReferenceTree_via_fullname

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObject_fullname | NVARCHAR(261) | no |  |
| @Referenced_Depth | INT | no |  |
| @Referencing_Depth | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
--Duplicates are possible, if exists alternative path between objects with different depth
--to elimenate them, exclude Referenced_Depth and Referencing_Depth and use DISTINCT


DECLARE @RepoObject_fullname NVARCHAR(261)

SET @RepoObject_fullname = '[repo].[RepoObject_gross]'

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree_via_fullname](@RepoObject_fullname, DEFAULT, DEFAULT)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree_via_fullname](@RepoObject_fullname, 0, 6)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree_via_fullname](@RepoObject_fullname, 0, 6)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObject_ReferenceTree_via_fullname](@RepoObject_fullname, 100, 100)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]


*/
CREATE FUNCTION [repo].[ftv_RepoObject_ReferenceTree_via_fullname] (
 @RepoObject_fullname NVARCHAR(261)
 , @Referenced_Depth INT = 0
 , @Referencing_Depth INT = 0
 )
RETURNS TABLE
AS
RETURN (
  --trees are recursive to get parent child relations
  WITH tree_referenced AS (
    SELECT [FirstNode].*
     , 1 AS [Referenced_Depth]
     , 0 AS [Referencing_Depth]
    FROM graph.RepoObject_ReferencingReferenced AS FirstNode
    WHERE [Referencing_fullname] = @RepoObject_fullname
     AND 1 <= @Referenced_Depth
    
    UNION ALL
    
    SELECT [child].*
     , [Referenced_Depth] = [parent].[Referenced_Depth] + 1
     , 0
    FROM graph.RepoObject_ReferencingReferenced_u_v AS child
    INNER JOIN tree_referenced AS parent
     ON [child].Referencing_guid = [parent].Referenced_guid
    WHERE [parent].[Referenced_Depth] < @Referenced_Depth
    )
   , tree_referencing AS (
    SELECT [FirstNode].*
     , 0 AS [Referenced_Depth]
     , 1 AS [Referencing_Depth]
    FROM graph.RepoObject_ReferencingReferenced AS FirstNode
    WHERE [Referenced_fullname] = @RepoObject_fullname
     AND 1 <= @Referencing_Depth
    
    UNION ALL
    
    SELECT [child].*
     , 0
     , [Referencing_Depth] = [parent].[Referencing_Depth] + 1
    FROM graph.RepoObject_ReferencingReferenced_u_v AS child
    INNER JOIN tree_referencing AS parent
     ON [child].Referenced_guid = [parent].Referencing_guid
    WHERE [parent].[Referencing_Depth] < @Referencing_Depth
    )
  SELECT *
   , @RepoObject_fullname AS RepoObject_fullname
  FROM tree_referenced
  
  UNION
  
  SELECT *
   , @RepoObject_fullname AS RepoObject_fullname
  FROM tree_referencing
  )

```

</details>

[Back to top](#dhw_self)

### repo.ftv_RepoObjectColumn_ReferenceTree

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @RepoObjectColumn_guid | UNIQUEIDENTIFIER | no |  |
| @Referenced_Depth | INT | no |  |
| @Referencing_Depth | INT | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
--Duplicates are possible, if exists alternative path between objects with different depth
--to elimenate them, exclude Referenced_Depth and Referencing_Depth and use DISTINCT


DECLARE @RepoObjectColumn_guid uniqueidentifier

SET @RepoObjectColumn_guid = (SELECT RepoObjectColumn_guid from [repo].[RepoObjectColumn_gross] where RepoObjectColumn_fullname = '[repo].[RepoObjectColumn_gross].[RepoObjectColumn_guid]')

SELECT *
FROM [repo].[ftv_RepoObjectColumn_ReferenceTree](@RepoObjectColumn_guid, DEFAULT, DEFAULT)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObjectColumn_ReferenceTree](@RepoObjectColumn_guid, 1, 1)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObjectColumn_ReferenceTree](@RepoObjectColumn_guid, 0, 6)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]

SELECT *
FROM [repo].[ftv_RepoObjectColumn_ReferenceTree](@RepoObjectColumn_guid, 100, 100)
ORDER BY [Referenced_Depth]
 , [Referencing_Depth]


*/
CREATE FUNCTION [repo].[ftv_RepoObjectColumn_ReferenceTree] (
 @RepoObjectColumn_guid uniqueidentifier
 , @Referenced_Depth INT = 0
 , @Referencing_Depth INT = 0
 )
RETURNS TABLE
AS
RETURN (
  --trees are recursive to get parent child relations
  WITH tree_referenced AS (
    SELECT [FirstNode].*
     , 1 AS [Referenced_Depth]
     , 0 AS [Referencing_Depth]
    FROM graph.RepoObjectColumn_ReferencingReferenced AS FirstNode
    WHERE [Referencing_guid] = @RepoObjectColumn_guid
     AND 1 <= @Referenced_Depth
    
    UNION ALL
    
    SELECT [child].*
     , [Referenced_Depth] = [parent].[Referenced_Depth] + 1
     , 0
    FROM graph.RepoObjectColumn_ReferencingReferenced AS child
    INNER JOIN tree_referenced AS parent
     ON [child].Referencing_guid = [parent].Referenced_guid
    WHERE [parent].[Referenced_Depth] < @Referenced_Depth
    )
   , tree_referencing AS (
    SELECT [FirstNode].*
     , 0 AS [Referenced_Depth]
     , 1 AS [Referencing_Depth]
    FROM graph.RepoObjectColumn_ReferencingReferenced AS FirstNode
    WHERE [Referenced_guid] = @RepoObjectColumn_guid
     AND 1 <= @Referencing_Depth
    
    UNION ALL
    
    SELECT [child].*
     , 0
     , [Referencing_Depth] = [parent].[Referencing_Depth] + 1
    FROM graph.RepoObjectColumn_ReferencingReferenced AS child
    INNER JOIN tree_referencing AS parent
     ON [child].Referenced_guid = [parent].Referencing_guid
    WHERE [parent].[Referencing_Depth] < @Referencing_Depth
    )
  SELECT *
   , @RepoObjectColumn_guid AS RepoObjectColumn_guid
  FROM tree_referenced
  
  UNION
  
  SELECT *
   , @RepoObjectColumn_guid AS RepoObjectColumn_guid
  FROM tree_referencing
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_sqlparse

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @json_array | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
-- Alter Function ftv_sqlparse
CREATE FUNCTION [repo].[ftv_sqlparse] (@json_array NVARCHAR(MAX))
RETURNS TABLE
AS
RETURN (
  SELECT j1.[key] AS json_key
   , j2.*
  FROM OPENJSON(@json_array) j1
  CROSS APPLY OPENJSON(j1.[value]) WITH (
    class NVARCHAR(500) N'$.class'
    , is_group BIT N'$.is_group'
    , is_keyword BIT N'$.is_keyword'
    , is_whitespace BIT N'$.is_whitespace'
    , normalized NVARCHAR(MAX) N'$.normalized'
    , children NVARCHAR(MAX) N'$.children' AS JSON
    ----get values of some children
    ----children[0] is the first children
    --,child0_class nvarchar(500) N'$.children[0].class'
    --,child0_is_group bit N'$.children[0].is_group'
    --,child0_is_keyword bit N'$.children[0].is_keyword'
    --,child0_is_whitespace bit N'$.children[0].is_whitespace'
    --,child0_normalized nvarchar(MAX) N'$.children[0].normalized'
    --,child0_children nvarchar(MAX) N'$.children[0].children' AS JSON
    --,child1_class nvarchar(500) N'$.children[1].class'
    --,child1_is_group bit N'$.children[1].is_group'
    --,child1_is_keyword bit N'$.children[1].is_keyword'
    --,child1_is_whitespace bit N'$.children[1].is_whitespace'
    --,child1_normalized nvarchar(MAX) N'$.children[1].normalized'
    --,child1_children nvarchar(MAX) N'$.children[1].children' AS JSON
    ) j2
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_sqlparse_children_pivot

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @json_array | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
--test

declare @json_array nvarchar(max)
set @json_array =
'
[{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "[T1]", "normalized": "[T1]", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "[Active]", "normalized": "[Active]", "is_keyword": false, "is_whitespace": false, "children": []}]
'

SELECT * from [repo].[ftv_sqlparse_children_pivot](@json_array)

*/
CREATE FUNCTION [repo].[ftv_sqlparse_children_pivot] (@json_array NVARCHAR(MAX))
RETURNS TABLE
AS
RETURN (
  SELECT [child0_class] = JSON_VALUE(@json_array, '$[0].class')
   , [child0_is_group] = JSON_VALUE(@json_array, '$[0].is_group')
   , [child0_is_keyword] = JSON_VALUE(@json_array, '$[0].is_keyword')
   , [child0_normalized] = JSON_VALUE(@json_array, '$[0].normalized')
   , [child0_children] = JSON_VALUE(@json_array, '$[0].children')
   , [child1_class] = JSON_VALUE(@json_array, '$[1].class')
   , [child1_is_group] = JSON_VALUE(@json_array, '$[1].is_group')
   , [child1_is_keyword] = JSON_VALUE(@json_array, '$[1].is_keyword')
   , [child1_normalized] = JSON_VALUE(@json_array, '$[1].normalized')
   , [child1_children] = JSON_VALUE(@json_array, '$[1].children')
   , [child2_class] = JSON_VALUE(@json_array, '$[2].class')
   , [child2_is_group] = JSON_VALUE(@json_array, '$[2].is_group')
   , [child2_is_keyword] = JSON_VALUE(@json_array, '$[2].is_keyword')
   , [child2_normalized] = JSON_VALUE(@json_array, '$[2].normalized')
   , [child2_children] = JSON_VALUE(@json_array, '$[2].children')
   , [child3_class] = JSON_VALUE(@json_array, '$[3].class')
   , [child3_is_group] = JSON_VALUE(@json_array, '$[3].is_group')
   , [child3_is_keyword] = JSON_VALUE(@json_array, '$[3].is_keyword')
   , [child3_normalized] = JSON_VALUE(@json_array, '$[3].normalized')
   , [child3_children] = JSON_VALUE(@json_array, '$[3].children')
   , [child4_class] = JSON_VALUE(@json_array, '$[4].class')
   , [child4_is_group] = JSON_VALUE(@json_array, '$[4].is_group')
   , [child4_is_keyword] = JSON_VALUE(@json_array, '$[4].is_keyword')
   , [child4_normalized] = JSON_VALUE(@json_array, '$[4].normalized')
   , [child4_children] = JSON_VALUE(@json_array, '$[4].children')
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_sqlparse_IdentifierList__TestOnly

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @jsonstr | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
/*
soure

SELECT
       [T1].[RepoObject_guid]
     , [T1].[key]
     , [T1].[SysObject_fullname]
     , [T1].[RowNumber_per_Object]
     , [T1].[class]
       --, [T1].[is_group]
       --, [T1].[is_keyword]
       --, [T1].[is_whitespace]
     , [T1].[normalized]
       --, [T1].[children]
     , [T2_class] = [T2].[class]
     , [Identifier_alias] = CASE [T2].[class]
                                WHEN 'Identifier'
                                THEN CASE
                                         WHEN [T2].[child1_normalized] = 'AS'
                                         THEN [T2].[child2_normalized]
                                         WHEN [T2].[child3_normalized] = 'AS'
                                         THEN [T2].[child4_normalized]
                                     END
                                WHEN 'Comparison'
                                THEN CASE
                                         WHEN [T2].[child1_normalized] = '='
                                         THEN [T2].[child0_normalized]
                                     END
                            END
     , [Identifier_source] = CASE [T2].[class]
                                 WHEN 'Identifier'
                                 THEN CASE [T2].[child0_class]
                                          WHEN 'Token'
                                          THEN [T2].[normalized]
                                          WHEN 'Function'
                                          THEN [T2].[child0_normalized]
                                      END
                                 WHEN 'Comparison'
                                 THEN CASE
                                          WHEN [T2].[child1_normalized] = '='
                                          THEN [T2].[child2_normalized]
                                      END
                             END
     , [Identifier_source_class] = CASE [T2].[class]
                                       WHEN 'Identifier'
                                       THEN CASE [T2].[child0_class]
                                                WHEN 'Token'
                                                THEN [T2].[class]
                                                WHEN 'Function'
                                                THEN [T2].[child0_class]
                                            END
                                       WHEN 'Comparison'
                                       THEN CASE
                                                WHEN [T2].[child1_normalized] = '='
                                                THEN [T2].[child2_class]
                                            END
                                   END
     , [Identifier_source_children] = CASE [T2].[class]
                                          WHEN 'Identifier'
                                          THEN CASE [T2].[child0_class]
                                                   WHEN 'Token'
                                                   THEN [T2].[children]
                                                   WHEN 'Function'
                                                   THEN [T2].[child0_children]
                                               END
                                          WHEN 'Comparison'
                                          THEN CASE
                                                   WHEN [T2].[child1_normalized] = '='
                                                   THEN [T2].[child2_children]
                                               END
                                      END
     , [T2].[json_key]
     , [T2].[is_group]
     , [T2].[is_keyword]
     , [T2].[is_whitespace]
     , [T2].[normalized]
     , [T2].[children]
     , [T2].[child0_class]
     , [T2].[child0_is_group]
     , [T2].[child0_is_keyword]
     , [T2].[child0_is_whitespace]
     , [T2].[child0_normalized]
     , [T2].[child0_children]
     , [T2].[child1_class]
     , [T2].[child1_is_group]
     , [T2].[child1_is_keyword]
     , [T2].[child1_is_whitespace]
     , [T2].[child1_normalized]
     , [T2].[child1_children]
     , [T2].[child2_class]
     , [T2].[child2_is_group]
     , [T2].[child2_is_keyword]
     , [T2].[child2_is_whitespace]
     , [T2].[child2_normalized]
     , [T2].[child2_children]
     , [T2].[child3_class]
     , [T2].[child3_is_group]
     , [T2].[child3_is_keyword]
     , [T2].[child3_is_whitespace]
     , [T2].[child3_normalized]
     , [T2].[child3_children]
     , [T2].[child4_class]
     , [T2].[child4_is_group]
     , [T2].[child4_is_keyword]
     , [T2].[child4_is_whitespace]
     , [T2].[child4_normalized]
     , [T2].[child4_children]
FROM
     [repo].[RepoObject__sql_modules_20_statement_children] AS T1
     CROSS APPLY
     [repo].[ftv_sqlparse_with_some_children](T1.children) AS T2
WHERE  [T1].[class] = 'IdentifierList'
       AND [T2].[class] IN
                           (
                           'Identifier' , 'Comparison'
                           )



test:

declare @jsonstr nvarchar(max)
set @jsonstr =
'
[{"class": "Identifier", "ttype": null, "is_group": true, "str": "s.SupplierID", "normalized": "s.SupplierID", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "SupplierID", "normalized": "SupplierID", "is_keyword": false, "is_whitespace": false, "children": []}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "s.SupplierName", "normalized": "s.SupplierName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "SupplierName", "normalized": "SupplierName", "is_keyword": false, "is_whitespace": false, "children": []}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "sc.SupplierCategoryName", "normalized": "sc.SupplierCategoryName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "sc", "normalized": "sc", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "SupplierCategoryName", "normalized": "SupplierCategoryName", "is_keyword": false, "is_whitespace": false, "children": []}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "pp.FullName AS PrimaryContact", "normalized": "pp.FullName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "pp", "normalized": "pp", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "FullName", "normalized": "FullName", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Keyword"], "is_group": false, "str": "AS", "normalized": "AS", "is_keyword": true, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "PrimaryContact", "normalized": "PrimaryContact", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "PrimaryContact", "normalized": "PrimaryContact", "is_keyword": false, "is_whitespace": false, "children": []}]}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "ap.FullName AS AlternateContact", "normalized": "ap.FullName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "ap", "normalized": "ap", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "FullName", "normalized": "FullName", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Keyword"], "is_group": false, "str": "AS", "normalized": "AS", "is_keyword": true, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "AlternateContact", "normalized": "AlternateContact", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "AlternateContact", "normalized": "AlternateContact", "is_keyword": false, "is_whitespace": false, "children": []}]}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "s.PhoneNumber", "normalized": "s.PhoneNumber", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "PhoneNumber", "normalized": "PhoneNumber", "is_keyword": false, "is_whitespace": false, "children": []}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "s.FaxNumber", "normalized": "s.FaxNumber", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "FaxNumber", "normalized": "FaxNumber", "is_keyword": false, "is_whitespace": false, "children": []}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "s.WebsiteURL", "normalized": "s.WebsiteURL", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "WebsiteURL", "normalized": "WebsiteURL", "is_keyword": false, "is_whitespace": false, "children": []}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "dm.DeliveryMethodName AS DeliveryMethod", "normalized": "dm.DeliveryMethodName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "dm", "normalized": "dm", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "DeliveryMethodName", "normalized": "DeliveryMethodName", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Keyword"], "is_group": false, "str": "AS", "normalized": "AS", "is_keyword": true, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "DeliveryMethod", "normalized": "DeliveryMethod", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "DeliveryMethod", "normalized": "DeliveryMethod", "is_keyword": false, "is_whitespace": false, "children": []}]}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "c.CityName AS CityName", "normalized": "c.CityName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "c", "normalized": "c", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "CityName", "normalized": "CityName", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Keyword"], "is_group": false, "str": "AS", "normalized": "AS", "is_keyword": true, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "CityName", "normalized": "CityName", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "CityName", "normalized": "CityName", "is_keyword": false, "is_whitespace": false, "children": []}]}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "s.DeliveryLocation AS DeliveryLocation", "normalized": "s.DeliveryLocation", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "DeliveryLocation", "normalized": "DeliveryLocation", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Keyword"], "is_group": false, "str": "AS", "normalized": "AS", "is_keyword": true, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "DeliveryLocation", "normalized": "DeliveryLocation", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "DeliveryLocation", "normalized": "DeliveryLocation", "is_keyword": false, "is_whitespace": false, "children": []}]}]}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ",", "normalized": ",", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Identifier", "ttype": null, "is_group": true, "str": "s.SupplierReference", "normalized": "s.SupplierReference", "is_keyword": false, "is_whitespace": false, "children": [{"class": "Token", "ttype": ["Name"], "is_group": false, "str": "s", "normalized": "s", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Punctuation"], "is_group": false, "str": ".", "normalized": ".", "is_keyword": false, "is_whitespace": false, "children": []}, {"class": "Token", "ttype": ["Name"], "is_group": false, "str": "SupplierReference", "normalized": "SupplierReference", "is_keyword": false, "is_whitespace": false, "children": []}]}]
'
select *
    FROM
         OPENJSON(@jsonstr) AS j1

select * from [repo].[ftv_sqlparse_IdentifierList](@jsonstr)

select *
FROM
     [repo].[RepoObject__sql_modules_20_statement_children] AS T1
     CROSS APPLY
     [repo].[ftv_sqlparse_IdentifierList](T1.children) AS T2
WHERE  [T1].[class] = 'IdentifierList'
and isjson(T1.children) = 1



*/
--@jsonstr should be 'children' element of en entry class IdentifierList
CREATE FUNCTION [repo].[ftv_sqlparse_IdentifierList__TestOnly] (@jsonstr NVARCHAR(MAX))
RETURNS TABLE
AS
RETURN (
  SELECT
   --j1.*
   --,
   --  [T1].[RepoObject_guid]
   --, [T1].[key]
   --, [T1].[SysObject_fullname]
   --, [T1].[RowNumber_per_Object]
   --, [T1].[class]
   --  --, [T1].[is_group]
   --  --, [T1].[is_keyword]
   --  --, [T1].[is_whitespace]
   --, [T1].[normalized]
   --  --, [T1].[children]
   --, 
   [T2_class] = [T2].[class]
   , [Identifier_alias] = CASE [T2].[class]
    WHEN 'Identifier'
     THEN CASE 
       WHEN [T2].[child1_normalized] = 'AS'
        THEN [T2].[child2_normalized]
       WHEN [T2].[child3_normalized] = 'AS'
        THEN [T2].[child4_normalized]
       END
    WHEN 'Comparison'
     THEN CASE 
       WHEN [T2].[child1_normalized] = '='
        THEN [T2].[child0_normalized]
       END
    END
   , [Identifier_source] = CASE [T2].[class]
    WHEN 'Identifier'
     THEN CASE [T2].[child0_class]
       WHEN 'Token'
        THEN [T2].[normalized]
       WHEN 'Function'
        THEN [T2].[child0_normalized]
       END
    WHEN 'Comparison'
     THEN CASE 
       WHEN [T2].[child1_normalized] = '='
        THEN [T2].[child2_normalized]
       END
    END
   , [Identifier_source_class] = CASE [T2].[class]
    WHEN 'Identifier'
     THEN CASE [T2].[child0_class]
       WHEN 'Token'
        THEN [T2].[class]
       WHEN 'Function'
        THEN [T2].[child0_class]
       END
    WHEN 'Comparison'
     THEN CASE 
       WHEN [T2].[child1_normalized] = '='
        THEN [T2].[child2_class]
       END
    END
   , [Identifier_source_children] = CASE [T2].[class]
    WHEN 'Identifier'
     THEN CASE [T2].[child0_class]
       WHEN 'Token'
        THEN [T2].[children]
       WHEN 'Function'
        THEN [T2].[child0_children]
       END
    WHEN 'Comparison'
     THEN CASE 
       WHEN [T2].[child1_normalized] = '='
        THEN [T2].[child2_children]
       END
    END
  --     , [T2].[json_key]
  --     , [T2].[is_group]
  --     , [T2].[is_keyword]
  --     , [T2].[is_whitespace]
  --     , [T2].[normalized]
  --     , [T2].[children]
  --     , [T2].[child0_class]
  --     , [T2].[child0_is_group]
  --     , [T2].[child0_is_keyword]
  --     , [T2].[child0_is_whitespace]
  --     , [T2].[child0_normalized]
  --     , [T2].[child0_children]
  --     , [T2].[child1_class]
  --     , [T2].[child1_is_group]
  --     , [T2].[child1_is_keyword]
  --     , [T2].[child1_is_whitespace]
  --     , [T2].[child1_normalized]
  --     , [T2].[child1_children]
  --     , [T2].[child2_class]
  --     , [T2].[child2_is_group]
  --     , [T2].[child2_is_keyword]
  --     , [T2].[child2_is_whitespace]
  --     , [T2].[child2_normalized]
  --     , [T2].[child2_children]
  --     , [T2].[child3_class]
  --     , [T2].[child3_is_group]
  --     , [T2].[child3_is_keyword]
  --     , [T2].[child3_is_whitespace]
  --     , [T2].[child3_normalized]
  --     , [T2].[child3_children]
  --     , [T2].[child4_class]
  --     , [T2].[child4_is_group]
  --     , [T2].[child4_is_keyword]
  --     , [T2].[child4_is_whitespace]
  --     , [T2].[child4_normalized]
  --     , [T2].[child4_children]
  ----FROM
  ----     [repo].[RepoObject__sql_modules_20_statement_children] AS T1
  FROM --
   --     OPENJSON(@jsonstr) AS j1
   --     CROSS APPLY
   [repo].[ftv_sqlparse_with_some_children](@jsonstr) AS T2
  WHERE [T2].[class] IN (
    'Identifier'
    , 'Comparison'
    )
  )
```

</details>

[Back to top](#dhw_self)

### repo.ftv_sqlparse_with_some_children

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @json_array | NVARCHAR(MAX) | no |  |

#### Definition

<details><summary>Click to expand</summary>

```sql
CREATE FUNCTION [repo].[ftv_sqlparse_with_some_children] (@json_array NVARCHAR(MAX))
RETURNS TABLE
AS
RETURN (
  SELECT j1.[key] AS json_key
   , j2.*
  FROM OPENJSON(@json_array) j1
  CROSS APPLY OPENJSON(j1.[value]) WITH (
    class NVARCHAR(500) N'$.class'
    , is_group BIT N'$.is_group'
    , is_keyword BIT N'$.is_keyword'
    , is_whitespace BIT N'$.is_whitespace'
    , normalized NVARCHAR(MAX) N'$.normalized'
    , children NVARCHAR(MAX) N'$.children' AS JSON
    --get values of some children
    --children[0] is the first children
    , child0_class NVARCHAR(500) N'$.children[0].class'
    , child0_is_group BIT N'$.children[0].is_group'
    , child0_is_keyword BIT N'$.children[0].is_keyword'
    , child0_is_whitespace BIT N'$.children[0].is_whitespace'
    , child0_normalized NVARCHAR(MAX) N'$.children[0].normalized'
    , child0_children NVARCHAR(MAX) N'$.children[0].children' AS JSON
    , child1_class NVARCHAR(500) N'$.children[1].class'
    , child1_is_group BIT N'$.children[1].is_group'
    , child1_is_keyword BIT N'$.children[1].is_keyword'
    , child1_is_whitespace BIT N'$.children[1].is_whitespace'
    , child1_normalized NVARCHAR(MAX) N'$.children[1].normalized'
    , child1_children NVARCHAR(MAX) N'$.children[1].children' AS JSON
    , child2_class NVARCHAR(500) N'$.children[2].class'
    , child2_is_group BIT N'$.children[2].is_group'
    , child2_is_keyword BIT N'$.children[2].is_keyword'
    , child2_is_whitespace BIT N'$.children[2].is_whitespace'
    , child2_normalized NVARCHAR(MAX) N'$.children[2].normalized'
    , child2_children NVARCHAR(MAX) N'$.children[2].children' AS JSON
    , child3_class NVARCHAR(500) N'$.children[3].class'
    , child3_is_group BIT N'$.children[3].is_group'
    , child3_is_keyword BIT N'$.children[3].is_keyword'
    , child3_is_whitespace BIT N'$.children[3].is_whitespace'
    , child3_normalized NVARCHAR(MAX) N'$.children[3].normalized'
    , child3_children NVARCHAR(MAX) N'$.children[3].children' AS JSON
    , child4_class NVARCHAR(500) N'$.children[4].class'
    , child4_is_group BIT N'$.children[4].is_group'
    , child4_is_keyword BIT N'$.children[4].is_keyword'
    , child4_is_whitespace BIT N'$.children[4].is_whitespace'
    , child4_normalized NVARCHAR(MAX) N'$.children[4].normalized'
    , child4_children NVARCHAR(MAX) N'$.children[4].children' AS JSON
    ) j2
  )
```

</details>

[Back to top](#dhw_self)

</details>

## Synonyms

<details><summary>Click to expand</summary>

* [sys_dwh.columns](#sys_dwhcolumns)
* [sys_dwh.computed_columns](#sys_dwhcomputed_columns)
* [sys_dwh.default_constraints](#sys_dwhdefault_constraints)
* [sys_dwh.dm_exec_describe_first_result_set](#sys_dwhdm_exec_describe_first_result_set)
* [sys_dwh.dm_sql_referenced_entities](#sys_dwhdm_sql_referenced_entities)
* [sys_dwh.extended_properties](#sys_dwhextended_properties)
* [sys_dwh.foreign_key_columns](#sys_dwhforeign_key_columns)
* [sys_dwh.foreign_keys](#sys_dwhforeign_keys)
* [sys_dwh.identity_columns](#sys_dwhidentity_columns)
* [sys_dwh.index_columns](#sys_dwhindex_columns)
* [sys_dwh.indexes](#sys_dwhindexes)
* [sys_dwh.objects](#sys_dwhobjects)
* [sys_dwh.parameters](#sys_dwhparameters)
* [sys_dwh.schemas](#sys_dwhschemas)
* [sys_dwh.sp_addextendedproperty](#sys_dwhsp_addextendedproperty)
* [sys_dwh.sp_updateextendedproperty](#sys_dwhsp_updateextendedproperty)
* [sys_dwh.sql_expression_dependencies](#sys_dwhsql_expression_dependencies)
* [sys_dwh.sql_modules](#sys_dwhsql_modules)
* [sys_dwh.tables](#sys_dwhtables)
* [sys_dwh.types](#sys_dwhtypes)

### sys_dwh.columns


| Synonym | Base Object |
| --- | --- |
| sys_dwh.columns | [dhw_self.sys.columns](#sys.columns) |

[Back to top](#dhw_self)

### sys_dwh.computed_columns


| Synonym | Base Object |
| --- | --- |
| sys_dwh.computed_columns | [dhw_self.sys.computed_columns](#sys.computed_columns) |

[Back to top](#dhw_self)

### sys_dwh.default_constraints


| Synonym | Base Object |
| --- | --- |
| sys_dwh.default_constraints | [dhw_self.sys.default_constraints](#sys.default_constraints) |

[Back to top](#dhw_self)

### sys_dwh.dm_exec_describe_first_result_set


| Synonym | Base Object |
| --- | --- |
| sys_dwh.dm_exec_describe_first_result_set | [dhw_self.sys.dm_exec_describe_first_result_set](#sys.dm_exec_describe_first_result_set) |

[Back to top](#dhw_self)

### sys_dwh.dm_sql_referenced_entities


| Synonym | Base Object |
| --- | --- |
| sys_dwh.dm_sql_referenced_entities | [dhw_self.sys.dm_sql_referenced_entities](#sys.dm_sql_referenced_entities) |

[Back to top](#dhw_self)

### sys_dwh.extended_properties


| Synonym | Base Object |
| --- | --- |
| sys_dwh.extended_properties | [dhw_self.sys.extended_properties](#sys.extended_properties) |

[Back to top](#dhw_self)

### sys_dwh.foreign_key_columns


| Synonym | Base Object |
| --- | --- |
| sys_dwh.foreign_key_columns | [dhw_self.sys.foreign_key_columns](#sys.foreign_key_columns) |

[Back to top](#dhw_self)

### sys_dwh.foreign_keys


| Synonym | Base Object |
| --- | --- |
| sys_dwh.foreign_keys | [dhw_self.sys.foreign_keys](#sys.foreign_keys) |

[Back to top](#dhw_self)

### sys_dwh.identity_columns


| Synonym | Base Object |
| --- | --- |
| sys_dwh.identity_columns | [dhw_self.sys.identity_columns](#sys.identity_columns) |

[Back to top](#dhw_self)

### sys_dwh.index_columns


| Synonym | Base Object |
| --- | --- |
| sys_dwh.index_columns | [dhw_self.sys.index_columns](#sys.index_columns) |

[Back to top](#dhw_self)

### sys_dwh.indexes


| Synonym | Base Object |
| --- | --- |
| sys_dwh.indexes | [dhw_self.sys.indexes](#sys.indexes) |

[Back to top](#dhw_self)

### sys_dwh.objects


| Synonym | Base Object |
| --- | --- |
| sys_dwh.objects | [dhw_self.sys.objects](#sys.objects) |

[Back to top](#dhw_self)

### sys_dwh.parameters


| Synonym | Base Object |
| --- | --- |
| sys_dwh.parameters | [dhw_self.sys.parameters](#sys.parameters) |

[Back to top](#dhw_self)

### sys_dwh.schemas


| Synonym | Base Object |
| --- | --- |
| sys_dwh.schemas | [dhw_self.sys.schemas](#sys.schemas) |

[Back to top](#dhw_self)

### sys_dwh.sp_addextendedproperty


| Synonym | Base Object |
| --- | --- |
| sys_dwh.sp_addextendedproperty | dhw_selfsp_addextendedproperty |

[Back to top](#dhw_self)

### sys_dwh.sp_updateextendedproperty


| Synonym | Base Object |
| --- | --- |
| sys_dwh.sp_updateextendedproperty | dhw_selfsp_updateextendedproperty |

[Back to top](#dhw_self)

### sys_dwh.sql_expression_dependencies


| Synonym | Base Object |
| --- | --- |
| sys_dwh.sql_expression_dependencies | [dhw_self.sys.sql_expression_dependencies](#sys.sql_expression_dependencies) |

[Back to top](#dhw_self)

### sys_dwh.sql_modules


| Synonym | Base Object |
| --- | --- |
| sys_dwh.sql_modules | [dhw_self.sys.sql_modules](#sys.sql_modules) |

[Back to top](#dhw_self)

### sys_dwh.tables


| Synonym | Base Object |
| --- | --- |
| sys_dwh.tables | [dhw_self.sys.tables](#sys.tables) |

[Back to top](#dhw_self)

### sys_dwh.types


| Synonym | Base Object |
| --- | --- |
| sys_dwh.types | [dhw_self.sys.types](#sys.types) |

[Back to top](#dhw_self)

</details>

----

*Markdown generated by [sp_doc](https://dba-multitool.org)
 at 2021-03-12 18:34:46.5829966 +01:00.*
