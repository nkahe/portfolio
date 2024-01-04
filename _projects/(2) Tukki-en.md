---
name: Tukki ticketing system (en)
layout: default
tools: [Angular, TypeScript, HTML, Sass]
image: assets/images/tukki-en//lista.png
description: Diginet project, University of Oulu
# external_url: https://www.google.com
---
# Front-end for Tukki ticketing system

[This documentation in finnish](1-tukki.html)

[Fork of the repo in Github](http://github.com/nkahe/Tukki-frontend){:target="_blank" rel="noopener noreferrer"}

This is presentation of the frontend for the Tukki ticketing system I was
implementing for the Diginet -project. It has been implemented with
[Angular](https://angular.io/){:target="_blank" rel="noopener noreferrer"}.
Other technical documentation about interface I've made
[can be read here](https://github.com/nkahe/Tukki-frontend/blob/main/documentation/kuvaus/description.md).

First, is useful to define what was the scope I did and what was done by others:

## Things I've done for the frontend

- Frontend architechture.
- Most of the implementation.
- Technical documentation.
- Almost all unit tests.

## Things done my team mates

- Application functionality- and interface design.
- Some parts of the frontend: rich text editor, make a FAQ from question,
profile view, additional fields in question views, privacy statement content.

## Demonstration of implementation

![kysymyslista](assets/images/tukki-en/lista.png)

The list of questions is the main view of the application. Here is the view used
outside the Moodle upload. When logged in as a teacher, you can see all the
questions asked to teachers in the course. The table is made using the Angular
Material library. The rows can be sorted by different columns and filtered by
the information contained in the different questions. The content of the table
is updated periodically or manually.

![kysymyslista](src/assets/screenshots/lista.png)

![kysymyslista](assets/images/tukki-en/valikko.png)

You can change the language used in the app to Finnish

![kysymyslista](assets/images/tukki-en/login.png)

The system can be logged in manually with a login and password when used outside
the Moodle upload.

![kysymys](assets/images/tukki-en/tiketti.png)

In the individual question view, the user can view the information about the
question. The teacher can set the question as resolved and the sender of the
question can remove or edit it. Teachers and students can add comments to
the question, which are displayed below the question. Users can edit their own
comments.

![kommentti](assets/images/tukki-en/kommentti.png)

The name, role, avatar icon, and the date the comment was posted and edited are
displayed with the question and comment.

When editing a comment, you can delete it, change the status of the comment or text,
and add or remove attachments. The attachment component is something I made myself.

![kommentti](src/assets/screenshots/progress-bar.png)

Files are sent simultaneously and the status of their transmission is updated
with progress bars.

![oletko varma](assets/images/tukki-en/oletko-varma.png)

Teachers can ask Frequently Asked Questions. Here the user has selected "Beginning"
in the middle of editing, in which case they will be asked for confirmation. Forms
are validated using Angular Reactive Forms.

![asetukset](assets/images/tukki-en/asetukset.png)

Teachers on the course can change the course settings, download and add
frequently asked questions and course settings, and invite people outside
courses to join it. Clicking on the edit icon for additional fields will open
an editing view for them.

![asetukset](assets/images/tukki-en/lisäkenttä.png)

Edit view for additional fields. The addition of multiple options is implemented
using Angular Material chips.

 <a href="#">Back to beginning</a>
