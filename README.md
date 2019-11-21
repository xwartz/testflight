# testflight-monitor

🚑 Manage beta builds of your app, testers, and groups.

## monitor

### 测试人数监控

1. 监控 testflight 某个 group 的测试人数
2. 当测试超过「限制值」时，自动删除该 group 下的 N 个测试人员
3. ~~删除人员顺序按照安装时间~~
4. 发送删除信息到 slack

### build 过期监控

1. 监控 testflight 某个 group 的版本期限
2. 当版本距离过期时间 N 天时，自动发 slack 提示

## how to use

install:
```
yarn install
```

config:
```ts
// appstore.ts
export default {
  groupId: 'xxxxx',
  issuerId: 'xxxx',
  keyId: 'xxx',
  privateKey: './config/appstore/xxxx',
}
```

```ts
// slack.ts
export default {
  channel: '#monitor',
  webhookUrl: '/services/xxxxx',
}
```

run:
```
yarn start
```

or use pm2
```
yarn prod:start
```

## reference

- [App Store Connect API](https://developer.apple.com/documentation/appstoreconnectapi)
- [Unofficial REST API client for Apple's App Store Connect API](https://github.com/aaronsky/appstoreconnect)
