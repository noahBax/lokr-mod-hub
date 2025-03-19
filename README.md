# Here are my suggestions on how the LOKR Mod Hub should work

This is where the mod manager will download from. The mod manager acts as a cart
that you can select different mod packs to download

 - First it will download this repository
  
 - This repository is a collection of mod "packs". Not really mod packs, but for
   things like the New Heroes mod which is really a collection of separate mods
   (Assassin, Cleric, etc.), you can think of this repository as a collection of
   mod packs.

   - Each mod pack contains a folder or list of folders that are the individual
     mods themselves.

 - The mod manager looks at the `mod_inventory.json` file.
  
   - The `mod_inventory.json` says what mods packs (folders) are available and
     what folders/files are necessary (i.e. the dll and `Resources` folder right
     now) to have to run mods at all.

    - Inside of each mod folder itself, is another json file named
      `mod_parts.json` which says "here are the individual mods that can be
      added to your cart". It also says which mods are *necessary*.
	  
	  - So for example, the New Heroes mod has Assassin, Cleric, etc. that are
	    individual mods and the `new_heroes_lib` folder is *mandatory*

	  - For mod-packs that don't have multiple mods, the `mod_parts.json` will
	    just specify there is one mod and that it is mandatory.

 - When the user "checks out" their cart, the mod manager installs the selected
   mod folders into the `legends_data` directory.

The folder structure is a demo of some sort