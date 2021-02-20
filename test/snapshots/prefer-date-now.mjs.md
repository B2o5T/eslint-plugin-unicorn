# Snapshot report for `test/prefer-date-now.mjs`

The actual snapshot is saved in `prefer-date-now.mjs.snap`.

Generated by [AVA](https://avajs.dev).

## Invalid #1
      1 | const ts = new Date().getTime();

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = new Date().getTime();␊
        |                       ^^^^^^^ Prefer `Date.now()` over `Date#getTime()`.␊
    `

## Invalid #2
      1 | const ts = (new Date).getTime();

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = (new Date).getTime();␊
        |                       ^^^^^^^ Prefer `Date.now()` over `Date#getTime()`.␊
    `

## Invalid #3
      1 | const ts = (new Date()).getTime();

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = (new Date()).getTime();␊
        |                         ^^^^^^^ Prefer `Date.now()` over `Date#getTime()`.␊
    `

## Invalid #4
      1 | const ts = new Date().valueOf();

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = new Date().valueOf();␊
        |                       ^^^^^^^ Prefer `Date.now()` over `Date#valueOf()`.␊
    `

## Invalid #5
      1 | const ts = (new Date).valueOf();

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = (new Date).valueOf();␊
        |                       ^^^^^^^ Prefer `Date.now()` over `Date#valueOf()`.␊
    `

## Invalid #6
      1 | const ts = (new Date()).valueOf();

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = (new Date()).valueOf();␊
        |                         ^^^^^^^ Prefer `Date.now()` over `Date#valueOf()`.␊
    `

## Invalid #7
      1 | const ts = /* 1 */ Number(/* 2 */ new /* 3 */ Date( /* 4 */ ) /* 5 */) /* 6 */

> Output

    `␊
      1 | const ts = /* 1 */ Date.now() /* 6 */␊
    `

> Error 1/1

    `␊
    > 1 | const ts = /* 1 */ Number(/* 2 */ new /* 3 */ Date( /* 4 */ ) /* 5 */) /* 6 */␊
        |                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Prefer `Date.now()` over `Number(new Date())`.␊
    `

## Invalid #8
      1 | const tsBigInt = /* 1 */ BigInt(/* 2 */ new /* 3 */ Date( /* 4 */ ) /* 5 */) /* 6 */

> Output

    `␊
      1 | const tsBigInt = /* 1 */ BigInt(/* 2 */ Date.now() /* 5 */) /* 6 */␊
    `

> Error 1/1

    `␊
    > 1 | const tsBigInt = /* 1 */ BigInt(/* 2 */ new /* 3 */ Date( /* 4 */ ) /* 5 */) /* 6 */␊
        |                                         ^^^^^^^^^^^^^^^^^^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #9
      1 | const ts = + /* 1 */ new Date;

> Output

    `␊
      1 | const ts = Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = + /* 1 */ new Date;␊
        |            ^^^^^^^^^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #10
      1 | const ts = - /* 1 */ new Date();

> Output

    `␊
      1 | const ts = - /* 1 */ Date.now();␊
    `

> Error 1/1

    `␊
    > 1 | const ts = - /* 1 */ new Date();␊
        |                      ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #11
      1 | const ts = new Date() - 0

> Output

    `␊
      1 | const ts = Date.now() - 0␊
    `

> Error 1/1

    `␊
    > 1 | const ts = new Date() - 0␊
        |            ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #12
      1 | const foo = bar - new Date

> Output

    `␊
      1 | const foo = bar - Date.now()␊
    `

> Error 1/1

    `␊
    > 1 | const foo = bar - new Date␊
        |                   ^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #13
      1 | const foo = new Date() * bar

> Output

    `␊
      1 | const foo = Date.now() * bar␊
    `

> Error 1/1

    `␊
    > 1 | const foo = new Date() * bar␊
        |             ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #14
      1 | const ts = new Date() / 1

> Output

    `␊
      1 | const ts = Date.now() / 1␊
    `

> Error 1/1

    `␊
    > 1 | const ts = new Date() / 1␊
        |            ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #15
      1 | const ts = new Date() % Infinity

> Output

    `␊
      1 | const ts = Date.now() % Infinity␊
    `

> Error 1/1

    `␊
    > 1 | const ts = new Date() % Infinity␊
        |            ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #16
      1 | const ts = new Date() ** 1

> Output

    `␊
      1 | const ts = Date.now() ** 1␊
    `

> Error 1/1

    `␊
    > 1 | const ts = new Date() ** 1␊
        |            ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #17
      1 | const zero = (new Date(/* 1 */) /* 2 */) /* 3 */ - /* 4 */new Date

> Output

    `␊
      1 | const zero = (Date.now() /* 2 */) /* 3 */ - /* 4 */Date.now()␊
    `

> Error 1/2

    `␊
    > 1 | const zero = (new Date(/* 1 */) /* 2 */) /* 3 */ - /* 4 */new Date␊
        |               ^^^^^^^^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

> Error 2/2

    `␊
    > 1 | const zero = (new Date(/* 1 */) /* 2 */) /* 3 */ - /* 4 */new Date␊
        |                                                           ^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #18
      1 | foo -= new Date()

> Output

    `␊
      1 | foo -= Date.now()␊
    `

> Error 1/1

    `␊
    > 1 | foo -= new Date()␊
        |        ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #19
      1 | foo *= new Date()

> Output

    `␊
      1 | foo *= Date.now()␊
    `

> Error 1/1

    `␊
    > 1 | foo *= new Date()␊
        |        ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #20
      1 | foo /= new Date

> Output

    `␊
      1 | foo /= Date.now()␊
    `

> Error 1/1

    `␊
    > 1 | foo /= new Date␊
        |        ^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #21
      1 | foo %= new Date()

> Output

    `␊
      1 | foo %= Date.now()␊
    `

> Error 1/1

    `␊
    > 1 | foo %= new Date()␊
        |        ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `

## Invalid #22
      1 | foo **= new Date()

> Output

    `␊
      1 | foo **= Date.now()␊
    `

> Error 1/1

    `␊
    > 1 | foo **= new Date()␊
        |         ^^^^^^^^^^ Prefer `Date.now()` over `new Date()`.␊
    `