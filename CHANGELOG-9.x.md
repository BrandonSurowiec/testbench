# Changes for 9.x

This changelog references the relevant changes (bug and security fixes) done to `orchestra/testbench`.

## 9.1.1

Released: 2024-06-01

### Changes

* Update minimum support for Testbench Core v9.1.2+. ([v9.1.0...v9.1.2](https://github.com/orchestral/testbench-core/compare/v9.1.0...v9.1.2))

#### Testbench Changes

##### Changes

* Utilise `Orchestra\Testbench\package_path()` function instead of `TESTBENCH_WORKING_PATH` constant.
* Update configuration to match Laravel Framework v11.8.0,

##### Fixes

* Fixes `Orchestra\Testbench\Attributes\RequiresLaravel` attribute usage.

## 9.1.0

Released: 2024-05-21

### Changes

* Update minimum support for Testbench Core v9.1.0+. ([v9.0.13...v9.1.0](https://github.com/orchestral/testbench-core/compare/v9.0.13...v9.1.0))

#### Testbench Changes

##### Changes

* Uses `TESTBENCH_WORKING_PATH` from environment variable before fallback to `getcwd()`.
* PHPStan Improvements.
* Add support for PHPUnit 11.1.
* Update skeleton to match v11.0.7.

##### Fixes

* Fixes routing registration using macro with Workbench.

## 9.0.4

Released: 2024-04-16

### Changes

* Update minimum support for Testbench Core v9.0.13+. ([v9.0.9...v9.0.13](https://github.com/orchestral/testbench-core/compare/v9.0.9...v9.0.13))

#### Testbench Changes

##### Changes

* Allows `Orchestra\Testbench\remote` to accept `$env` with either `array` or `string`.
* Includes `TESTBENCH_PACKAGE_REMOTE=true` when running command using `Orchestra\Testbench\remote`.
* Flush Static Improvements.
* Revert setting `workbench` environment variable when Testbench CLI is used outside of testing. 

##### Fixes

* Fixes `serve` command.
* Fixes `runningInUnitTests()` returning `true` when not running tests via Testbench CLI.

## 9.0.3

Released: 2024-03-27

### Changes

* Update minimum support for Testbench Core v9.0.9+. ([v9.0.7...v9.0.9](https://github.com/orchestral/testbench-core/compare/v9.0.7...v9.0.9))
* Update minimum support for Laravel Framework `11.1.0`.

#### Testbench Changes

##### Changes

* Add support for `HASH_VERIFY` environment variables.

##### Fixes

* Force reset `RefreshDatabaseState` when using `LazilyRefreshDatabase` with SQLite `:in-memory:` database connections.

## 9.0.2

Released: 2024-03-25

### Changes

* Update minimum support for Testbench Core v9.0.7+. ([v9.0.6...v9.0.7](https://github.com/orchestral/testbench-core/compare/v9.0.6...v9.0.7))

#### Testbench Changes

##### Fixes

* Fixes `RefreshDatabase` to be executed on `tearDown()` only limited when ad-hoc migrations was added during test.

## 9.0.1

Released: 2024-03-19

### Changes

* Update minimum support for Testbench Core v9.0.6+. ([v9.0.1...v9.0.6](https://github.com/orchestral/testbench-core/compare/v9.0.1...v9.0.6))

#### Testbench Changes

##### Changes

* Run `ResetRefreshDatabaseState` via `tearDownTheTestEnvironmentUsingTestCase()` method.
* Check against `RefreshDatabaseState::$migrated` and `RefreshDatabaseState::$lazilyRefreshed` before loading migration paths to the instance of `migrator`.
* Update skeleton to match v11.0.3.
* Revert default skeleton database collations to `utf8mb4_unicode_ci`.

##### Fixes

* Fixes `beforeApplicationDestroyed()` usage on `loadLaravelMigrations()` method.
* Fixes `RefreshDatabase` usage does not reset the database migrations between tests.
* Fixes `class_implements()` should only be executed if the Attribute class exists.
* Testbench CLI should prioritize application kernels defined via `bootstrap/app.php` when configured using a custom skeleton.

## 9.0.0

Released: 2024-03-13

### Added

* Added support for PHPUnit 11.

### Changes

* Update support for Laravel Framework v11.
* Increase minimum PHP version to 8.2 and above (tested with 8.2 and 8.3).

### Deprecated

* Deprecate `Orchestra\Testbench\Concerns\HandlesAnnotations` in line with PHPUnit removal support for meta-comment support using annotation.

### Removed

* Remove deprecated `Orchestra\Testbench\Concerns\Database\HandlesConnections` trait.
* Removed deprecated `create-sqlite-db` and `drop-sqlite-db` standalone commands.

