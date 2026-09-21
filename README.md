# Fall 2026 coordinator

A single page for one semester at the Hertie School: what is due this week and next,
the weekly timetable, every session dated, how each grade is composed, and what is
still unconfirmed.

Published at **https://fsotoj.github.io/hertie-fall-2026/**

The page is one self-contained `index.html`. Course documents are not here.

## Adding a session primer

One file per session in `sessions/`, named `<course>-s<NN>.html`, for example
`c23-s01.html`. Copy an existing one: the shared design lives in
`assets/style.css`, so a primer only carries its own content. Then add a row to
the **Session notes** list on `index.html`, using the course's colour class
(`c1` Data Science, `c2` Mathematics, `c3` Econ of Crime, `c4` Econ of Media).

A lab session is named `<course>-lab<NN>.html` and works the same way. Where the lab
materials have not been published yet, the primer says so and prepares from the
lecture the lab extends, rather than guessing at the sheet.

Once a session has been taught, its row moves into the closed **Earlier sessions**
fold at the end of the same block, and the count in the `<summary>` goes up by one.
The file and its URL do not change.

`sessions/reading-a-paper.html` is not a session: it is the method page, the seven
questions to ask of a paper, linked from the top of the Session notes list.

## The week counters

The two counters in the masthead are computed in the browser from the `ITEMS` list in
the script at the bottom of `index.html`, one `['YYYY-MM-DD', 'label']` pair per dated
obligation. They show what is left in the current week and what falls in the next one,
so they age by themselves; what does not age by itself is the list, which needs a new
line whenever a deadline is announced.

## Changing the weekly timetable

Each class is one `.ev` inside its `.tt-day`, and its hours live only in
`data-at` (`"10:00–12:00"`). The script at the bottom of `index.html` reads that
and derives the grid row, so there is nothing to keep in sync: edit the time and
the block moves. The day comes from `data-day` on the wrapper, whose column is
set in `assets/style.css`.

The same markup is a day-by-day list under 861px, which is the phone layout and
also what a browser with JavaScript off gets. The hour grid appears only where
there is room for it without an inner scrollbar.
