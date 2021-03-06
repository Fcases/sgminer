# Release news

## Version 4.2.0 - 20th May 2014

* git repo moved to [sgminer-dev](https://github.com/sgminer-dev/sgminer).
  It is now a GitHub organisation with several people having write access.
* Kernel `bufius` merger from `vertminer` (by _Bufius_).
* Set pool as idle on several stratum failure conditions (by _elbandi_).
* API response to `version` has field `CGMiner` instead of `SGMiner`
  for API client compatibility, and an additional `Miner` field (by
  _luke-jr_).
* API response to `restart` and `quit` only contains a `status` section
  and passes JSON validation (by _luke-jr_).
* API response to `devs` contains `XIntensity` and `RawIntensity` fields.
* Config file writing from TUI/API should produce a borked config less
  often.


## Version 4.1.271 - 12th April 2014

* Allow setting algorithm per-pool and initial implementation of kernel
  hot-swapping (by _mrbrdo_). Use options `pool-algorithm` (in config
  file or in CLI) or `algorithm` (config-only).
* NCurses UI `[S][W]` writes pool name and description to configuration.
* Added algorithm name to `pools` API command (by _troky_).
* NCurses UI asks for (optional) pool name, description and algorithm
  when adding pool.
* API command `addpool` allows both `url,user,pass` and
  `url,user,pass,name,desc,algo`.


## Version 4.1.242 - 7th April 2014

* There are now two mailing lists (on SourceForge), see `README.md`.
* Adaptive-N-factor algorithm support (by _Bufius_, _Zuikkis_ and
  _veox_). For details on choosing the algorithm, see
  `doc/configuration.md`.
* Allowed kernel names are no longer hard-coded. It is now possible to
  use any `.cl` file.
* Configuration parameter `poolname` has been renamed to `name`.
  `poolname` is deprecated and will be removed in a future version.
* Multiple `--name` parsing should now work as expected (by _troky_).
* `--description` configuration parameter to specify a freeform pool
  description, and `--priority` to specify the pool's priority (by
  _troky_).


## Version 4.1.153 - 14th March 2014

* Display pool URL instead of "Pool N" if no `poolname` specified.
* Incognito mode to hide user name in NCurses interface - useful for
  publishing screenshots. To enable, use `--incognito` on command line,
  `incognito` in config or `[D][I]` in NCurses interface.
* Support building in Microsoft Visual Studio 2010, perhaps other
  versions as well (by _troky_). Documentation in `winbuild/README.txt`.
* Support building in Cygwin (by _markuspeloquin_). Documentation in
  `doc/cygwin-build.txt`.
* Forward-port changes from `ckolivas/cgminer` up to 3.12.3.
* Allow setting `worksize` for kernel `zuikkis`.
* More log messages in pool handling.
* Updated `doc/FAQ.md`.
* Updated `example.conf`.


## Version 4.1.0 - 7th February 2014

* Writing configuration file from NCurses interface is broken!
* Commandline option parsing may be broken!
* MinGW building may be broken!
* Bug reporting documentation: `doc/BUGS.md`.
* Kernel selection and integration: `doc/KERNEL.md`.
* Several updates to other documentation files.
* Warn if `GPU_*` environment variables are not set.
* Maximum `intensity` lowered to 31 (anything above that gives an overflow
  anyway).
* Experimental `xintensity` setting (by _Kalroth_), see
  [commit message](https://github.com/veox/sgminer/commit/7aeae40af22e6108aab8b68a229eea25a639d650).
* Experimental `rawintensity` setting (by _Kalroth_), see
  [commit message](https://github.com/veox/sgminer/commit/d11df698d141988491494aa1f29c7d3595e9712b).
* `-v` is now a shorthand for `--verbose`, not `--vectors`.
* Default `scantime` and `expiry` changed to 7 and 28 (tests run by
  _MissedOutOnBTC_).
* Increased precision of `API_MHS`; added `API_KHS`.
* Pulled in kernels: `alexkarold`, `alexkarnew`, `psw`, `zuikkis`; renamed
  `scrypt` to `ckolivas`; all kernels now reside in directory `kernel`.
  Kernels can be chosen at startup only, by specifying `kernel`.
* Small optimisation to `ckolivas` kernel (by _gdevenyi_).
* Named pools via `poolname` (by _Kalroth_).
* Failover pool switching back delay is configurable via
  `failover-switch-delay` (by _Kalroth_).
* Pool `state`: `enabled`, `disabled`, and `hidden` (by _Joe4782_).
* Allow all pools to be set `disabled`.
* Use RPM in ADL `get-fanspeed` requests (from `bfgminer`, by _luke-jr_).
* Verbose ADL failure messages (by _Joe4782_ and _deba12_).
* Use `git` version string if available.
* Allow bypassing ADL checks during build with `--disable-adl-checks`.
* MinGW build checks (by _tonobitc_).
* Experimental Microsoft Visual Studio 2010 building support in branch
  `build-msvs2010-upd` (by _troky_).


## Version 4.0.0 - 15th January 2014

* Fork `veox/sgminer` from `ckolivas/cgminer` version 3.7.2.
* Remove code referencing SHA256d mining, FPGAs and ASICS. Leftovers most
  probably still remain.
* AMD ADL crash fix on R9 chipsets by Benjamin Herrenschmidt.
* Maximum allowed intensity increased to 42.
* Move documentation to directory `doc`.
* `--gpu-threads` support for comma-separated values by Martin Danielsen
  (_Kalroth_).
* AMD ADL SDK 5 mandatory, preparation for ADL Overdrive 6 support by
  _Kalroth_.
* Allow changing TCP keepalive packet idle time using `--tcp-keepalive`.
* Automatic library presence detection by `configure`.
* `--scrypt` option removed (no other choice now).
* `--vectors` option removed (current kernel only supports 1).
* Display per-GPU reject percentage instead of absolute values by _Kalroth_.
* Do not show date in log by default (switch with `--log-show-date`).
* Fix network difficulty display to resemble that of `cgminer` 3.1.1.
* Forward-port relevant bugfixes form `ckolivas/cgminer`, up to `cgminer`
  version 3.10.0.


Previous NEWS file available [here](https://github.com/veox/sgminer/blob/829f0687bfd0ddb0cf12a9a8588ae2478dfe8d99/NEWS).
