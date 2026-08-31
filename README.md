# Fall 2026 coordinator

A single page for one semester at the Hertie School: the weekly timetable, every
session dated, how each grade is composed, and what is still unconfirmed.

Published at **https://fsotoj.github.io/hertie-fall-2026/**

The page is one self-contained `index.html`. Course documents are not here.

## Adding a session primer

One file per session in `sessions/`, named `<course>-s<NN>.html`, for example
`c23-s01.html`. Copy an existing one: the shared design lives in
`assets/style.css`, so a primer only carries its own content. Then add a row to
the **Session notes** list on `index.html`, using the course's colour class
(`c1` Data Science, `c2` Mathematics, `c3` Econ of Crime, `c4` Econ of Media).
