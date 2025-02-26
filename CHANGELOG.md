# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.3.1] - 2021-8-3

### Changed

- fix: first OnReconnectAttempt will not triggered when reconnecting
- fix: incorrect disconnect reason

## [2.3.0] - 2021-7-21

### Added

- OnReconnected event
- OnReconnectAttempt event
- OnReconnectError event
- OnReconnectFailed event

### Changed

SocketIOCLient.Windows7 becomes a plug-in, the following code shows how to support Windows7 / Windows 2008 R2

```cs
var client = new SocketIOClient(...);
client.Socket = new ClientWebSocketManaged();
```

### Removed

- OnReconnecting event
- Options.AllowedRetryFirstConnection
- OnReceivedEvent event

## [2.2.4] - 2021-6-24

SocketIOClient  
SocketIOClient.Windows7

### Changed

- Set the default EIO to 4

### Added

- Strong name for SocketIOClient.Windows7

## [2.2.3] - 2021-6-15

SocketIOClient  
SocketIOClient.Windows7

### Changed

- Fix: wrong num was used when sending multiple byte arrays at once

### Added

- OnAny
- OffAny
- PrependAny
- ListenersAny

## [2.2.2] - 2021-6-7

SocketIOClient  
SocketIOClient.Windows7

### Changed

- Increase the buffer size to improve the performance when receiving big data

## [2.2.1] - 2021-6-5

SocketIOClient  
SocketIOClient.Windows7

### Changed

- Fix the problem of disconnection when sending large amounts of data continuously

## [2.2.1] - 2021-5-8

SocketIOClient.Newtonsoft.Json

### Changed

- Fix binary message index is out of range(SocketIOClient.Newtonsoft.Json)

## [2.2.0] - 2021-4-29

### Added

- Use System.Text.Json serialization/deserialization
- Decouple JSON plugin
- SocketIOClient.Newtonsoft.Json
- Support CancellationToken to cancel Emit

### Changed

- .NET Framework 4.5 is no longer supported

## [2.1.7] - 2021-3-24

### Changed

- Fix Unicode characters garbled

## [2.1.6] - 2021-3-11

### Changed

- Strong-named assemblies
- Fix reconnection failure

## [2.1.5] - 2021-2-5

### Removed

- Strong-named assemblies, PFX signing not supported on .NET Core.

## [2.1.4] - 2021-2-5

### Changed

- Strong-named assemblies
- Optimize for .NET Framework(WebSocketSharpClient)

## [2.1.3] - 2021-1-13

### Changed

- Fix socket.io v3 binary message bug

## [2.1.2] - 2020-12-23

### Added

- Support custom connection interval

### Changed

- Fix multiple pings working at the same time in some cases

## [2.1.1] - 2020-11-13

### Added

- Support socket.io v3

## [2.1.0] - 2020-11-11

No longer maintain `SocketIOClient.NetFx`, it is replaced by `SocketIOClient`. For users, you don’t have to worry about choosing `SocketIOClient` or `SocketIOClient.NetFx`

### Added

- Support verify the server certificate

### Changed

- The usage of `Options.EnabledSslProtocols` has changed
- `ClientWebSocket` becomes a sealed class
- Changed the way to configure the proxy

### Removed

- Removed `ClientWebSocket.CreatClient()` virtual method

## [2.0.2.9] - 2020-10-27

### Fixed

- Fixed a serious error that caused connection and sending message to become unusable. The error originated from the last update(v2.0.2.8).

## [2.0.2.8] - 2020-10-25

### Added

- Implement ConnectionTimeout
- Added library docs
- When connecting for the first time, it supports automatic reconnection.

## [2.0.2.7] - 2020-10-09

### Added

- Support WebProxy, [PR](https://github.com/doghappy/socket.io-client-csharp/pull/87)

## [2.0.2.6] - 2020-09-09

### Fixed

- Fixed "SynchronizationLockException" exception, [issues-84](https://github.com/doghappy/socket.io-client-csharp/issues/84)

## [2.0.2.5] - 2020-09-08

### Fixed

- Fixed "Collection was modified" exception