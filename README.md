# ENBREA CSV Format (ECF)

Das ENBREA CSV Format (kurz ECF-Format) dient zum Importieren von Daten nach ENBREA und zum Exportieren von Daten aus ENBREA. Auch andere Anwendungen wie z.B. DAVINCI und MAGELLAN unterstützen das ECF-Format.

Das ECF-Format umfasst einen standardisierte Menge von CSV-Dateien, die mit Hilfe von [Simple CSV Schema](https://github.com/simple-csv-schema/simple-csv-schema.spec) formal spezifiziert sind. 

## Dokumentation

### Liste der ECF-Dateien

Die Liste aller Schema-Dateien [findest Du hier](src).

#### Schlüsselverzeichnisse

Dateiname                         | Inhalt                          | Spezifikation
--------------------------------- | ------------------------------- | -------------
Countries.csv                     | Staaten                         | [CSV-Schema](src/ecf-countries.scsv.json)
CourseCategories.csv              | Kurskategorien                  | [CSV-Schema](src/ecf-catalog.scsv.json)
CourseFlags.csv                   | Kursmerkmale                    | [CSV-Schema](src/ecf-catalog.scsv.json)
CourseTypes.csv                   | Kursarten                       | [CSV-Schema](src/ecf-catalog.scsv.json)
Languages.csv                     | Sprachen                        | [CSV-Schema](src/ecf-languages.scsv.json)
MaritalStatuses.csv               | Ehestände                       | [CSV-Schema](src/ecf-catalog.scsv.json)
Nationalities.csv                 | Nationalitäten                  | [CSV-Schema](src/ecf-nationalities.scsv.json)
Religions.csv                     | Religionszugehörigkeiten        | [CSV-Schema](src/ecf-catalog.scsv.json)
RoomAbsenceReasons.csv            | Raumausfallgründe               | [CSV-Schema](src/ecf-catalog.scsv.json)
RoomAbsenceStatuses.csv           | Raumausfallstatus               | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolClassAbsenceReasons.csv     | Klassenabwesenheitsgründe       | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolClassCategories.csv         | Klassenkategorien               | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolClassLevels.csv             | Klassenstufen                   | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolClassProfiles.csv           | Klassenprofile                  | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolClassTypes.csv              | Klassenarten                    | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolOrganisations.csv           | Schulorganisationen             | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolProfiles.csv                | Schulprofile                    | [CSV-Schema](src/ecf-catalog.scsv.json)
SchoolTypes.csv                   | Schularten                      | [CSV-Schema](src/ecf-catalog.scsv.json)
SubjectFocuses.csv                | Fachschwerpunkte                | [CSV-Schema](src/ecf-catalog.scsv.json)
SubjectCategories.csv             | Fachkategorien                  | [CSV-Schema](src/ecf-subject-categories.scsv.json)
SubjectGroups.csv                 | Fachgruppen                     | [CSV-Schema](src/ecf-catalog.scsv.json)
SubjectTypes.csv                  | Facharten                       | [CSV-Schema](src/ecf-catalog.scsv.json)
TeacherAbsenceReasons.csv         | Lehrerabwesenheitsgründen       | [CSV-Schema](src/ecf-catalog.scsv.json)

#### Schuldaten

Dateiname                         | Inhalt                          | Spezifikation
--------------------------------- | ------------------------------- | -------------
Announcements.csv                 | Mitteilungen                    | [CSV-Schema](src/ecf-announcements.scsv.json)
Courses.csv                       | Kurse                           | [CSV-Schema](src/ecf-courses.scsv.json)
Departments.csv                   | Abteilungen                     | [CSV-Schema](src/ecf-departments.scsv.json)
LessonGaps.csv                    | Fehlstellen                     | [CSV-Schema](src/ecf-lesson-gaps.scsv.json)
RoomAbsences.csv                  | Raumausfälle                    | [CSV-Schema](src/ecf-room-absences.scsv.json)
Rooms.csv                         | Räume                           | [CSV-Schema](src/ecf-rooms.scsv.json)
ScheduledLessons.csv              | Verplanter Unterricht           | [CSV-Schema](src/ecf-scheduled-lessons.scsv.json)
SchoolClassAbsences.csv           | Klassenabwesenheiten            | [CSV-Schema](src/ecf-schoolclass-absences.scsv.json)
SchoolClasses.csv                 | Klassen                         | [CSV-Schema](src/ecf-schoolclasses.scsv.json)
StudentCourseAttendances.csv      | Schüler-Kursteilnahmen          | [CSV-Schema](src/ecf-student-course-attendances.scsv.json)
StudentForeignLangusges.csv       | Schüler-Fremdsprachenfolge      | [CSV-Schema](src/ecf-student-foreign-languages.scsv.json)
StudentSchoolClassAttendances.csv | Schüler-Klassenteilnahmen       | [CSV-Schema](src/ecf-student-schoolclass-attendances.scsv.json)
StudentSubjects.csv               | Schüler-Fachdaten               | [CSV-Schema](src/ecf-student-subjects.scsv.json)
Students.csv                      | Schüler                         | [CSV-Schema](src/ecf-students.scsv.json)
Subjects.csv                      | Fächer                          | [CSV-Schema](src/ecf-subjects.scsv.json)
SubstituteLessons.csv             | Vertretungsunterricht           | [CSV-Schema](src/ecf-substitute-lessons.scsv.json)
TeacherAbsences.csv               | Lehrer-Abwesenheiten            | [CSV-Schema](src/ecf-teacher-absences.scsv.json)
TeacherCourseAttendances.csv      | Lehrer-Kursteilnahmen           | [CSV-Schema](src/ecf-teacher-course-attendances.scsv.json)
Teachers.csv                      | Lehrer                          | [CSV-Schema](src/ecf-teachers.scsv.json)
TimeFrames.csv                    | Zeitrahmen                      | [CSV-Schema](src/ecf-timeframes.scsv.json)
Vacations.csv                     | Ferien                          | [CSV-Schema](src/ecf-vacations.scsv.json)

### Konzepte

#### CSV-Schema

ECF ist mit Hilfe von [Simple CSV Schema](https://github.com/simple-csv-schema/simple-csv-schema.spec) formal spezifiziert. 

Vorteile:

+ ECF-Dateien sind sauber dokumentiert. Die Dokumentation ist standardisiert und versionierbar.
+ ECF-Dateien können validiert werden.

#### JSON-Schema als Unterschema

CSV ist ein relationales Format, das Daten 2-dimensional abbildet: Jede Zeile in einer CSV-Datei ist ein Datensatz und jede Spalte repräsentiert ein Feld in diesen Datensätzen. Komplexere Strukturen werden standardmäßig durch zusätzliche CSV-Dateien modelliert, die untereinander eine Relationsbeziehung aufbauen. Das ist aber nicht immer gewünscht. In diesem Fall muss man den Inhalt einzelne CSV-Felder komplexer modellieren. 

Das ECF-Format nutzt dafür [JSON](https://www.json.org/json-de.html) als eingebettetes Format, d.h. die Inhalte einzelner Felder sind entweder als JSON-Array oder als JSON-Objekt gespeichert.

Ein Beispiel:

```
Id;Code;Name;DepartmentIdList
216C0B8C-E6BB-4C9A-9463-47531650238A;DE;Deutsch;"[""CA96D550-DA95-4DE4-8CE7-57BB8AE5ADED"",""DDDFA6BF-BDE4-45B9-B4DF-37410CE6619F""]"
```

Das Feld `DepartmentIdList` ist hier als JSON-Array mit zwei Id-Einträgen formatiert.

[Simple CSV Schema](https://github.com/simple-csv-schema/simple-csv-schema.spec) unterstützt [JSON-Schema](https://json-schema.org/) als Unterschema, so dass einer vollständigen Validierung von ECF nichts im Wege steht.

## Kann ich mithelfen?

Ja, sehr gerne. Der beste Weg mitzuhelfen ist es, Rückmeldung per Issue-Tracker zu geben und/oder eigene Pull-Requests zu generieren. Oder schreibe uns einfach eine E-Mail unter enbrea@stueber.de.

## Code of conduct (Verhaltensregeln)

In diesem Projekt wurde der [STÜBER SYSTEMS Code of conduct](https://www.stueber.de/code-of-conduct.php) übernommen.
