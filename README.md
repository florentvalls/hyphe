# Hyphe: web corpus builder & links crawler

Welcome to Hyphe: developped by [SciencesPo's médialab](http://www.medialab.sciences-po.fr/) for the [DIME-SHS Web project (Equipex)](http://www.sciencespo.fr/dime-shs/).

Hyphe aims at providing a tool to crawl data from the web to generate networks between what we call WebEntities, which can be single pages as well as a website or a combination of such.

## Demo

You can try a restricted version of Hyphe at the following url: [http://hyphe.medialab.sciences-po.fr/demo/](http://hyphe.medialab.sciences-po.fr/demo/)


## Easy start

__DISCLAIMER:__ Hyphe has changed a lot between version `0.1` and `0.2`. Migrating from an older version by pulling the code from git was guaranteed as best as possible, although it is highly recommended to reinstall from scratch. Older corpora can be reran by exporting the list of WebEntities from the old version and recrawl from that list of urls in the new version.


### Install a release

For an easy install, the best solution is to download directly the [release version](https://github.com/medialab/Hypertext-Corpus-Initiative/releases), which was built to run against various GNU/Linux distributions (Ubuntu, Debian, CentOS...).

Just uncompress the release archive, go into the directory and run the installation script.

Do __not__ use `sudo`: the script will do so on its own and will ask for your password only once. This works so in order to install all missing dependencies at once, including mainly Java (OpenJDK-6-JRE), Python (python-dev, pip, virtualEnv, virtualEnvWrapper...), Apache2, MongoDB & ScrapyD.

If you are not comfortable with this, you can read the script and run the steps line by line or follow the [Advanced install instructions](doc/install.md) for more control on what is actually installed.

```bash
# WARNING: DO NOT prefix any of these commands with sudo!
tar xzvf hyphe-release-*.tar.gz
cd Hyphe
./bin/install.sh
```

To install from git sources of if you want to contribute to Hyphe's development, please follow the [Advanced install documentation](doc/install.md).


### Configure Hyphe

Before starting Hyphe, you should probably adjust the settings first. Everything you need to change is in the global configuration file ```config/config.json```.

Please read the [Configuration documentation](doc/config.md) for details.


### Run Hyphe

Hyphe relies on a web interface communicating with a server daemon which must be running at all times.
To start, stop or restart the daemon, run (again, __no__ `sudo`):

```bash
bin/hyphe <start|restart|stop> [--nologs]
```

By default the starter will display Hyphe's log in the console using ```tail```. You can ```Ctrl-C``` whenever you want without shutting it off. Use the ```--nologs``` option to disable this.

You can always check the logs for both the core backend and each corpus' MemoryStructure in the ```log``` directory:

```bash
tail -f log/hyphe-*.log
```

As soon as the daemon is started, you can start playing with the web interface on your local machine at the following url: [http://localhost/hyphe](http://localhost/hyphe).


### Serve on the web

Using the website on localhost, you can already use Hyphe. Although, if you want to let others use it as well (typically if you installed on a distant server), you need to make a few adjustments to the Apache configuration.

Please read the dedicated [WebService documentation](doc/serve.md) to do so.


## Advanced developers features & contributing

Please read the dedicated [Developers documentation](doc/dev.md) and the [API description](doc/api.md).


## What's next?

See our [roadmap](doc/roadmap.md)!


## Authors

[Mathieu Jacomy](https://github.com/jacomyma) & [Benjamin Ooghe-Tabanou](https://github.com/boogheta) @ SciencesPo [médialab](https://github.com/medialab)

Discover more of our projects at [médialab tools](http://tools.medialab.sciences-po.fr/)

Hyphe is a free software released under [LGPL](LICENSE.LGPL) &amp; [CECILL-C](LICENSE.CECILL-C) licenses.
