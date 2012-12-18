# All DBWipes Frontend Notes


Dec 18, 2012
------------

### PAPER

devise: Integrated querying and visual exploration of large datasets

* Livny, Ramakrishnan, et al

Summary

* Mechanisms for data driven viz and formalizations of relationships between views
* Set-oriented semantics for visual operations
* Focus on Views and constraints (links) between views
    * Links are directional
    * Visual Link: keeps axes same
    * Record Link: joins views based on attr(s) equality
    * Operator Link: view tables&rarr;virtual table based on set operation
    * Aggregate Link: create virtual table as result of group-by aggregate existing table

Notations

* Tdata: table + schema
* Gdata: Tdata mapped to visualization properties (size, x, y, etc)
    * Not clear how to specify properties of different marks
* Mapping: u(Tdata) = Gdata
* View: a single plot
* Link: between views
* Visual filter (&sigma;<sup>viz</sup>): constraint on Gdata (on viewport)
* VGData: GData after visual filter
* view = view template (markup+title etc) + VGData
* Window: multiple views + links
* Presentation: multiple windows + links
* Cursor: a highlighted region in the viz (brush)
* &sigma;: filter.  (e.g., VGdata = &sigma;<sup>viz</sup> * u(Tdata))

Queries

* Selection: highlight, zoom, scroll
* Click: see tuples
* CursorMv: move cursor by clicking
* View formally defined as 5-tuple: (B, &sigma;<sup>viz</sup>,u, T, C)
    * B: background (data independent part of view)
    * T: Tdata
    * C: cursor layer 
* Push down &sigma;<sup>viz</sup>: u\*&sigma;<sup>T</sup>(Tdata) = &sigma;<sup>viz</sup>*u(Tdata)
* Lots of formal notation of how each link maps to the 5-tuple notation
* Non-nested filter queries can be made by combination of selections and record/agg links (seems very tedious)


Misc

* Supports multiple databases
* Distributed query management + buffer management (not discussed in paper)
* Prior papers describe the viz system

Good parts

Problems

 - does not discuss how to *create* visualizations
 - Mapping (u) are 1-1 and invertible &rarr;  No aggregation before mapping