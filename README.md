# sri-fallback

Implementation of a non-standard "x-sri-fallback" attribute for use with Subresource Integrity.

Example usage:

```
<script
	src='https://ajax.googleapis.com/ajax/libs/jquery/2.1.4/jquery.min.js'
	x-sri-fallback='/jquery.min.js'
	integrity='sha256-ImQvICV38LovIsvla2zykaCTdEh1Z801Y+DSop91wMU='
	crossorigin='anonymous'
></script>
```

In the event that the resource located at the `src` fails to validate against the specified hash, the backup resource at `x-sri-fallback` will be fetched and validated against the same hash prior to its execution. Also works in exactly the same manner with `<link>` CSS imports.
