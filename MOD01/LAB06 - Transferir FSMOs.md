## Transfer FSMO

## Validar posicionamento das FSMOs - OPÇÃO01:
```netdom query fsmo```

 

## registrar active directory schema
```regsvr32 schmmgmt.dll ```


## Validando FSMOs - OPÇÃO02

```Get-ADDomain | fl PDCEmulator,RIDMaster,InfrastructureMaster```

```Get-ADForest | fl SchemaMaster,DomainNamingMaster```


## Transferir FSMOs de domínio:
```Move-ADDirectoryServerOperationMasterRole "vm-ad" -OperationMasterRole PDCEmulator```

```Move-ADDirectoryServerOperationMasterRole "vm-ad" -OperationMasterRole RIDMaster```

```Move-ADDirectoryServerOperationMasterRole "vm-ad" -OperationMasterRole InfrastructureMaster```

 

## ransferir FSMOs de infraestrutura:
```Move-ADDirectoryServerOperationMasterRole "vm-ad" -OperationMasterRole SchemaMaster```

```Move-ADDirectoryServerOperationMasterRole "vm-ad" -OperationMasterRole DomainNamingMaster```

 

## Transferir todas FSMOs:
```Move-ADDirectoryServerOperationMasterRole "vm-adds01" -OperationMasterRole PDCEmulator,RIDMaster,InfrastructureMaster,SchemaMaster,DomainNamingMaster```

 

## Seize FSMOs:
``` Move-ADDirectoryServerOperationMasterRole "vm-adds01" -OperationMasterRole PDCEmulator,RIDMaster,InfrastructureMaster,SchemaMaster,DomainNamingMaster -Force ```


## Transferindo FSMOs com NTDSUtil:
Type ntdsutil and press Enter.  
Type roles and press Enter.  
Type connections and press Enter.  
Type connect to server DC01 and press Enter, where DC01 is the server computer name that will transfer the FSMO roles to.  


## Modo grafico :

## Para as 3 funcoes de dominio (RID - PDC - INFRASTRUCTURE)
* Abra a console de Active directory users and computers
* Clique com o botao direito sob o nome do dominio
* Selecione Operations Masters

## Domain naming master
* Abra a console Active Directory domains and trusts
* Clique com o botao direito sob o nome da console
* Selecion operations Masters

## Schema
* Habilitar a console, use powershell como administrador  :  regsvr32 schmmgmt.dll 
* Abra a console pelo snap-in usando o mmc.exe  (Active directory Schema)
* Clique com o botao direito sob o nome do dominio
* Selecione Operations Masters