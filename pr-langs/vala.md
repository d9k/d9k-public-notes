# #Vala

## #CLI

- :symbols: [Draft: Add CLI template by colinkiama · Pull Request #17 · vala-lang/valdo](https://github.com/vala-lang/valdo/pull/17/files)

## Learn Vala in Y Minutes

- https://learnxinyminutes.com/vala/

- `string?` - possible null value
- Default access modifier is private.
- Vala methods cannot be overloaded. Use default argument values
- getters/setters generation (`private set`)
- All GLib.Objects have a signal `notify(field_name)` emitted when a property changes.
- `rabbit.notify["age"].connect((s, p) => stdout.printf("Property '%s' has changed!\n", p.age)`
- `override`, `virtual`, `abstract`

## Memory management

- [Projects/Vala/ReferenceHandling – GNOME Wiki Archive](https://wiki.gnome.org/Projects/Vala/ReferenceHandling)
	- `weak` keyword

## C interop

- need bindings