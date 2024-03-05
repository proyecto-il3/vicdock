# Dockerfile para Oracle Database 19c

# Utilizando la imagen de Oracle Linux 7 como base
# FROM oraclelinux:7-slim
FROM container-registry.oracle.com/database/enterprise:19.3.0.0

# Etiqueta de mantenimiento
LABEL maintainer="Victor Bondaruk. https://github.com/victorbondaruk victorbondaruk@gmail.com"

# Variables de entorno para configurar la base de datos
ENV ORACLE_BASE=/opt/oracle \
    ORACLE_HOME=/opt/oracle/product/19c/dbhome_1 \
    ORACLE_SID=ORCL \
    ORACLE_PDB=PDB1 \
    PATH=$ORACLE_HOME/bin:$PATH \
    LD_LIBRARY_PATH=$ORACLE_HOME/lib:/lib:/usr/lib \
    ORACLE_CHARACTERSET=AL32UTF8 \
    ORACLE_EDITION=EE \
    DBCA_TOTAL_MEMORY=2048 \
    ORACLE_ALLOW_REMOTE=true \
    ORACLE_PWD=Password$123

# Crear directorio para la base de datos
# RUN mkdir -p $ORACLE_BASE && \
#     yum install -y oracle-database-preinstall-19c && \
#     rm -rf /var/cache/yum

# Copiar el archivo de respuesta de instalación
# COPY db_install.rsp $ORACLE_BASE/db_install.rsp

# Copiar el archivo de respuesta de creación de base de datos
# COPY dbca.rsp $ORACLE_BASE/dbca.rsp

# Copiar el script de inicio de la base de datos
# COPY start.sh /start.sh

# Dar permisos de ejecución al script de inicio
# RUN chmod +x /start.sh

# Configurar la base de datos
# RUN yum -y install oracle-database-ee-19c && \
#     $ORACLE_HOME/bin/dbca -silent -createDatabase -responseFile $ORACLE_BASE/dbca.rsp

# Exponer puertos
EXPOSE 1521 5500 8080

# Establecer CMD si es necesario
CMD ["true"]
# Ejecutar script de inicio
# CMD ["/start.sh"]