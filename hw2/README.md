# Welcome to Homework 2
Sahil Sewani
2023-09-01

This is my solution to homework 2. I’m using Quarto render this document
from a QMD file to a regular MD file for display on GITHUB.

## Scenario

Imagine you’re designing a Library Management System for a small local
library. The system needs to track information about books and library
members. Each book has a unique ISBN (International Standard Book
Number), a title, and a publication year. Each library member is
identified by a unique member ID, and the system needs to store their
name and contact information. Library members can check out books, but
they don’t have to.

## Design Task 1

Identify and document the entities, attributes, and relationships using
Chen notation.

{dot} //\| echo: false

graph ER { layout=neato; scale=1.1; node \[shape=box\]; book,
library_member; node \[shape=ellipse\]; title, isbn, member_ID,
publication_year, name, contact_information node
\[shape=diamond,style=filled,color=lightgrey\]; check_outs

    library_member -- check_outs [label="1",len=1.00]
    checkouts -- book [label="n",len=1.00]

    library_member -- member_ID
    library_member -- name
    library_member -- contact_information
    book -- isbn
    book -- title
    book -- publication_year

}

## Design Task 2

Identify and document the entities, attributes, and relationships using
Crow’s Foot notation.

erDiagram LIBRARY_MEMBER \|\|–\|{ BOOK : check_outs

    LIBRARY_MEMBER{
        string member_ID
        string name
        string contact_information

}

    BOOK {
        string isbn
        string title
        string publication_year

}
