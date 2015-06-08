# Platformer

Platformer was an experiment with Unreal Engine 4. The idea was to produce a short demo game using only [Blueprints](https://docs.unrealengine.com/latest/INT/Engine/Blueprints/index.html) (in other words, no code was involved). At the same time, I also wanted to try experimental [Paper2D](https://docs.unrealengine.com/latest/INT/Engine/Paper2D/index.html) functionality.

You play as an avatar who is trying to escape a level. A bat guards a chest and a guardian devil guards the exit. Your goal is to simply find the exit key and escape through the locked door! But the obstacles are seemingly insurmountable. With your death a certainty, you must strategically die and then use the corpses of your former incarnations to advance throughout the level.

The demo is fully playable. Here is a short walkthrough (clicks through to youtube).

[![Platformer walkthrough](http://img.youtube.com/vi/jE0NUf_VJaI/0.jpg)](http://youtu.be/jE0NUf_VJaI)

## Assets

I used the excellent [Alagard font](http://opengameart.org/content/pixel-fonts-by-pix3m) -- [CC-BY 3.0](http://opengameart.org/content/pixel-fonts-by-pix3m).

I also used the awesome broad-purpose tileset [made by surt and found at opengameart.org](http://opengameart.org/content/simple-broad-purpose-tileset) -- [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

## Technical notes

For these who are also experimenting with Paper2D, here are some guidelines.

- Collision is manually done via `StaticMeshActor`s. UE4 does not support tileset collisions yet.
- Physics can be fiddly. Some things that may help:
  - Lock sprites to the Y-axis.
  - Turn off physics/gravity (when applicable).
  - Increase angular/linear damping.
- To preserve a pixel-perfect aspect ratio:
  - Camera must be orthographic (obviously).
  - Camera width set to the number of actual pixels.
  - `constrain aspect ratio` must be checked.
  - Run the game in a separate window; make sure it is not embedded in the selected viewport.
- Make judicious use of custom collision responses.
