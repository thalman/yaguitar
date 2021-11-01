# yaguitar
Yet another TeX style for guitar chords

## Motivation
The main goal is to make song typing as simple as possible. Also using international characters is mandatory.

## Using yaguitar
Yaguitar style works in both - plainTeX and LaTeX

### Commands
#### \chord
#### \chordScheme
#### \ukeChordScheme

### Guitar environment
Yaguitar defines new environment _guitar_. In LaTex use

    \begin{guitar}
    \end{guitar}

In plainTeX use

    \guitarOn
    \guitarOff

Inside guitar environment some characters are active (square bracket, pipe, space and new line). This allows stretch text under
chords when it is needed.

    \begin{guitar}
    [Ami]Lorem [C]ipsum do[G]lor sit amet,
    con[C]secte[C#]tuer adipiscing elit.
    Etiam quis qu[Cmi]am. [Cbmi]Maecenas [Hmi]lorem.
    |: [Ami]Etiam dui sem, [D#dim]fer[Ddim]men[Dbdim]tum vitae, :|
    sagit[C#mi7/5]tis id, [D]malesuada in, quam. In convallis.
    \end{guitar}


