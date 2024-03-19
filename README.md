Source text for a document comparing dPID to DSI
================================================

This source text has been set up on GitHub to automatically generate a Baseprint
snapshot and HTML/PDF preview by following the steps described in the tutorial
[try.perm.pub/tutorial/author_via_github](https://try.perm.pub/tutorial/author_via_github).

The automatically generated Baseprint snapshot is saved in the
[`baseprint` directory on the `autobaseprint` branch](https://github.com/castedo/dpid-vs-dsi/tree/autobaseprint/baseprint).

The HTML/PDF preview generated from the Baseprint snapshot is automatically pushed to
[castedo.github.io/dpid-vs-dsi/](https://castedo.github.io/dpid-vs-dsi/).


Authoring this source into a Baseprint snapshot
-----------------------------------------------

See [try.perm.pub/tutorial/author_locally](https://try.perm.pub/tutorial/author_locally/)
for a tutorial on authoring a Baseprint snapshot locally.

The `pandocin.yaml` is a Pandoc defaults file that can be used with
[Baseprinter](https://try.perm.pub/baseprinter) as such:

```
baseprinter -d pandocin.yaml -b=baseprint --outdir=preview --skip-pdf
```

