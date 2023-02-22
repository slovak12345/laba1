
# Дневник разработки

Здесь будут описаны шаги разработки

## DD.MM.YYYY Создан план разработки приложения по указанным требованиям

Чтобы создать приложение Spring Boot с указанными выше требованиями, выполним следующие действия:

1. Создайдим новый проект Spring Boot с помощью Spring Initializr, добавив следующие зависимости:
	- Spring Web
	- Spring Data JPA
	- PostgreSQL Driver
	- Liquibase Migration
	- Testcontainers
	- JUnit Jupiter API
	
2. Определим свои модели Entity и аннотируем их соответствующими аннотациями JPA, такими как @Entity, @Table, @Column и @Id. Кроме того, добавим проверку на уровне поля, используя аннотации javax.validation.constraints.

3. Определим свои модели Dto, которые должны представлять данные, отправляемые/получаемые через API. Создадим сопоставление между моделями Entity и Dto с помощью таких инструментов, как MapStruct.

4. Создайдим интерфейсы репозитория Spring Data JPA, расширив интерфейс JpaRepository. Определим свои запросы, используя имена методов или аннотации @Query.

5. Используйем Liquibase для создания схемы базы данных и исходных данных.

6. Определим контроллеры Spring MVC, используя аннотации @RestController и @RequestMapping. Реализуйте операции CRUD для своих основных объектов, используя соответствующие методы HTTP (GET, POST, PUT, DELETE).

7. Реализуем разбиение на страницы для запросов findAll, используя встроенную в Spring Data JPA поддержку разбиения на страницы.

8. Реализуем по крайней мере одну конечную точку бесконечной прокрутки, которая возвращает данные с помощью разбиения на страницы с флагом hasMore в ответе.

9. Реализуем по крайней мере одну конечную точку, которая возвращает данные с разбиением на страницы с общим количеством записей в заголовке ответа.

10. Реализуем транзакции в сложных запросах, требующих нескольких операций с базой данных. Используем аннотацию @Transactional, чтобы аннотировать методы, которым требуется поддержка транзакций.

11. Используем переменные среды для настройки приложения, используя аннотацию @Value, чтобы внедрить их в приложение.

12. Используем docker-compose для запуска экземпляра базы данных PostgreSQL.

13. Напишем интеграционные тесты для своих контроллеров, используя Testcontainers и JUnit Jupiter API.

14. Обрабатываем исключения и ошибки в ваших контроллерах с помощью аннотаций @ControllerAdvice и @ExceptionHandler, возвращая удобочитаемое сообщение об ошибке в тексте ответа.

15. Сериализуем все перечисления в базе данных как строки, используя аннотацию @Enumerated(EnumType.STRING).

16. Разделим приложение на разные уровни (сервисы, репозитории, контроллеры, модели, перечисления и т. д.), чтобы поддерживать чистоту архитектуры и кода.

## DD.MM.YYYY Установка необходимых компонентов

1. Установка MS Visual Studio Code

2. Установка Java https://download.oracle.com/java/19/latest/jdk-19_windows-x64_bin.msi ( sha256)

3. Установка Maven https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip

4. Установка необходимых расширений:

	Name: Spring Boot Dashboard
	Id: vscjava.vscode-spring-boot-dashboard
	Description: Spring Boot Dashboard for VS Code
	Version: 0.10.1
	Publisher: Microsoft
	VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-boot-dashboard

	Name: Spring Boot Extension Pack
	Id: vmware.vscode-boot-dev-pack
	Description: A collection of extensions for developing Spring Boot applications
	Version: 0.2.1
	Publisher: VMware
	VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=vmware.vscode-boot-dev-pack
	
	Name: Spring Boot Tools
	Id: vmware.vscode-spring-boot
	Description: Provides validation and content assist for Spring Boot `application.properties`, `application.yml` properties files. As well as Boot-specific support for `.java` files.
	Version: 1.44.0
	Publisher: VMware
	VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=vmware.vscode-spring-boot

	Name: Spring Initializr Java Support
	Id: vscjava.vscode-spring-initializr
	Description: A lightweight extension based on Spring Initializr to generate quick start Spring Boot Java projects.
	Version: 0.11.2
	Publisher: Microsoft
	VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-spring-initializr