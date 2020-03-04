# implementacionS3
comandos de AWS .

Para crear un sistema de archivos, use el create-file-systemcomando CLI de Amazon EFS (la operación correspondiente es CreateFileSystem ), como se muestra a continuación.

$ aws efs create-file-system \
--creation-token creation-token \
--performance-mode generalPurpose \
--throughput-mode bursting \
--region aws-region \
--tags Key=key,Value=value Key=key1,Value=value1 \
--profile adminuser
Por ejemplo, el siguiente create-file-systemcomando crea un sistema de archivos en la us-west-2  región de AWS. El comando especifica MyFirstFScomo token de creación. Para obtener una lista de las regiones de AWS donde puede crear un sistema de archivos Amazon EFS, consulte la Referencia general de Amazon Web Services .

$  aws efs create-file-system \
--creation-token MyFirstFS \
--performance-mode generalPurpose \
--throughput-mode bursting \
--region us-west-2 \
--tags Key=Name,Value="Test File System" Key=developer,Value=rhoward \
--profile adminuser
Después de crear con éxito el sistema de archivos, Amazon EFS devuelve la descripción del sistema de archivos como JSON, como se muestra en el siguiente ejemplo.

{
    "OwnerID": "123456789abcd",
    "CreationToken": "MyFirstFS",
    "FileSystemId": "fs-c7a0456e",
    "CreationTime": 1422823614.0,
    "LifeCycleState": "creating",
    "Name": "Test File System",
    "NumberOfMountTargets": 0,
    "SizeInBytes": {
        "Value": 6144,
        "ValueInIA": 0,
        "ValueInStandard": 6144
    },
    "PerformanceMode": "generalPurpose",
    "ThroughputMode": "bursting",
    "Tags": [ 
      { 
         "Key": "Name",
         "Value": "Test File System"
      },
      {
         "Key": "developer",
         "Value": "rhoward"
      }
   ]
}
Amazon EFS también proporciona el describe-file-systemscomando CLI (la operación API correspondiente es DescribeFileSystems ) que puede usar para recuperar una lista de sistemas de archivos en su cuenta, como se muestra a continuación:

$  aws efs describe-file-systems \
--region aws-region \
--profile adminuser
Amazon EFS devuelve una lista de los sistemas de archivos en su cuenta de AWS creada en la región especificada.
