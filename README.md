# firehose-handlers

[![Build Status](https://travis-ci.org/atomist-rugs/firehose-handlers.svg?branch=master)](https://travis-ci.org/atomist-rugs/firehose-handlers)
[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

[rug]: http://docs.atomist.com/

This [Rug][rug] project contains Rugs to help you create basic event handlers of your own.

## Rugs


### AddLocalEditor

The AddLocalEditor editor adds an editor for modifying the local
project, initiating a Rug archive if needed.

#### Prerequisites

A source code project.

#### Parameters

This Rug takes following parameters.

Name | Required | Default | Description
-----|----------|---------|------------
`editorName` | Yes | | Name of the editor to add, it should start with a capital letter and contain only alphanumeric characters
`description` | No | "an editor for modifying this project" | A short description of what the editor will do

#### Running

Run this Rug as follows:

```
$ cd project/directory
$ rug edit atomist-rugs:firehose-handlers:AddLocalEditor \
    editorName=MyLocalEditor \
    description='does something useful'
```

This will add a Rug editor as `.atomist/editors/MyLocalEditor.ts`.  If
the project is currently set up for Atomist, it will also create the
`.atomist` directory with appropriate initial contents like the
`manifest.yml` and `package.json` files and the Rug TypeScript typings
in the `node_modules` directory.

## Support

General support questions should be discussed in the `#support`
channel on our community Slack team
at [atomist-community.slack.com][slack].

If you find a problem, please create an [issue][].

[issue]: https://github.com/atomist-rugs/firehose-handlers/issues

## Development

You can build, test, and install the project locally with
the [Rug CLI][cli].

[cli]: https://github.com/atomist/rug-cli

```
$ rug test
$ rug install
```

To create a new release of the project, simply push a tag of the form
`M.N.P` where `M`, `N`, and `P` are integers that form the next
appropriate [semantic version][semver] for release.  For example:

[semver]: http://semver.org

```
$ git tag -a 1.2.3
```

The Travis CI build (see badge at the top of this page) will
automatically create a GitHub release using the tag name for the
release and the comment provided on the annotated tag as the contents
of the release notes.  It will also automatically upload the needed
artifacts.

---
Created by [Atomist][atomist].
Need Help?  [Join our Slack team][slack].

[atomist]: https://www.atomist.com/
[slack]: https://join.atomist.com/
