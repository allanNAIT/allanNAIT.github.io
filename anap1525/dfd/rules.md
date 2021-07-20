---
layout: page
title: DFD Rules
---

## Rules:
Avoid “Black Holes”, “Miracles” and “Grey Holes”

### Black Holes:
Process has Input but no Output Order Data.
[black-hole](files/black-hole.png)

### White Hole or Miracle:
Process has Output but no Input.
[miracle](files/miracle.png)

### Gray Hole:
Process has insufficient Input for the Output it generates.
[gray-hole](files/gray-hole.png)

**Incorrect Data Flows** | **Correct Data Flows**
-------------------------|-----------------------
[incorrect-data-flows](files/incorrect-data-flows.png) | [correct-data-flows](files/correct-data-flows.png)

## Guidelines for Constructing DFDs:
1. Choose meaningful names for processes, flows, stores, and entities:<br>
    <ol type="a">
        <li>Label the process to identify the function the system is carrying out</li>
        <li>Choose an active verb and an appropriate object to form a descriptive phrase</li>
        <li>Avoid verbs such as DO, HANDLE, PROCESS</li>
        <li>Avoid specific abbreviations and acronyms familiar to the user or to us</li>
    <ol>
2. Number the processes:<br>
    <ol type="a">
        <li>Numbering schemes should be consistent</li>
        <li>Numbering schemes may imply a certain sequence of operation</li>
        <li>Numbers are a convenient way of referencing processes</li>
        <li>Numbers become the basis for a hierarchical numbering scheme</li>
    </ol>
3. Avoid overly complex DFDs:<br>
    <ol type="a">
        <li>Should be easy to understand, easy to absorb, easy to read and pleasing to the eye</li>
        <li>Should fit comfortably on an 8.5 by 11-inch sheet of paper</li>
        <li>Generally, not more than 6 - 8 processes per page</li>
        <li>Context diagram shows one process that represents the entire system and highlights the interfaces between the system and the external entities</li>
    </ol>
4. Redraw the DFD as many times as necessary for aesthetics:<br>
    <ol type="a">
        <li>Draw, redraw, redraw</li>
        <li>Should be technically correct</li>
        <li>Should be acceptable to the user</li>
        <li>Should be neat</li>
    </ol>
5. Make sure your DFD is logically consistent:<br>
    <ol type="a">
        <li>Avoid processes that have no outputs - "black holes"</li>
        <li>Avoid processes that have no inputs - "miracles"</li>
        <li>Beware of unlabeled flows and unlabeled processes</li>
        <li>Beware of read-only or write-only stores</li>
        <li>Make sure that dataflows coming into and going out of an entire level correspond to the dataflows coming into and going out at the next lower level which describes that process</li>
        <li>A store at the highest level serves as an interface between two or more processes; show it at EVERY lower-level that further describes those processes</li>
    </ol>

### [DFD Home](dfds.md)
### [ANAP1525 Home](../)