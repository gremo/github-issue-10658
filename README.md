# github-issue-10658

This repo is related with Tailwind not being able to watch for content change, at least with this dev container.

```bash
cat /etc/os-release
```

```txt
PRETTY_NAME="Debian GNU/Linux 11 (bullseye)"
NAME="Debian GNU/Linux"
VERSION_ID="11"
VERSION="11 (bullseye)"
VERSION_CODENAME=bullseye
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
```


## Replicate the bug

> **Note**: This exact same project works perfectly fine on Windows.

1. Reopen this project in the container (VSCode feature)
2. Run `yarn install`
2. Run `yarn encore dev --watch`
3. Change `templates/page/test.html.twig` i.e. add a class `bg-red-500` to the `<p>` element
4. The re-build isn't triggered as you save and class isn't added to the output file `public/build/app.css`

```bash
cat public/build/app.css | grep bg-red
```
