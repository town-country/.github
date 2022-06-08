# Town & Country

## Repository format

The repositories starts with a abbreviation which defines what is inside of the repository.

| abbreviation | explanation     |
| --- | ------------------------ |
| F   | Frontend                 |
| A   | Application Layer        |
| D   | Domain Layer             |
| I   | Infrastructure Layer     |
| S   | Service                  |
| R   | Rules Data               |
| M   | Model ( Protobuffers )   |
| L   | Library                  |
| SDK | Software development kit |
| E   | Environment              |
| T   | Template                 |

## Repositories

| name | explanation     |
| --- | ------------------------ |
| [F-Business-Central](https://github.com/town-country/F-Business-Central) | User Interface to maintain Rules |
| [F-Storybook](https://github.com/town-country/F-Storybook) | Encapsulates Design System |
| [F-Building-Planner](https://github.com/town-country/F-Building-Planner) | User Interface (Revit-Plugin) for Planner |
| [F-House-Planner](https://github.com/town-country/F-House-Planner) | User Interface to configure Houses |
| [F-Revit-Toolkit](https://github.com/town-country/F-Revit-Toolkit) | User Interface (Revit-Plugin) to export Platform Parameters |
| [F-Kafka-UI](https://github.com/town-country/F-Kafka-UI) | User Interface for Apache Kafka |
| [F-Tecronomicon](https://github.com/town-country/F-Tecronomicon) | User Interface for Development Guidelines |
| [A-Building-Planner](https://github.com/town-country/A-Building-Planner) | Application Layer from the Building Context |
| [I-Building](https://github.com/town-country/I-Building) | Infrastructure layer for the Building Context |
| [SDK-Building](https://github.com/town-country/SDK-Building) | SDK to communicate with the Building Context |
| [SDK-Revit](https://github.com/town-country/SDK-Revit) | SDK to communicate with Revit |
| [S-MySQL](https://github.com/town-country/S-MySQL) | MySQL Database |
| [S-Kafka](https://github.com/town-country/S-Kafka) | Apache Kafka |
| [L-Kafka-Connector](https://github.com/town-country/L-Kafka-Connector) | Library that allows to connect to Apache Kafka, and handle subscriptions via attributes |
| [S-Kie-Server](https://github.com/town-country/S-Kie-Server) | KIE Server |
| [S-Zookeeper](https://github.com/town-country/S-Zookeeper) | Apache Kafka Zookeeper |
| [S-OP-Connect-Api](https://github.com/town-country/S-OP-Connect-Api) | One Password Connector |
| [SDK-Infrastructure-Building](https://github.com/town-country/SDK-Infrastructure-Building) | SDk for the infrastructure layer of the building domain |
| [R-Architectural-Construction](https://github.com/town-country/R-Architectural-Construction) | Architectural Construction Rules |
| [E-Building](https://github.com/town-country/E-Building) | Local Environment for Building Context |
| [T-Infrastrucure](https://github.com/town-country/T-Infrastructure) | Template for Infrastructure Layer |
| [T-SDK-Domain](https://github.com/town-country/T-SDK-Domain) | Template for SDK to communicate with the domain layer  |
| [T-SDK-Infrastructure](https://github.com/town-country/T-SDK-Infrastrucure) | Template for SDK to communicate with the infrastructure layer |
| [T-Domain](https://github.com/town-country/T-Domain) | Template for Domain Layer |
| [T-Application](https://github.com/town-country/T-Application) | Template for Application Layer |
| [T-Environment](https://github.com/town-country/T-Application) | Template for local Environment |
| [T-Frontend-React](https://github.com/town-country/T-Frontend-React) | Template for React Frontend |


## Guidelines

### Repository Anlegen / Create Repository

Repositories können als Teil einer Organisation im Gitea angelegt werden:

Erkunden→ Organisation→Organisation auswählen→ Repository anlegen



You can create Repositories as a part of an Organisation in Gitea: 

Erkunden→ Organisation→Organisation auswählen→ Repository anlegen



### Repository klonen / Clone Repository

Nachdem du ein Repository angelegt hast musst du dir eine lokale Kopie des Repositories auf deinem Arbeitslaptop erstellen. Alle Änderungen die du vornimmst befinden sich nur auf deinem Laptop, bis du sie ins gitea hochlädst (push).

After creating a repository in gitea you need to fetch the repository to your local working machine. After that, all changes you made are only on your local machine until you push it to the gitea web instance.



git clone https://tcnet.towncountry.de/git/{{organization}}/{{project_name}}.git



### Branch erzeugen / Create Branch

Am Anfang befindet man sich auf dem master branch. Es ist nicht empfohlen gemeinsam auf diesem Branch  zu arbeiten, da man alle Änderungen, die von deinen Mitarbeitern gemacht werden, zunächst runterladen und zusammenfügen muss, bevor man seine eigenen Änderungen hochladen kann. Dies kann sehr frustrierend sein und kostet viel Zeit. Daher ist es besser für einzelne Features einen eigenen Branch zu erstellen.

In the beginning there are only the master branch. It is not recommended working on this branch all together, because you need to pull and merge all changes of your coworkers made in this repository before you can push your changes. This is really annoying and waste time. It is better to create your own branch for the feature you implement currently.



git checkout -b feature/{{feature_name}}



### Änderungen hinzufügen / Add Changes

Es gibt 3 verschiedene Bereiche in denen sich deine Änderungen befinden können:

Lokal auf deinem Rechner außerhalb des Git Prozesses
Im Index Bereich nachdem du deine Änderungen hinzugefügt hast
Im HEAD nachdem du deine Änderungen mit einem Commit zusammgefasst hast
Bevor du deine Änderungen comitten kannst, musst du sie zunächst zum Index hinzufügen.



There are 3 instances where your code changes are:

- On your local machine outside the git process
- in the Index ( the place after you add your changes )
- in the HEAD ( after you commit your changes locally )

To make a commit you need to add the changes you want to commit to the index.


git add {{folder_name||file_name||*}}


### Änderungen zusammenfassen / Commit Changes

Alle Änderungen am Repository sollten in kleinen Schritten erfolgen, dies macht es einfacher commits zu finden die möglicherweise Bugs enthalten. Auf der anderen Seite ist es einfacher für deine Mitarbeiter die Schritte deiner Arbeit zu reproduzieren. Alle Dateien die du zunächst mit git add {{ ... }} hinzugefügt hast, sind Teil deines Commits. Bitte achte darauf eine gute commit Nachricht zu hinterlassen, um deinen Commit für andere erklärbar zu machen. 

You should commit your changes in small steps, this makes it easier to find the corresponding commit when you are looking for bugs. On the other side it's easy for your coworkers to reproduce the work you have done. All files added by git add {{...}} will be a part of your commit. Please provide a good commit message (what have you done? - short!) for your coworkers.


git commit -m "I added a new dll for walls"


Änderungen deinem Branch hinzufügen / Push Commits to your Branch
Nachdem du deine Arbeit in mehreren Commits zusammen gefasst hast, ist es an der Zeit diese auf deinen Branch zu übernehmen. 

After you group your changes in different commits it's time to push them to your feature branch.



Wenn du das erste mal auf deinen Branch "pushst" musst du den "origin" setzen. Dies ist der Ziel-Branch für deine Änderungen.

When you push first time from a new branch you need to set the origin, thats the target branch for your changes. 



git push -u origin feature/{{feature_name}}



Wenn das Ziel einmal gesetzt ist, kannst du folgenden Befehl nutzen:

When the origin path is already set you can use:



git push



### Änderungen herunterladen / Pull Changes

Von Zeit zu Zeit arbeitet man gemeinsam auf einem Branch, sollte dies der Fall sein, macht es Sinn die Änderungen deiner Mitarbeiter regelmäßig deiner lokalen Kopie hinzuzufügen:

From time to time you work with your coworkers together on one Branch, if this is the case, it makes sense to pull thier changes to your lokal work copy.



git pull



### Pull Request Erstellen / Create a Pull Request

You should use the webinterface to create a pull request. All changes you made in your branch will be applied to the master branch. This is the last step and finish your feature implementation. Your coworkers can take a look at your changes and make a review. 

Du solltest das Webinterface nutzen um einen Pull Request zu erstellen. Alle Änderungen die du in deinem Branch vorgenommen hast werden auf den Master Branch übernommen. Dies ist der letzte Schritt und schließt deine Arbeit an deinem Feature ab. Deine Mitarbeiter können die Änderungen die du gemacht hast einsehen und ein Review vornehmen.


### Error Handling

Ooopsi how can I reset my added changes?
Sometimes you add some files to the index section and realize some of them are added by mistake. You can remove files from the index section with:



git reset HEAD {{file_name}}

Ooopsi how can I reset my last Commit ( not pushed )?
Sometimes you made a commit and realize some of the files or changes are comitted by mistake. You can reset the last commit ( not pushed ) with:



git reset --soft HEAD~1

