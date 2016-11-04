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

<link
	rel='stylesheet'
	href='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css'
	x-sri-fallback='/bootstrap.min.css'
	integrity='sha256-8EtRe6XWoFEEhWiaPkLawAD1FkD9cbmGgEy6F46uQqU='
	crossorigin='anonymous'
></link>
```

In the event that the resource located at the `src` or `href` fails to validate against the specified hash, the backup resource at `x-sri-fallback` will be fetched and validated against the same hash prior to its execution.

Browser compatibility: sri-fallback will work in any browser with `MutationObserver` support. For older browsers, you'll need a polyfill like [this one](https://github.com/megawac/MutationObserver.js).
