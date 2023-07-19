
# Web Service MVC project layout

This repository presents a suggested project structure for developing web applications using frameworks with flexible structure e.g. FastaPI, Flask in Python or Express, and Fastify in Javascript/Typescript, it also can be used with Chi in Go, but with some modifications due to [Golang Project Layout](https://github.com/golang-standards/project-layout) recommendations. It offers a well-organized folder structure that is particularly recommended for medium to big size projects, where handling and ordering the application logic becomes crucial. By adopting this structure, developers can benefit from a modular and scalable architecture that promotes code reusability, maintainability, and collaboration among team members.

The proposed project structure follows the Model-View-Controller (MVC) design pattern, which promotes a clear separation of concerns.  This separation lets developers easily navigate and modify specific application components, facilitating teamwork and reducing code conflicts.

Moreover, this project structure proposal includes directories like "dao" or "repository" for storing persistent layer logic. "ci" to store common utility functions which can be useful for build, deploy, or test purposes, "tests" to house unit, integration or functional tests for the application, and "config" to hold configuration files. These directories help streamline development, testing, and configuration processes, making maintaining and extending the project in the long run easier.

In summary, this project structure proposal provides a solid foundation for organizing the logic of medium to big size web applications. However, it can also be beneficial for smaller projects that have the potential to grow rapidly. By adopting this structure, developers can ensure scalability, maintainability, and codebase organization, enabling them to build robust and efficient applications.

---

Please view `README.md` in each directory for more info. This section has only a short description of every package.

## Project root directories

`/ci`

CI related files like build, deployment and test related scripts

`/project_package`

Main project package. Contains project essential packages

## Project package directories

`/api`

All API documentation related files

`/assets`

Project related assets e.g. templates, images, etc.

`/clients`

Project specific API clients for third party APIs.

`/config`

Config files and config related logic

`/controller`

MVC Controllers package
 
`/dao` (optional)

> For projects which adopts this pattern

 DAO packages. 

`/di` (optional)

> For projects which adopts this pattern

Dependency injection configurations. 

`/middleware`

API middlewares

`/model`

MVC Model package.

`/repository` (optional)

> For projects which adopts this pattern

Repository pattern contracts and sources implementations.

`/router`

API routers package.

`/tests`

Packages with different types of tests

---

## Package which better to avoid

`/utils`

Projects often dump all code for which was not found in a better place in well-structured packages to this directory.
And at the end of the day, this package becomes some kind of dumpster for all bad and unstructured code in the project.
So better to spend a little bit of time and place the code in the right structure than dump it to `/utils`.

`/common`

Same as in `utils` very fast and too often turns into another kind of code dumpster. Often contains code that can be reworked in some parent classes for inheritance rather not to just being dumped in this folder.

`/helpers`

Same as `/utils` and `/common` packages.