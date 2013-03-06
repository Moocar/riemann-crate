[Repository](https://github.com/pallet/riemann-crate) &#xb7; [Issues](https://github.com/pallet/riemann-crate/issues) &#xb7; [API docs](http://palletops.com/riemann-crate/0.8/api) &#xb7; [Annotated source](http://palletops.com/riemann-crate/0.8/annotated/uberdoc.html)

A [pallet](http://palletops.com/) crate to install and configure
 [riemann](http://riemann.io).

### Dependency Information

```clj
:dependencies [[com.palletops/riemann-crate "0.8.0-alpha.1"]]
```

### Releases

<table>
<thead>
  <tr><th>Pallet</th><th>Crate Version</th><th>Repo</th><th>GroupId</th></tr>
</thead>
<tbody>
  <tr>
    <th>0.8.0-beta.1</th>
    <td>0.8.0-alpha.1</td>
    <td>clojars</td>
    <td>com.palletops</td>
    <td><a href='https://github.com/pallet/riemann-crate/blob/0.8.0-alpha.1/ReleaseNotes.md'>Release Notes</a></td>
    <td><a href='https://github.com/pallet/riemann-crate/blob/0.8.0-alpha.1/'>Source</a></td>
  </tr>
</tbody>
</table>

## Usage

The riemann crate provides a `server-spec` function that returns a
server-spec. This server spec will install and run the riemann server (not the
dashboard).  You pass a map of options to configure riemann.  The `:config`
value should be a form that will be output as the
[riemann configuration](http://riemann.io/howto.html).

The `server-spec` provides an easy way of using the crate functions, and you can
use the following crate functions directly if you need to.

The `settings` function provides a plan function that should be called in the
`:settings` phase.  The function puts the configuration options into the pallet
session, where they can be found by the other crate functions, or by other
crates wanting to interact with the riemann server.

The `install` function is responsible for actually installing riemann.  At
present installation from tarball url is the only supported method.
Installation from deb or rpm url would be nice to add, as these are now
available from the riemann site.

The `config` function writes the riemann configuration file, using the form
passed to the :config key in the `settings` function.

The `run` function starts the riemann server.

## License

Copyright (C) 2012, 2013 Hugo Duncan

Distributed under the Eclipse Public License.
