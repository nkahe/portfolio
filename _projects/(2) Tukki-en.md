---
name: Tukki ticketing system (en)
layout: page
tools: [Angular, TypeScript, HTML, Sass, Jasmine, REST]
image: assets/images/tukki-en//lista.png
description: Web application for communication between teachers and students. 
# external_url: https://www.google.com
---
# Front-end of Tukki -ticketing system

[View this documentation in finnish](1-tukki.html)

This is presentation of the frontend for the Tukki ticketing system I was
implementing for the *Diginet* -project. I did it during 14 month period. It has been implemented with
[Angular](https://angular.io/){:target="_blank" rel="noopener noreferrer"}. Programming language was TypeScript and Sass/SCSS for styles. For reactivity I used RxJS where it offered advantage in addition to promises. I made technical documentation about frontend which [can be read here](https://github.com/nkahe/Tukki-frontend/blob/main/documentation/kuvaus/description.md). Backend of the application uses Node.js, PostreSQL as database and communication with the frontend is done using REST API. For code editor I used VS Code.

Application is open source and the code [can be viewed at my Github -repo](http://github.com/nkahe/Tukki-frontend){:target="_blank" rel="noopener noreferrer"}


First, is useful to define what was the scope I did and what was done by others. Things I've done:

- Frontend architechture.
- Most of the implementation.
- Technical documentation.
- Almost all unit tests.

Things done by my team mates:

- Application functionality- and interface design.
- Some parts of the frontend: rich text editor, make a FAQ from question,
profile view, additional fields in question views, privacy statement content.

Size of project's (front-end) source code by numbers:

| Language    | Files | Blank | Comment | Code  |
|------------|-------|-------|---------|-------|
| TypeScript | 123   | 1508  | 1854    | 10660 |
| HTML       | 27    | 510   | 74      | 3179  |
| SCSS       | 38    | 376   | 136     | 1766  |
| JSON       | 2     | 0     | 0       | 319   |
| **Total**  | 190   | 2394  | 2064    | 15924 |

## Demonstration of implementation

I won't go through all the functions or views of the system, but I'll show you some of the highlights. The application is designed to be used primarily on a computer screen or tablet, but is also usable on a phone screen. Attention has been paid to accessibility.

The list of questions is the main view of the application:

![kysymyslista](assets/images/tukki-en/lista.png)

The app can be embedded in the Moodle learning system, or used as a standalone web application. Above is the latter view. When logged in as a teacher, you can see all the
questions asked to teachers on the course. All users can see questions and answers teachers are set as *frequently asked questions* (FAQ).

Table like most components of the app are made using Angular Material library which appearance is customized when necessary. Part of components I have made by myself.
The rows of table can be sorted by different columns and filtered by
the information contained in the different questions. The content of the table
is updated periodically or manually.

![kysymyslista](assets/images/tukki-en/valikko.png)

You can change the language used in the app to Finnish. I made the translations for the app. Users can view their profile and teachers can change the settings for the course.

![kysymyslista](assets/images/tukki-en/login.png)

When embedded, the app gets login information from Moodle. Outside Moodle the login is done first manually with a login and password. It uses authorization code flow. After that authorization is can be done using the received cookie.

![kysymys](assets/images/tukki-en/tiketti.png)

In the individual question view, the user can view the information about the
question. The teacher can set the question's state as resolved and the sender of the
question can remove or edit the question. Teachers and students can add comments to
the question, which are displayed below the question. Users can edit their own
comments.

![kommentti](assets/images/tukki-en/kommentti.png)

The name, role, avatar icon of the questioner are
displayed with the question and comments along with the date when the comment was posted and edited. I made this component by myself. While editing a comment, user can delete it, change it's status and add or remove attachment files. I made the component by myself.

![progress bar](assets/images/tukki/progress-bar.png)

Files are sent in parallel and the status of their transmission is updated
with progress bars and it can be stopped.

![oletko varma](assets/images/tukki-en/oletko-varma.png)

Teachers can ask Frequently Asked Questions. Here the user has selected "Beginning"
in the middle of editing, in which case they will be asked for confirmation. Forms
are validated using *Angular Reactive Forms*.

![asetukset](assets/images/tukki-en/asetukset.png)

Teachers on the course can change the course settings, import and export
frequently asked questions course settings as JSON -files, and invite people outside
courses to join it. Clicking on the edit icon for additional fields will open
an editing view for them (below).

![asetukset](assets/images/tukki-en/lisäkenttä.png)

Edit view for additional fields. The addition of multiple options is implemented
using Angular Material chips.

{% include elements/button.html link="#" text="Back to start" block=true %}
