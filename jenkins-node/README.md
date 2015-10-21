# Jenkins Slave with Node.js

This image is used by [Jenkins][jenkins] to dynamically start agents with Node.js on Docker Hosts.

[jenkins]: https://jenkins-ci.org

## How To Use

This image should be used with the Docker Plugin 'docker-plugin' in the Jenkins repo: https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin

Just follow the instructions in the wiki of the plugin

## Docker Image

The plugin mentioned above will pull the plugin automagically if configured correctly.
However, if you haven't configured the automatic pull, you can do so manually by 

```
docker pull 42nerds/jenkins-node
```

You'll find the repo on [docker hub][repo]

[repo]: https://hub.docker.com/r/42nerds/jenkins-node/

## License

This repository is Copyright (c) 2015 42nerds. It is free software, and may be
redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: /LICENSE

## About

![42nerds](https://42nerds.com/sites/56015d6106da30000100028a/assets/5626bb0ce3c2530001000000/Logo-42nerds-128.png)

This repo is maintained and funded by 42nerds. The names and logos for
42nerds are trademarks of 42nerds.

We love open source software! See [our our website][website] or [hire us][hire] to help you with your project.

[website]: https://42nerds.com/?utm_source=github
[hire]: https://42nerds.com/contact?utm_source=github