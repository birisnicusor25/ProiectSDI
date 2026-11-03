# ProiectSDI

Proiect realizat în cadrul disciplinei **Sisteme Distribuite**.

## Autor

- Biris Nicolae

## Descriere

ProiectSDI reprezintă implementarea unui sistem distribuit de stocare a fișierelor folosind Java.

Sistemul este format din mai multe noduri de stocare și un client care permite gestionarea fișierelor distribuite în rețea.

### Operații suportate

- `put` - încărcarea unui fișier
- `get` - descărcarea unui fișier
- `ls` - listarea fișierelor disponibile
- `rm` - ștergerea unui fișier
- `nodes` - afișarea nodurilor active

## Structura proiectului

```text
ProiectSDI
├── README.md
├── pom.xml
├── docs
│   └── cerinte.md
├── scripts
│   └── start-local.sh
├── src
│   └── main
│       └── java
│           └── ro
│               └── ubm
│                   └── sd
│                       ├── client
│                       │   └── Client.java
│                       ├── node
│                       │   └── StorageNode.java
│                       └── common
└── data
```

## Tehnologii utilizate

- Java 17
- Maven
- Git
- GitHub
- TCP Sockets
- UDP Multicast

## Cerințe software

- JDK 17+
- Maven 3.8+
- Git

Verificare:

```bash
java -version
mvn -version
git --version
```

## Compilare

```bash
mvn clean package
```

## Pornirea nodurilor

### Nod coordonator

```bash
java -cp target/classes ro.ubm.sd.node.StorageNode --id n1 --port 7001 --dir data/n1 --coordinator
```

### Nod de stocare 2

```bash
java -cp target/classes ro.ubm.sd.node.StorageNode --id n2 --port 7002 --dir data/n2
```

### Nod de stocare 3

```bash
java -cp target/classes ro.ubm.sd.node.StorageNode --id n3 --port 7003 --dir data/n3
```

## Pornirea clientului

```bash
java -cp target/classes ro.ubm.sd.client.Client --coordinator localhost:7001
```

## Comenzi disponibile

```text
put <fisier>
get <fisier>
ls
rm <fisier>
nodes
exit
```

## Stadiul proiectului

- ✅ Etapa 1 - Analiza cerințelor și realizarea scheletului aplicației
-  Implementarea comunicației intre noduri
-  Replicarea fisierelor
-  Detectarea defectarii nodurilor
-  Alegerea coordonatorului
-  Testare finala
