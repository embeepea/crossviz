The steps below aren't needed for normal development --- these are
just my notes to myself about the only way that I've figured out so
far to get a browser REPL with this project.

I'd really like to figure out how to get a browser REPL going for this
project using Emacs/CIDER.  If anyone knows how to do that, please help me!


  1. cd into this dir
  1. `lein cljsbuild auto`; leave this running during entire work session
  1. `nohup LightTable &`
  1. in LightTable window, View->Commands, then type "Add Connection".  Choose the "External Browser"
     option, note the port number it mentions
  1. in LightTable, open `resources/public/index.html` and change the port number to the one
     you noted in the previous step
  1. in browser, open http://localhost/~mbp/crossviz/resources/public, or refresh the page
     if it was already open
  1. open `src/crossviz/scratch.cljs` in LightTable. This file contains experimental code
     that doesn't get compiled or executed by default, but you can now execute forms in this
     file in LightTable by putting the cursor at the end of a form and hitting Ctrl-Enter.
     The first thing you should do is execute the `ns` form at the top of the file.  Note
     that nothing in this file is executed unless/until you do so manually, and even then,
     only one form at a time. So you can't assume defs or defns have been executed until
     you execute them.
     
     You'll need to re-execute the `ns` form at the top of the file if/when you 
     trigger a recompilation by saving one of the other cljs files in the project
     (e.g. `core.cljs`).
