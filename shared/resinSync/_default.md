Okay, so now we know how to provision a device and push code. There is just one glaring problem...
>Do I really have to go through the whole `git add`, `git commit`, `git push` dance every time I forget a semicolon?

Luckily, our nifty little command line tool `{{ $names.company.lower }} sync` is here to save the day. It allows you to quickly sync source code and file changes across to one of the devices in your fleet, so you can rapidly iterate code on this test device before releasing it to the whole fleet.

__Note:__ {{ $names.company.lower }} sync will only work on {{ $names.os.lower }} v1.1.4+
and Agent v1.8.0+.

#### Setting up {{ $names.company.lower }} sync.

{{ $names.company.lower }} sync is bundled in with our handy {{ $names.cli.lower }} tool. The CLI allows you to basically do all your {{ $names.company.lower }} management from the comfort of the command line. Read the [CLI reference][cli-ref-link] more info on all the cool things it can do.

__Warning:__ Currently {{ $names.company.lower }} sync is **NOT** supported on Windows. Support is currently being worked on, you can check the progress on this on the [git repository][windows-support].

To install {{ $names.cli.lower }} and sync you need at least [`node.js 6.0.0`][nodejs-link] on your development machine, then run:
```
$ npm install --global --production {{ $names.company.lower }}-cli
```
You may need to run the install with admin privileges depending on how you have installed node.js.

__Note:__ If you already have {{ $names.cli.lower }} installed, you will need to upgrade to {{ $names.cli.lower }} v4.0.0+

Once the CLI is installed globally, login with your {{ $names.company.lower }} account:
```
$ {{ $names.company.lower }} login
```
You should then be presented with 3 options to login. The recommended method is `Web authorization` which will open a dialog in your web browser and ask you to authorize the use of the CLI.
```
{{ $names.company.lower }}:simple-server-node shaun$ {{ $names.company.lower }} login
 _            _
| |__   __ _ | |  ____  _ __    __ _
| '_ \ / _` || | / __ \| '_ \  / _` |
| |_) | (_) || ||  ___/| | | || (_) |
|_.__/ \__,_||_| \____/|_| |_| \__,_|

Logging in to {{ $names.company.lower }}
? How would you like to login? (Use arrow keys)
❯ Web authorisation (recommended)
  Credentials
  Authentication token
  I don't have a {{ $names.company.upper }} account!
```

[cli-ref-link]:/tools/cli/
[windows-support]:{{ $links.githubMain }}-modules/resin-sync/blob/feat/windows-support/README.md#windows
[nodejs-link]:https://nodejs.org/en/
