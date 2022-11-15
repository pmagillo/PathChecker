# PathChecker


DEMO: Visual path checker

CONTENT OF THIS README

Purpose,
Sources,
Compiling,
Execution,
Instructions for use,
References.

PURPOSE

Draw a digital path (specified as a sequence of moves in the four cardinal
directions on a square grid) without self crossing (if possible).

Each segment composing the curve is drawn with a small perturbation
(up or downs for horizontal segments, left or right fro vertical ones),
in such a way to avoid crossings when passing a second time through the
same point. If this is not possible, a self intersection is reported.

The input path cannot contain U-turns (= consecutive moves in opposite
directions) and cannot pass a second time through the starting point
(although it may return at the starting point, i.e., it may be a closed
path).

If the path is entered interactively, the buttons corresponding to
forbidden moves are disabled.

If the path is pre-entered as a string of characters in N,S,W,E, the
path is cheched before use.

SOURCES AND COMPILING

The executable is provided. If you don't plan to recompile, skip this section.

The sources of the program are in Java. The package orthopaths contains
the following classes:
 Vertex,
 Direction,
 HalfSegment,             
 VertexSet,
 HalfSegmentSkipList,
 PathUtils,
 PathChecker,
 VisualCheck.

To compile, you need to have the Java JDK installed on your PC. 
Type the following from a command window:

  javac orthopaths/*.java

  jar cfm pathchecker.jar Manifest.txt orthopaths/*.class

And, optionally, for generating the documentation:

  javadoc  orthopaths/*.java 

EXECUTION

If you want just to run the demo, download the already compiled file pathchecker.jar

  java -jar pathchecker.jar 

INSTRUCTIONS FOR USE

The upper part of the window is the drawing area. The green dot marks the
starting point of the path. The window enlarges automatically when the path
needs more space to be drawn. It is provided with scroll bars.

The bottom parts contains three bars, from top to bottom:

1) shows the number of already drawn moves.

2) shows the entire path decomposed in the sequence of already drawn moves
(left) and the sequence of moves entered but not drawn yet (right and in
square brackets).

3) empty, it will become red to show a detected self intersection.

The middle parts contains buttons for user interaction.

Button "exit" terminates the program.

Button "hide/show drawn curve" swicthes between the curve drawing the path
in the trivial way and in the crossing-free way.

The two radio buttons "type in an entire path" and "enter the next moves"
switch between two modes:
1) a path is given and the moves composing it are progressively drawn 
by pressing button "next move" or "all moves".
2) a path is entered incrementally by pressing the buttons labeled with
the four cardinal directions.

The four buttons with the cardinal directions allow drawing the next
move when "enter the next move" is selected. The directions corresponding
to forbidden moves are disabled. The button having the opposite direction of
the last drawn move is disabled to avoid U-turns. All four buttons are
disabled if the path has been closed.

The two buttons "next move" or "all moves" draw the next move, or all
remaining moves, of the given path when "type in an entire path" is
selected. If the given path has been completely drawn, they are disabled.

The two buttons "undo last move" and "undo all moves" allow undoing 
drawing actions. If the undone move came from a given path, it is sent back
to the part of the path which is still to be drawn. If the undone move 
was entered interactively, it is simply lost.

REFERENCES

This demo is associated with the article
"Crossing-Free Paths in the Square Grid" 
by Lidija Comic (faculty of Technical Sciences, University of Novi Sad, Serbia)
and Paola Magillo (DIBRIS, University of Genova, Italy),
submitted for publication in November 2022.
