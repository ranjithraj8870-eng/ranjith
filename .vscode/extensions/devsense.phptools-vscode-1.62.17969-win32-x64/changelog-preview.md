## 1.62.17969 (October 09, 2025)

### Tests Code Coverage

We're introducing support for tests [_Code Coverage_](https://docs.devsense.com/vscode/test-explorer/#code-coverage). Try it now, navigate to _Testing_ panel, and click _Run Tests with Coverage_ button. Code coverage will appear in _Testing_ panel, _Explorer_ panel, and also right in your code.

![code coverage button](https://docs.devsense.com/vscode/imgs/code-coverage-start-button.png)

![code coverage](https://raw.githubusercontent.com/DEVSENSE/phptools-docs/refs/heads/master/docs/vscode/imgs/code-coverage-results-explorer.png)

![code coverage](https://raw.githubusercontent.com/DEVSENSE/phptools-docs/refs/heads/master/docs/vscode/imgs/code-coverage-visual.png)

> The feature relies on PHPUnit/Para/Pest functionality - it runs the tests using appropriate command line arguments and displays the coverage information conveniently right in VSCode. Please make sure, your `phpunit.xml` configuration contains `<source>` element. For troubleshooting, watch the _OUTPUT_ window / _PHP (Test Explorer)_ .

### More Features

- `@see` in mouse tooltip contains clickable links to the referenced symbols, if possible.
- `@see` in source code has semantically colorized symbols.
- **PHP 8.5** language level, pipe operator (`|>`) and basic checks.
- Validation of `enum` declarations ([#926](https://github.com/DEVSENSE/phptools-docs/issues/926)).
- Check for implicitly nullable parameters (deprecated in PHP &gt;= 8.4).
- When running all tests with several test suites, only one process is created now.

## 1.61.17926 (September 23, 2025)

### Improvements

- Behavior of `"search.exclude"` is unified across _Find all references_, _Code Lenses_, _Find Implementations_, _Symbols in Workspace_.
- Diagnostic for `new` member call without parentheses on PHP &lt;8.4.
- Pest functions respect the new `$this`. Related to any parameters annotated with `@param closure($this)` or `@param-closure-this` ([#918](https://github.com/DEVSENSE/phptools-docs/issues/918)).
- Diagnostic for unreachable match arm ([#919](https://github.com/DEVSENSE/phptools-docs/issues/919)).
- Changes how completion of function parameter snippets work, which complies with language server protocol and avoids unnecessary warnings by VSCode ([#909](https://github.com/DEVSENSE/phptools-docs/issues/909)).

### PHPUnit, Pest, and Data Sets

We are introducing new features to the _Test Explorer_: Support for newer paratest, experimental support for Pest, and support for data sets right in the Test Explorer UI.

![data sets in Test Explorer](https://raw.githubusercontent.com/DEVSENSE/phptools-docs/master/docs/vscode/imgs/testexplorer-datasets.png)

### Fixes

- Fixed overload checks and quick fix to implement missing abstract methods ([#2392](https://community.devsense.com/d/2392)).
- Fixed unwanted space after `[` on the new line in array initializers ([#923](https://github.com/DEVSENSE/phptools-docs/issues/923)).
- Spaces are added for lambdas when `php.format.rules.spaceWithinDeclParens` is enabled ([#922](https://github.com/DEVSENSE/phptools-docs/issues/922)).
- Fixed _Go To Definition_ to a class symbol in PHP manual.

## 1.60.17873 (Sep 2, 2025)

### Fixes

- Parameters completion snippet (setting `php.completion.parameters` == `"parameters"`) has default parameter values as it should have.
- Fixes autocomplete in the inline CSS and script tags [#914](https://github.com/DEVSENSE/phptools-docs/issues/914)

## 1.60.17845 (Aug 23, 2025)

### Improvements

- Checking invalid PHP configuration or configuration that may break debugging; all the warnings are listed in `OUTPUT` / `PHP` log.
- Type inferring inside `trait` has been improved, so members after `static::`, `self::`, `parent::` are mostly resolved. The editor tracks all uses of given `trait`, and it also looks at `@extends` and `@mixin` annotations.

### Debug

Fixed an issue where some breakpoints were incorrectly marked as unverified.

### Fixes

- `$this` in lambda functions with `@closure-this` or `@param callable(TYPE $this)` is annotated with correct type in tooltips.
- "Override abstracts" code action generates correct type namespaces.
- Correctly resolves `@method static static` tag.
- Removed unnecessary parentheses around complex type names in tool tips.
- Correctly resolves `self` and `static` inside `trait`.

## 1.60.17803 (Aug 14, 2025)

### Simplify `&&` Code Action

Long conditions with call chains `->` and and operator `&&` can be simplified now to a single call chain with `?->`.

### Improvements

Various type inferring improvements has been made based on user's feedback.

Newly, methods called through magic `__call()` are annotated with `PHP6615` diagnostic. This shows up in a tool-tip and the in the editor. The new diagnostic helps with unintended wrong method calls.

![unintended method call](https://raw.githubusercontent.com/DEVSENSE/phptools-docs/master/docs/vscode/imgs/err-call-via-magic.png)

### Fixes

- Fixed navigation for symbols in current file.
- Fixed navigation to symbols in PHAR files.
- Fixed `"php.problems.exclude"` setting with simple `"/"` glob pattern.
- Fixed `array` type information causing wrong types in functions in `/vendor/`.
- Fixed wrongly detected unused imports of classes used in property hookes.
- Fixed analysis of `method_exists()` with ambiguous `$class_or_object` argument.
- Improved methods check in case of ambiguously inferred type.

## 1.59.17706 (July 29, 2025) [...]
## 1.59.17685 (July 23, 2025) [...]
## 1.59.17674 (July 18, 2025) [...]
## 1.59.17515 (June 23, 2025) [...]
## 1.59.17478 (June 15, 2025) [...]
## 1.58.17223 (May 2, 2025) [...]
## 1.57.17158 (April 11, 2025) [...]
## 1.57.17031 (March 25, 2025) [...]
## 1.57.16971 (March 12, 2025) [...]
## 1.56.16884 (February 19, 2025) [...]
## 1.56.16853 (February 12, 2025) [...]
## 1.55.16740 (January 22, 2025) [...]
## 1.55.16685 (January 15, 2025) [...]
## 1.54.16574 (December 23, 2024) [...]
## 1.54.16480 (December 10, 2024) [...]
## 1.53.16379 (November 19, 2024) [...]
## 1.53.16338 (November 12, 2024) [...]
## 1.52.16273 (October 30, 2024) [...]
## 1.52.16226 (October 21, 2024) [...]
## 1.51.16099 (September 26, 2024) [...]
## 1.51.15986 (September 10, 2024) [...]
## 1.50.15906 (August 20, 2024) [...]
## 1.50.15872 (August 13, 2024) [...]
## 1.49.15728 (July 8, 2024) [...]
## 1.48.15635 (June 16, 2024) [...]
## 1.47.15512 (May 28, 2024) [...]
## 1.46.15409 (May 9, 2024) [...]
## 1.45.15272 (April 11, 2024) [...]
## 1.45.15260 (April 8, 2024) [...]
## 1.45.15192 (March 26, 2024) [...]
## 1.45.15145 (March 14, 2024) [...]
## 1.45.15061 (February 27, 2024) [...]
## 1.44.14997 (February 14, 2024) [...]
## 1.44.14950 (February 7, 2024) [...]
## 1.44.14925 (February 5, 2024) [...]
## 1.43.14858 (January 24, 2024) [...]
## 1.43.14756 (January 15, 2024) [...]
## 1.42.14626 (December 30, 2023) [...]
## 1.42.14434 (December 12, 2023) [...]
## 1.41.14263 (November 14, 2023) [...]
## 1.40.14103 (October 18, 2023) [...]
## 1.39.13943 (September 20, 2023) [...]
## 1.38.13918 (September 15, 2023) [...]
## 1.38.13779 (September 1, 2023) [...]
## 1.38.13759 (August 30, 2023) [...]
## 1.37.13534 (August 4, 2023) [...]
## 1.36.13417 (July 1, 2023) [...]
## 1.35.13327 (June 20, 2023) [...]
## 1.34.13295 (June 15, 2023) [...]
## 1.34.13120 (May 5, 2023) [...]
## 1.33.12934 (April 8, 2023) [...]
## 1.33.12924 (April 05, 2023) [...]
## 1.32.12895 (March 28, 2023) [...]
## 1.31.12821 (March 20, 2023) [...]
## 1.31.12740 (March 4, 2023) [...]
## 1.30.12484 (February 10, 2023) [...]
## 1.30.12450 (February 9, 2023) [...]
## 1.30.12417 (February 7, 2023) [...]
## 1.29.12304 (January 29, 2023) [...]
## 1.28.12200 (January 21, 2023) [...]
## 1.27.12010 (January 9, 2023) [...]
## 1.26.11866 (January 3, 2023) [...]
## 1.26.11753 (December 28, 2022) [...]
## 1.25.11652 (December 21, 2022) [...]
## 1.25.11537 (December 11, 2022) [...]
## 1.24.11420 (December 1, 2022) [...]
## 1.23.11234 (November 10, 2022) [...]
## 1.22.11089 (October 31, 2022) [...]
## 1.21.10985 (October 23, 2022) [...]
## 1.20.10937 (October 19, 2022) [...]
## 1.19.10893 (October 16, 2022) [...]
## 1.18.10692 (September 30, 2022) [...]
## 1.17.10641 (September 26, 2022) [...]
## 1.15.10535 (September 14, 2022) [...]
## 1.14.10471 (September 7, 2022) [...]
## 1.13.10390 (August 30, 2022) [...]
## 1.13.10378 (August 29, 2022) [...]
## 1.13.10301 (August 16, 2022) [...]
## 1.13.10239 (August 11, 2022) [...]
## 1.12.10140 (August 4, 2022) [...]
## 1.12.10040 (July 26, 2022) [...]
## 1.12.10022 (July 25, 2022) [...]
## 1.12.9985 (July 20, 2022) [...]
## 1.11.9762 (July 1, 2022) [...]
## 1.11.9761 (June 29, 2022) [...]
## 1.10.9721 (June 25, 2022) [...]
## 1.10.9716 (June 25, 2022) [...]
## 1.9.9585 (June 7, 2022) [...]
## 1.9.9479 (May 25, 2022) [...]
## 1.9.9277 (April 29, 2022) [...]
## 1.8.8970 (March 23, 2022) [...]
## 1.7.8766 (March 8, 2022) [...]
## 1.7.8717 (March 4, 2022) [...]
## 1.7.8637 (February 26, 2022) [...]
## 1.7.8627 (February 25, 2022) [...]
## 1.6.8588 (February 19, 2022) [...]
## 1.6.8479 (February 11, 2022) [...]
## 1.6.8448 (February 10, 2022) [...]
## 1.6.8324 (January 28, 2022) [...]
## 1.5.8292 (January 25, 2022) [...]
## 1.5.8280 (January 24, 2022) [...]
## 1.5.8204 (January 17, 2022) preview [...]
## 1.4.8059 (December 20, 2021) preview [...]
## 1.4.8033 (December 17, 2021) preview [...]
## 1.4.7597 (September 30, 2021) preview [...]
## 1.4.7534 (September 21, 2021) preview [...]
## 1.4.7520 (September 19, 2021) preview [...]
## 1.4.7494 (September 15, 2021) preview [...]
## 1.4.7449 (September 7, 2021) preview [...]
## 1.4.7295 (August 17, 2021) preview [...]
## 1.4.7254 (August 15, 2021) preview [...]
## 1.4.6982 (July 15, 2021) preview [...]
## 1.4.6842 (June 22, 2021) preview [...]
## 1.4.6822 (June 19, 2021) preview [...]
## 1.4.6762 (June 07, 2021) preview [...]
## 1.3.6645 (May 25, 2021) preview [...]
## 1.3.6632 (May 21, 2021) preview [...]
## 1.3.6616 (May 21, 2021) preview [...]
## 1.2.6549 (May 12, 2021) preview [...]
## 1.2.6469 (April 24, 2021) preview [...]
## 1.2.6305 (April 04, 2021) preview [...]
## 1.2.6273 (March 30, 2021) preview [...]
## 1.2.6177 (March 17, 2021) preview [...]
## 1.2.6021 (Feb 17, 2021) preview [...]
## 1.2.5988 (Feb 10, 2021) preview [...]
## 1.2.5973 (Feb 08, 2021) preview [...]
## 1.2.5931 (Jan 31, 2021) preview [...]
## 1.2.5887 (Jan 23, 2021) preview [...]
## 1.2.5843 (Jan 18, 2021) preview [...]
## 1.2.5783 (Jan 04, 2021) preview [...]
## 1.1.5686 (Dec 23, 2020) preview [...]
## 1.1.5620 (Dec 12, 2020) preview [...]
## 1.1.5595 (Dec 04, 2020) preview [...]
## 1.1.5532 (Nov 21, 2020) preview [...]
## 1.0.5403 (Oct 28, 2020) preview [...]
## 1.0.5342 (Oct 20, 2020) preview [...]
## 1.0.5264 (Sep 30, 2020) preview [...]
## 1.0.5229 (Sep 22, 2020) preview [...]
## 1.0.5153 (Aug 28, 2020) preview [...]
## 1.0.5087 (Aug 17, 2020) preview [...]
## 1.0.5044 (Aug 11, 2020) preview [...]
## 1.0.5029 (Aug 07, 2020) preview [...]
## 1.0.5015 (Aug 06, 2020) preview [...]
## 1.0.4975 (July 29, 2020) preview [...]
## 1.0.4934 (July 19, 2020) preview [...]
## 1.0.4908 (July 13, 2020) preview [...]
## 1.0.4698 (May 19, 2020) preview [...]
## 1.0.4666 (May 06, 2020) preview [...]
## 1.0.4654 (May 05, 2020) preview [...]
## 1.0.4608 (April 17, 2020) preview [...]
## 1.0.4394 (January 23, 2020) preview [...]
## 1.0.4277 (December 10, 2019) preview [...]
## 1.0.4229 (November 22, 2019) preview [...]
## 1.0.4187 (November 10, 2019) preview [...]
## 1.0.4168 (November 4, 2019) preview [...]
## 1.0.4145 (October 24, 2019) preview [...]
## 1.0.4009 (September 23, 2019) preview [...]
## 1.0.3951 (September 9, 2019) preview [...]
## 1.0.3936 (September 5, 2019) preview [...]
## 1.0.3774 (August 1, 2019) preview [...]
## 1.0.3748 (July 24, 2019) preview [...]
## 1.0.3703 (July 17, 2019) preview [...]
## 1.0.3645 (July 11, 2019) preview [...]
## 1.0.3603 (July 8, 2019) preview [...]
## 1.0.3593 (July 5, 2019) preview [...]
## 1.0.3574 (July 2, 2019) preview [...]
## 1.0.3547 (June 27, 2019) preview [...]
## 1.0.3525 (June 24, 2019) preview [...]
## 1.0.3507 (June 22, 2019) preview [...]
## 1.0.3483 (June 17, 2019) preview [...]
## 1.0.3471 (June 12, 2019) preview [...]
## 1.0.3435 (May 28, 2019) preview [...]
## 1.0.3428 (May 27, 2019) preview [...]
## 1.0.3386 (May 9, 2019) preview [...]
## 1.0.3348 (Apr 23, 2019) preview [...]
## 1.0.3241 (Mar 4, 2019) preview [...]
## 1.0.3230 (Feb 27, 2019) preview [...]
## 1.0.3202 (Feb 20, 2019) preview [...]
## 1.0.3185 (Feb 14, 2019) preview [...]
## 1.0.3174 (Feb 12, 2019) preview [...]
## 1.0.3058 (Dec 30, 2018) preview [...]
## 1.0.3031 (Dec 3, 2018) preview [...]
## 1.0.3003 (Nov 26, 2018) preview [...]
## 1.0.2930 (Nov 3, 2018) preview [...]
## 1.0.2915 (Oct 30, 2018) preview [...]
## 1.0.2895 (Oct 23, 2018) preview [...]
## 1.0.2802 (Oct 11, 2018) preview [...]
## 1.0.2765 (Oct 8, 2018) preview [...]
## 1.0.2738 (Oct 3, 2018) preview [...]
## 1.0.2681 (Sep 27, 2018) preview [...]
## 1.0.2590 (Sep 14, 2018) preview [...]

