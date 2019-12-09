# Godot 3 2D Fake Explosion Particles

A script to simulate explosion particles.

![Godot-3-2D-Fake-Explosion-Particles-GIF](examples/Godot-3-2D-Fake-Explosion-Particles.gif)

## Instalation

* [Download](https://github.com/hiulit/Godot-3-2D-Fake-Explosion-Particles/archive/master.zip) the repository ZIP file.
* Copy `fake_explosion_particles.tscn` and `fake_explosion_particles.gd`.

## Usage

Instance `fake_explosion_particles` and attach `fake_explosion_particles.gd` as a script.

## Parameters

![Godot-3-2D-Fake-Explosion-Particles-Parameters](examples/parameters.png)

The minimum and maximum variables values are used to generate random values. If you don't want to use random values, set the minimum and maximum variables values with the same value.

### Min particles number

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_number` | `int` | Set the mininum number of the particles. | `200` |

### Max particles number

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_number` | `int` | Set the maximum number of the particles. | `400` |

### Min particles gravity

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_gravity` | `float` | Set the mininum gravity of the particles. | `200.0` |

### Max particles gravity

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_gravity` | `float` | Set the maximum gravity of the particles. | `600.0` |

### Min particles velocity

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_velocity` | `float` | Set the mininum initial velocity of the particles. | `200.0` |

### Max particles velocity

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_velocity` | `float` | Set the maximum initial velocity of the particles. | `600.0` |

### Max particles position X

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_position_x` | `int` | Set the maximum initial X position of the particles. | `ProjectSettings.get_setting("display/window/size/width"` |

### Max particles position Y

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_position_y` | `int` | Set the maximum initial Y position of the particles. | `ProjectSettings.get_setting("display/window/size/height"` |

### Max particles size

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_size` | `int` | Set the minimum size of the particles. | `1` |

### Max particles size

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_size` | `int` | Set the maximum size of the particles. | `3` |

### Get random position

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `get_random_position` | `bool` | Get a random initial position for the particles. | `false` |

If set to `true`, the particles will be created in a random position based on `max_particles_position_x` and `max_particles_position_y`.

### Start timer

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `start_timer` | `bool` | Start the particles timer. | `false` |

If set to `true` it will start a timer. When it times out, it will create new particles.

### Timer wait time

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `timer_wait_time` | `float` | Set the wait time of the timer (in seconds). | `1` |

### Particles explode

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `particles_explode` | `bool` | Explode the particles. | `false` |

If set to `true`, the particles will explode.

### Group name

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `group_name` | `String` | Set the name of the group. | `fake_explosion_particles` |
