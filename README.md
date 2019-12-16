# Godot 3 2D Fake Explosion Particles

A script to simulate exploding particles.

![Godot-3-2D-Fake-Explosion-Particles-GIF](examples/Godot-3-2D-Fake-Explosion-Particles.gif)

## Instalation

* [Download](https://github.com/hiulit/Godot-3-2D-Fake-Explosion-Particles/archive/master.zip) the repository ZIP file.
* Copy `fake_explosion_particles.tscn` and `fake_explosion_particles.gd`.

## Usage

Instance `fake_explosion_particles.tscn` and attach `fake_explosion_particles.gd` as a script.

You can of course use GDScript as well.

```
# Creata a new node.
var fake_explosion = Node2D.new()
fake_explosion.name = "fake_explosion"

# Attach the script.
fake_explosion.set_script(preload("res://path/to/fake_explosion_particles.gd"))

# Set 'fake_explosion' variables.
fake_explosion.min_particles_number = 5
fake_explosion.max_particles_number = 10
fake_explosion.min_particles_gravity = 20
fake_explosion.max_particles_gravity = 60
fake_explosion.min_particles_velocity = 20
fake_explosion.max_particles_velocity = 60
fake_explosion.min_particles_size = 1
fake_explosion.max_particles_size = 2
# etc ...

# Set its position
fake_explosion.position = Vector2(0, 0)

# This is useful if you want the explosion to be more visible.
fake_explosion.z_index = 1

# Add it to the scene.
get_parent().add_child(fake_explosion, true)

# And then you can explode it whenever you want.
fake_explosion.explode_particles = true

# You can use the name of the group to find all the fake particles nodes more easily.
get_tree().get_nodes_in_group("fake_explosion_particles")
```

You can change the colors of the particles, but you have to change them inside the script. They are set in `particles_colors_with_weights`.

The colors of the particles are chosen randomly depending on *weights*. If you want a color to have more probabilities to be chosen, give it a greater *weight*.

These are the defaults:

```
var particles_colors_with_weights = [
	[4, Color("#ffffff")],
	[2, Color("#000000")],
	[8, Color("#ff004d")],
	[8, Color("#ffa300")],
	[10, Color("#ffec27")]
]
```

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

### Min particles velocity increment

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_velocity_increment` | `float` | Set the mininum velocity increment of the particles. | `0.991` |

### Max particles velocity increment

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_velocity_increment` | `float` | Set the maximum velocity increment of the particles. | `1.009` |

### Max particles position X

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_position_x` | `int` | Set the maximum initial X position of the particles. | `ProjectSettings.get_setting("display/window/size/width"` |

### Max particles position Y

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_position_y` | `int` | Set the maximum initial Y position of the particles. | `ProjectSettings.get_setting("display/window/size/height"` |

### Min particles lifespan

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_lifespan` | `float` | Set the minimum lifespan of the particles (in seconds). | `0.05` |

### Max particles lifespan

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_lifespan` | `float` | Set the minimum lifespan of the particles (in seconds). | `0.1` |

### Min particles fade factor

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `min_particles_fade_factor` | `float` | Set the minimum fade factor of the particles. The bigger the number, the faster the particles will fade. | `2.0` |

The factor is `1 / min_particles_fade_factor`. Using the default values that would be `0.5` seconds.

### Max particles fade factor

| Name | Type | Description | Default |
| --- | --- | --- | --- |
| `max_particles_fade_factor` | `float` | Set the minimum fade factor of the particles. The bigger the number, the faster the particles will fade. | `10.0` |

The factor is `1 / max_particles_fade_factor`. Using the default values that would be `0.1` seconds.

### Min particles size

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

## Changelog

See [CHANGELOG](CHANGELOG.md).

## Authors

* Me 😛 [hiulit](https://github.com/hiulit).

## Credits

Thanks to:

* [CowThing](https://github.com/CowThing) - For the `_rand_array` function.
* [_justpassingby_](https://www.reddit.com/user/_justpassingby_) - For helping in fixing and cleaning up some code.

## License

[MIT License](LICENSE).