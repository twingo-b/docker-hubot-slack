# docker-hubot-slack

## 開発環境
```bash
# npm install & generate hubot slack template
% npm install -g yo generator-hubot
% yo hubot --adapter slack --defaults

# edit token
% direnv edit
export HUBOT_SLACK_TOKEN=

# docker-compose
% docker-compose build
% docker-compose up -d
```

# heroku
## heroku create
```bash
% heroku create
% heroku addons:add redistogo:nano
# % heroku config:set HUBOT_LOG_LEVEL=debug
% heroku config:set HUBOT_SLACK_TOKEN=
```
 
## hubot-heroku-keepalive
```bash
% heroku config:add TZ="Asia/Tokyo"
% heroku config:set HUBOT_HEROKU_KEEPALIVE_URL=$(heroku apps:info -s | grep web-url | cut -d= -f2)
% heroku addons:create scheduler:standard
```

### Scheduler
```bash
% heroku addons:open scheduler
```

```
$ curl ${HUBOT_HEROKU_KEEPALIVE_URL}heroku/keepalive
```
- DYNO SIZE: Free
- FREQUENCY: Daily
- NEXT DUE: 15:00 UTC (06:00 JST)

# heroku deploy
```bash
% git push heroku master
```

