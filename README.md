# SOD IMPLEMENTACIÓN AWS TRANSFR FOR SFTP
## Prerrequisitos
1.	S3 Bucket - BucketName ( Por ej :: sftp.dest.testbkt)
o	Deberá crear su propio depósito y usar ese nombre en las instrucciones
2.	Cliente SFTP
o	Preferiblemente, una máquina Linux como cliente sftp está disponible por defecto.
3.	Función de IAM para usuarios de SFTP
o	Permisos - AmazonS3FullAccess
## Cree el servidor SFTP
Básicamente, puede tener su punto final personalizado con su nombre de dominio o puede usar el punto final predeterminado.
### Configurar usuarios
Necesitará un par de claves SSH y cargará la clave pública que el usuario utilizará cuando se conecte al servidor SFTP.
Crear par de claves SSH
Desde el servidor linux puede hacer esto (puede hacer lo mismo en Windows usando putty-gen).
> ssh-keygen -P " " -f " sftp-test-key "

Copie la clave pública a la configuración del usuario y guárdela. Nota: La clave pública no debe ser de varias líneas (o) tener caracteres especiales como enter.
### Conectarse al servidor SFTP
> sftp -i sftp-test-key testuser @ YOUR-SFTP-END-POINT # Para listar archivos > ls # Para cargar archivos > mput YOUR-FILE-NAME > ls



