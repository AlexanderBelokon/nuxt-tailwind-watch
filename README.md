# Reproduction for nuxt-community/tailwindcss-module#359

If you run `yarn dev` in this repo, all files in it will be watched.

If you then run `touch test; git add test`, recompilation will be triggered twice, for `test` and for `.git/index.lock`.

This is annoying, but the real problem is that when developing on WSL1, watching places locks on files, preventing VSCode's git integration from working.

To work around this issue it is possible to downgrade to `@nuxtjs/tailwindcss@4.1.3`, which uses `tailwindcss@2.1.2`
