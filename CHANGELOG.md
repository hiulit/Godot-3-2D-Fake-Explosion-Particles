# CHANGELOG

## Unreleased

* Up to date

## [1.1.0] - 2019-12-16

### Added

* New parameter: `randomize_seed` - To let the user randomize the seed, or not. Default is set to `false`.
* New parameters: `min/max_particles_fade_factor` - To set the fade factor of the particles. The bigger the number, the faster the particles will fade.
* New parameters: `min/max_particles_lifespan` - To set the minimun and maximum lifespan of the particles (in seconds).

### Changed

* `_get_random_number()` for `_get_random_int(min_number, max_number)` - Better naming, so we know that the function will return an `int`. Also added min and max numbers as arguments.
* `_get_random_time()` for `_get_random_lifespan()` - Better naming, so we know that the *random time* is actually referring to the lifespan.
* `particle.time` for `particle.time_alive` - Better naming, so we know that the *time* is actually referring to the time the particle has been alive.

### Fixed

* Detecting when the particle is invisible. See [commit](https://github.com/hiulit/Godot-3-2D-Fake-Explosion-Particles/commit/283e9ffeae35940e50bf70cb819bf386198af6ea).
* Removing the particle from the particles array. See [commit](https://github.com/hiulit/Godot-3-2D-Fake-Explosion-Particles/commit/19b841309ab94e9ea59a543a9451535444a57531).

## [1.0.0] - 2019-12-09

* Released stable version.
