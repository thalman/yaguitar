# yaguitar
Yet another TeX style for guitar chords

## Motivation
The main goal is to make song typing as simple as possible. Also using international characters is mandatory.

## Using yaguitar
Yaguitar style works in both - plainTeX and LaTeX

### Commands
#### \chord

The \chord#1 command prints the chord name above the current place

    \chord{D}V širém poli studáne\chord{A}čka \chord{G}kamen\chord{D}ná

produces something like

    D                   A   G    D
    V širém poli studánečka kamenná

If you want to adjust the chord style, you may redefine \theChord, for exmple:

    \def\theChord#1{\strut{\footnotesize\bf #1}\hbox to 2pt{\hss}}%


#### \chordScheme

The `\chordScheme#1#2#3#4#5#6#7#8` draws chord diagram. First parameter is the name (Ami7). Next
six parameters represents strings (from top) and where to press them.

* -1 - muted string
* 0 - empty string
* 1+ - fretboard position

Last parameter is the fretboard position for chords played up the neck.

C major example: `\chordScheme{C}332010{}` and `\chordScheme{C}113331{3}`

![Chords](doc/c-chord.jpg)

#### \ukeChordScheme

The `\ukeChordScheme` is the same as `\chordScheme`, just for four string instrument like uke.

### Guitar environment
Yaguitar defines new environment _guitar_. In LaTex use

    \begin{guitar}
    \end{guitar}

In plainTeX use

    \guitarOn
    \guitarOff

Inside guitar environment some characters are active (square bracket, pipe, space and new line). This allows stretch text under
chords when it is needed.

### Quick Start Guide

![Song](doc/quickstartguide.jpg)

The above song was created with this LaTeX code:

    \section*{Lorem ipsum dolor}
    
    \chordScheme{Cdim}{-1}{0}{1}{2}{1}{2}{}
    \chordScheme{Ami}{0}{0}{2}{2}{1}{0}{}
    \chordScheme{Gmi}133111{3}
    \ukeChordScheme{Cdim}{2}{3}{2}{3}{}
    \ukeChordScheme{Ami}{2}{0}{0}{0}{}
    \ukeChordScheme{Gmi}0231{}
    
    \begin{guitar}
    \strophe{}%
    [Ami]Lorem [C]ipsum do[G]lor sit amet,
    con[C]secte[C#]tuer adipiscing elit.
    Etiam quis qu[Cmi]am. [Cbmi]Maecenas [Hmi]lorem.
    |: Etiam dui [Ami]sem, fer[Ddim]mentum vitae, :|
    sagit[C#mi7/5]tis id, [D]malesuada in, quam. In convallis.
    
    \refrain{}%
    [Ami]Pellentesque arcu. [C]Integer malesuada.
    [Ami]Nullam sit amet magna [C]in magna gravida vehicula.
    [A#mi]Nullam [Cdim]at [C]arcu a est [Cb]sollicitudin euismod.
    [Ami]Integer [Dmi]pe[E]llentesque [C]quam vel velit.[C][G][C]
    \end{guitar}
