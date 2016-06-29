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

