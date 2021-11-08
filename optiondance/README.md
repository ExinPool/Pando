# OptionDance Process Monitor

> OptionDance process monitor tools.

[![Build Status](http://img.shields.io/travis/badges/badgerbadgerbadger.svg?style=flat-square)](https://travis-ci.org/badges/badgerbadgerbadger) [![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

## Table of Contents

- [Installation](#installation)
- [Features](#features)
- [Contributing](#contributing)
- [Team](#team)
- [FAQ](#faq)
- [Support](#support)
- [License](#license)

## Installation

- Ubuntu 16.04.1 LTS
- Written in bash

### Clone

- Clone this repo to your server using:

``` bash
$ sudo mkdir -p /data/monitor/exinpool
$ cd /data/monitor/exinpool
$ sudo git clone https://github.com/ExinPool/Pando
```

### Setup

Search `7000000012` in [Mixin Messenger](https://mixin.one/messenger) and add **[Webhook](https://mixin.one/codes/4d792128-1db8-4baf-8d90-d0d8189a4a7e)** as contact.

Invite Webhook and somebody who want to receive monitor message to a small group in Mixin Messenger. Open Webhook in the group, you can see the access token.

> Note: The access token is only available for the owner of the group.

Copy `config.cfg.defaults` to `config.cfg` and change some varibles like this in the `config.cfg`.

``` bash
SERVICE=OptionDance
PROCESS=6028
PROCESS_NUM=1
HOST=optiondance.exin.one
LOG_FILE=doptiondance_process.log
WEBHOOK_URL=https://webhook.exinwork.com/api/send?access_token
ACCESS_TOKEN=YOUR_ACCESS_TOKEN
LARK_WEBHOOK_URL=https://open.larksuite.com/open-apis/bot/v2/hook/
```

Add crontab like this in the server.

``` bash
# OptionDance process monitor
*/5 * * * * cd /data/monitor/exinpool/Pando/optiondance && bash optiondance_process.sh >> optiondance_process.log &

# OptionDance process monitor
*/5 * * * * cd /data/monitor/exinpool/Pando/optiondance && bash optiondance_process_lark.sh >> optiondance_process.log &
```

The crontab will run every minute then you can check the log in the `optiondance_process.log`.

## Features

- Monitor OptionDance process
- Send alarm message when OptionDance process is abnormal
- Send alarm message via Webhook which based on Mixin API
- Send alarm message to Lark

## Contributing

To be continued.

## Team

@ExinPool

## FAQ

To be continued.

## Support

Reach out to us at one of the following places!

- Website at <a href="https://exinpool.com" target="_blank">`exinpool.com`</a>
- Twitter at <a href="http://twitter.com/ExinPool" target="_blank">`@ExinPool`</a>
- Email at `robin@exin.one`

## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](https://opensource.org/licenses/mit-license.php)**
- Copyright 2019 © <a href="https://exinpool.com" target="_blank">ExinPool</a>.
