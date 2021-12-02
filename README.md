# docker-php-nginx-node

Minimal image of Nginx + PHP-FPM running on Alpine.

- When it encounters an ONBUILD instruction, the builder adds a trigger to the metadata of the image being built. The instruction does not otherwise affect the current build.
- At the end of the build, a list of all triggers is stored in the image manifest, under the key OnBuild. They can be inspected with the docker inspect command.
- Later the image may be used as a base for a new build, using the FROM instruction. As part of processing the FROM instruction, the downstream builder looks for ONBUILD triggers, and executes them in the same order they were registered. If any of the triggers fail, the FROM instruction is aborted which in turn causes the build to fail. If all triggers succeed, the FROM instruction completes and the build continues as usual.
- Triggers are cleared from the final image after being executed. In other words they are not inherited by “grand-children” builds.

[Supervisor: A Process Control System](http://supervisord.org/index.html)

[onbuild](https://docs.docker.com/engine/reference/builder/#onbuild)

