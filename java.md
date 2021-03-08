# Java things

[Descargar Oracle JDBC con Maven](https://blogs.oracle.com/dev2dev/get-oracle-jdbc-drivers-and-ucp-from-oracle-maven-repository-without-ides)

Mapstruct Eclipse/Maven Support: [link](https://mapstruct.org/documentation/ide-support/)
- Instalar Plugin eclipse [m2e-apt](https://marketplace.eclipse.org/content/m2e-apt)
- Ir a Window > Preferences > Maven > Annotation Processing y seleccionar el de eclipse
- Agregar ´´´<m2e.apt.activation>jdt_apt</m2e.apt.activation>´´´ a las <properties> del POM.xml del proyecto.