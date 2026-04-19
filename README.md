<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# atleastnd

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Convert a list of values (scalars and/or ndarrays) to ndarrays having at least a specified number of dimensions.

<section class="intro">

</section>

<!-- /.intro -->



<section class="usage">

## Usage

```javascript
import atleastnd from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-atleastnd@esm/index.mjs';
```

#### atleastnd( ndims, arrays )

Converts a list of values (scalars and/or ndarrays) to ndarrays having at least a specified number of dimensions.

```javascript
import array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-array@esm/index.mjs';

var x = array( [ [ [ 1.0, 2.0 ] ], [ [ 3.0, 4.0 ] ] ] );
// returns <ndarray>[ [ [ 1.0, 2.0 ] ], [ [ 3.0, 4.0 ] ] ]

var y = array( [ [ 5.0, 6.0 ], [ 7.0, 8.0 ] ] );
// returns <ndarray>[ [ 5.0, 6.0 ], [ 7.0, 8.0 ] ]

var out = atleastnd( 3, [ x, y ] );
// returns [ <ndarray>, <ndarray> ]
```

The function accepts the following arguments:

-   **ndims**: minimum number of dimensions.
-   **arrays**: array-like object containing a list of scalars and/or ndarrays.

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   If a provided ndarray has fewer dimensions than `ndims`, the function prepends singleton dimensions, and the returned ndarray is a view on the input ndarray data buffer.

-   The returned ndarray is a "base" [ndarray][@stdlib/ndarray/base/ctor], and, thus, the returned [ndarray][@stdlib/ndarray/base/ctor] does not perform bounds checking or afford any of the guarantees of the non-base [ndarray][@stdlib/ndarray/ctor] constructor. The primary intent of this function is to broadcast an ndarray-like object within internal implementations and to do so with minimal overhead.

-   If provided a scalar value (i.e., a non-ndarray) and that value

    -   is a number, the returned ndarray will have the [default][@stdlib/ndarray/defaults] real-valued floating-point data type.
    -   is a boolean, the returned ndarray will have the [default][@stdlib/ndarray/defaults] boolean data type.
    -   is a complex number object of a known data type, the data type of the returned ndarray will be the same as the provided value.
    -   is a complex number object of an unknown data type, the returned ndarray will have the [default][@stdlib/ndarray/defaults] complex-valued floating-point data type.
    -   is any other value type, the returned ndarray will have a `'generic'` data type.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="module">

import discreteUniform from 'https://cdn.jsdelivr.net/gh/stdlib-js/random-discrete-uniform@esm/index.mjs';
import ndarray2array from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-to-array@esm/index.mjs';
import atleastnd from 'https://cdn.jsdelivr.net/gh/stdlib-js/ndarray-base-atleastnd@esm/index.mjs';

var x = discreteUniform( [ 2, 2, 2 ], -100, 100 );
// returns <ndarray>

var y = discreteUniform( [ 5, 2 ], -100, 100 );
// returns <ndarray>

var out = atleastnd( 3, [ x, y ] );
// returns [ <ndarray>, <ndarray> ]

console.log( ndarray2array( out[ 0 ] ) );
console.log( ndarray2array( out[ 1 ] ) );

</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/ndarray-base-atleastnd.svg
[npm-url]: https://npmjs.org/package/@stdlib/ndarray-base-atleastnd

[test-image]: https://github.com/stdlib-js/ndarray-base-atleastnd/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/ndarray-base-atleastnd/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/ndarray-base-atleastnd/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/ndarray-base-atleastnd?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/ndarray-base-atleastnd.svg
[dependencies-url]: https://david-dm.org/stdlib-js/ndarray-base-atleastnd/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/ndarray-base-atleastnd/tree/deno
[deno-readme]: https://github.com/stdlib-js/ndarray-base-atleastnd/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/ndarray-base-atleastnd/tree/umd
[umd-readme]: https://github.com/stdlib-js/ndarray-base-atleastnd/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/ndarray-base-atleastnd/tree/esm
[esm-readme]: https://github.com/stdlib-js/ndarray-base-atleastnd/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/ndarray-base-atleastnd/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/ndarray-base-atleastnd/main/LICENSE

[@stdlib/ndarray/ctor]: https://github.com/stdlib-js/ndarray-ctor/tree/esm

[@stdlib/ndarray/base/ctor]: https://github.com/stdlib-js/ndarray-base-ctor/tree/esm

[@stdlib/ndarray/defaults]: https://github.com/stdlib-js/ndarray-defaults/tree/esm

</section>

<!-- /.links -->
