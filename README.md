## TreeBase

TreeBase is a system for growing collaborative, limitless knowledge bases that get better with age.

### When TreeBase Helps

TreeBase helps you build knowledge bases about _anything_. It doesn't matter how simple or complex the domain.

TreeBase is useful whether you are building a knowledge base by yourself or with thousands of people.

### TreeBase Implementations

- [TypeScript/Javascript](https://github.com/treenotation/jtree/tree/master/treeBase)

### Demo TreeBases

- [The Solar System - 8 files](https://github.com/treenotation/jtree/tree/master/treeBase/planets)
- [IMDB Subset - 6,000 files](https://github.com/breck7/6k)

### How it Works

TreeBase stores data in plain text files using [Tree Notation](https://treenotation.org). Instead of storing data in rows in a compressed binary format, you store data in regular files.

So a database of planets might look like this:

    planets/
     venus.planet
     mercury.planet
     earth.planet
     mars.planet
     jupiter.planet
     saturn.planet
     neptune.planet
     uranus.planet

Each file contains information in a schema that you specify in a Grammar file.

For example, the file `mars.planet` might look like this:

    diameter 6794
    surfaceGravity 4
    yearsToOrbitSun 1.881
    moons 2

The Grammar file (TreeBase's version of "Schemas"), for this file would be this:

    planetNode
     root
     todo Change pattern to postfix.
     pattern \.planet$
     inScope abstractIntPropertyNode abstractFloatPropertyNode
     catchAllNodeType errorNode
    anyFirstCell
     todo remove the need for this
    errorNode
     baseNodeType errorNode
    intCell
     highlightScope constant.numeric.integer
    floatCell
     highlightScope constant.numeric.float
    keywordCell
     highlightScope keyword
    abstractIntPropertyNode
     cells intCell
     firstCellType keywordCell
     abstract
    abstractFloatPropertyNode
     cells floatCell
     firstCellType keywordCell
     abstract
    surfaceGravityNode
     extends abstractIntPropertyNode
    diameterNode
     extends abstractIntPropertyNode
    moonsNode
     extends abstractIntPropertyNode
    yearsToOrbitSunNode
     extends abstractFloatPropertyNode

TreeBase delegates to Git for versioning, backups, and collaboration.

## Do I need to use a library to use TreeBase?

No. You can use the TreeBase system without installing any new software on your computer. In fact, you don't even need to use a computer at all. Pen, paper, and some folders work well for small TreeBases.

## Can I use TreeBase with my existing SQL databases?

Yes. With one command you can turn any TreeBase database into a SQL database. There is no lock-in.

## Can I use TreeBase with my existing JSON or CSV workflows?

Yes. With one command you can convert any TreeBase into JSON, CSV, TSV, etc. There is no lock-in.

## Does TreeBase scale?

For collaborative knowledge bases, yes. We have been using TreeBase for over 2 years in systems with millions of lines and dozens of collaborators.

At the moment TreeBase works best for knowledge bases of less than 100,000 entities/files (each file can have many facts). For larger TreeBases you are likely to hit some scaling challenges. Read more on that [here](https://breckyunits.com/building-a-treebase-with-6-point-5-million-files.html).

Our focus with TreeBase is on collaborative knowledge bases, like Wikipedia for data. You are free to experiment with using TreeBase in other domains, and if you do please let us know how you are using it, but at the moment our focus is on knowledge bases.

## How is this different than Wikipedia?

You can think of TreeBase as similar to the [MediaWiki](https://www.mediawiki.org/wiki/MediaWiki) system that powers Wikipedia. The difference is whereas Wikipedia is focused on narratives first and semantic facts second, TreeBase is focused on semantics first and narratives second.

## Alternatives Considered and Relevant Links

- [Outline](https://github.com/outline/outline)
- [Forest 1.0](https://www.cs.princeton.edu/research/techreps/TR-904-11)
- [Semantic Wikis](https://en.wikipedia.org/wiki/Semantic_wiki)
- [Athens Research](https://github.com/athensresearch)
- [Dendron](https://dendron.so/)
- [org-roam](https://www.orgroam.com/)
- [jelly](https://jellypbc.com/)
- [tiddlyroam](https://tiddlyroam.org/)
- [foam](https://foambubble.github.io/foam/)
- [Remnote](https://www.remnote.io/)
- [Obsidian](https://obsidian.md/)
- [logseq](https://logseq.com/)

