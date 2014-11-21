---
layout: post
title: "Depending on Other Atom Packages"
date: "2014-11-21 12:47"
---

###The problem

In making [my first Atom package](/2014-11-20-make-atom-package/) I kind of had a crash course in package management. There were npm modules I had to depend on, sure, and this was [outlined in github's tutorial](https://atom.io/docs/v0.150.0/creating-a-package#packagejson); you just stick the modules and versions you want in the `dependencies` object in `package.json`.

There was no way to include dependencies on *other Atom packages*, however, and the original implementation of my pdf converter required the [markdown-preview package](https://github.com/atom/markdown-preview/) to get  HTML (though this dependency was later removed).

There were [other people](https://discuss.atom.io/t/depending-on-other-packages/2360) who had the same problem, and without a built-in solution or a consistent workaround, it was impossible to programmatically force users to install packages the same way npm modules were installed automatically.

###The solution?

While the issue is still not completely solved, I took a smack at it by making [an npm module](https://www.npmjs.org/package/atom-package-dependencies) that checks dependencies on other Atom packages, and installs what's missing.

It works fine for me right now, though there are a couple features absent that make it less smooth for devs who are used to npm's way of including dependencies.

#####Issues
Ultimately, I would like to mirror npm's behaviour of
specifying a package/version, and installing it if it isn't present.
The problem with this is that Atom packages are installed in a different way than npm modules; they are placed in a main directory `.../.atom/packages/some-atom-pack` instead of a subdirectory `.../this-package/node_modules/some-npm-module`.
This means that installing a different version of an Atom package will overwrite the existing version in `.atom/packages/`, [so if two packages depend on separate versions of some package, there is a conflict](https://github.com/travs/atom-package-dependencies/issues/2).

There are several options to deal with this, like including the version name of a package in the installation like `.atom/packages/markdown-preview@0.1.1/`, but this could get cluttered, and how would Atom know which package should be active if there are several instances?

Another solution could be to create an `atom_packages` subdirectory in packages with those dependencies, similar to the `node_modules` subdirectory. To reduce weight, this could be performed only when the depended-on package results in a version conflict with the installed version of the package.

In any case, I hope that the community finds this package useful in developing further packages for Atom, and can suggest improvements for it that I have not yet conceived of.
