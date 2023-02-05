# ENBREA CSV Format (ECF)

Das ENBREA CSV Format (kurz ECF-Format) dient zum Importieren von Daten nach ENBREA und zum Exportieren von Daten aus ENBREA. Auch andere Anwendungen wie z.B. DAVINCI und MAGELLAN unterstützen das ECF-Format.

Das ECF-Format umfasst einen standardisierte Menge von CSV-Dateien, die mit Hilfe von [CSV Table Schema](https://openpotato.github.io/csv-table-schema/) formal spezifiziert sind. 

## Dokumentation

### Liste der ECF-Dateien

Die Liste aller Schema-Dateien [findest Du hier](src).

#### Manifest

Dateiname                         | Inhalt                          | Spezifikation
--------------------------------- | ------------------------------- | -------------
Manifest.csv                      | Globale Daten                   | [CSV-Schema](src/ecf-manifest.csvts.json)

#### Schlüsselverzeichnisse

Dateiname                         | Inhalt                          | Spezifikation
--------------------------------- | ------------------------------- | -------------
Countries.csv                     | Staaten                         | [CSV-Schema](src/ecf-countries.csvts.json)
CourseCategories.csv              | Kurskategorien                  | [CSV-Schema](src/ecf-catalog.csvts.json)
CourseFlags.csv                   | Kursmerkmale                    | [CSV-Schema](src/ecf-catalog.csvts.json)
CourseTypes.csv                   | Kursarten                       | [CSV-Schema](src/ecf-catalog.csvts.json)
Languages.csv                     | Sprachen                        | [CSV-Schema](src/ecf-languages.csvts.json)
MaritalStatuses.csv               | Ehestände                       | [CSV-Schema](src/ecf-catalog.csvts.json)
Nationalities.csv                 | Nationalitäten                  | [CSV-Schema](src/ecf-nationalities.csvts.json)
Religions.csv                     | Religionszugehörigkeiten        | [CSV-Schema](src/ecf-catalog.csvts.json)
RoomAbsenceReasons.csv            | Raumausfallgründe               | [CSV-Schema](src/ecf-catalog.csvts.json)
RoomAbsenceStatuses.csv           | Raumausfallstatus               | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolClassAbsenceReasons.csv     | Klassenabwesenheitsgründe       | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolClassCategories.csv         | Klassenkategorien               | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolClassLevels.csv             | Klassenstufen                   | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolClassProfiles.csv           | Klassenprofile                  | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolClassTypes.csv              | Klassenarten                    | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolOrganisations.csv           | Schulorganisationen             | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolProfiles.csv                | Schulprofile                    | [CSV-Schema](src/ecf-catalog.csvts.json)
SchoolTypes.csv                   | Schularten                      | [CSV-Schema](src/ecf-catalog.csvts.json)
SubjectFocuses.csv                | Fachschwerpunkte                | [CSV-Schema](src/ecf-catalog.csvts.json)
SubjectCategories.csv             | Fachkategorien                  | [CSV-Schema](src/ecf-subject-categories.csvts.json)
SubjectGroups.csv                 | Fachgruppen                     | [CSV-Schema](src/ecf-catalog.csvts.json)
SubjectTypes.csv                  | Facharten                       | [CSV-Schema](src/ecf-catalog.csvts.json)
TeacherAbsenceReasons.csv         | Lehrerabwesenheitsgründen       | [CSV-Schema](src/ecf-catalog.csvts.json)

#### Schuldaten

Dateiname                         | Inhalt                          | Spezifikation
--------------------------------- | ------------------------------- | -------------
Announcements.csv                 | Mitteilungen                    | [CSV-Schema](src/ecf-announcements.csvts.json)
Courses.csv                       | Kurse                           | [CSV-Schema](src/ecf-courses.csvts.json)
Departments.csv                   | Abteilungen                     | [CSV-Schema](src/ecf-departments.csvts.json)
LessonGaps.csv                    | Fehlstellen                     | [CSV-Schema](src/ecf-lesson-gaps.csvts.json)
RoomAbsences.csv                  | Raumausfälle                    | [CSV-Schema](src/ecf-room-absences.csvts.json)
Rooms.csv                         | Räume                           | [CSV-Schema](src/ecf-rooms.csvts.json)
ScheduledLessons.csv              | Verplanter Unterricht           | [CSV-Schema](src/ecf-scheduled-lessons.csvts.json)
SchoolClassAbsences.csv           | Klassenabwesenheiten            | [CSV-Schema](src/ecf-schoolclass-absences.csvts.json)
SchoolClasses.csv                 | Klassen                         | [CSV-Schema](src/ecf-schoolclasses.csvts.json)
StudentCourseAttendances.csv      | Schüler-Kursteilnahmen          | [CSV-Schema](src/ecf-student-course-attendances.csvts.json)
StudentForeignLangusges.csv       | Schüler-Fremdsprachenfolge      | [CSV-Schema](src/ecf-student-foreign-languages.csvts.json)
StudentSchoolClassAttendances.csv | Schüler-Klassenteilnahmen       | [CSV-Schema](src/ecf-student-schoolclass-attendances.csvts.json)
StudentSubjects.csv               | Schüler-Fachdaten               | [CSV-Schema](src/ecf-student-subjects.csvts.json)
Students.csv                      | Schüler                         | [CSV-Schema](src/ecf-students.csvts.json)
Subjects.csv                      | Fächer                          | [CSV-Schema](src/ecf-subjects.csvts.json)
SubstituteLessons.csv             | Vertretungsunterricht           | [CSV-Schema](src/ecf-substitute-lessons.csvts.json)
TeacherAbsences.csv               | Lehrer-Abwesenheiten            | [CSV-Schema](src/ecf-teacher-absences.csvts.json)
TeacherCourseAttendances.csv      | Lehrer-Kursteilnahmen           | [CSV-Schema](src/ecf-teacher-course-attendances.csvts.json)
Teachers.csv                      | Lehrer                          | [CSV-Schema](src/ecf-teachers.csvts.json)
TimeFrames.csv                    | Zeitrahmen                      | [CSV-Schema](src/ecf-timeframes.csvts.json)
Vacations.csv                     | Ferien                          | [CSV-Schema](src/ecf-vacations.csvts.json)

### Konzepte

#### CSV-Schema

ECF ist mit Hilfe von [CSV Table Schema](https://github.com/csv-table-schema/csv-table-schema.spec) formal spezifiziert. 

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

[CSV Table Schema](https://github.com/csv-table-schema/csv-table-schema.spec) unterstützt [JSON-Schema](https://json-schema.org/) als Unterschema, so dass einer vollständigen Validierung von ECF nichts im Wege steht.

## Kann ich mithelfen?

Ja, sehr gerne. Der beste Weg mitzuhelfen ist es, Rückmeldung per Issue-Tracker zu geben und/oder eigene Pull-Requests zu generieren. Oder schreibe uns einfach eine E-Mail unter enbrea@stueber.de.

## Code of conduct (Verhaltensregeln)

In diesem Projekt wurde der [STÜBER SYSTEMS Code of conduct](https://www.stueber.de/code-of-conduct.php) übernommen.
