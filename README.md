### Automatically tracked protobufs for Steam and Valve's games.

These protobufs are being dumped as updates come in the [SteamTracking](https://github.com/SteamDatabase/SteamTracking) repository.

Protobufs are dumped using [SteamKit's protobuf dumper](https://github.com/SteamRE/SteamKit/tree/master/Resources/ProtobufDumper).

Each folder has the `google/protobuf/descriptor.proto` of its binaries, which for games has options such as `boxed_type` that the stock one doesn't have, so compile each folder with that folder as the import path, for example `protoc -I csgo csgo/usermessages.proto`.

For protobufs dumped from javascript files (in webui folder), we have a [separate dumper](https://github.com/SteamDatabase/SteamTracking/blob/master/tools/dump_javascript_protobufs.mjs) which parses javascript files into abstract syntax tree and tries to find all the messages and services. As such, these dumps are not as complete as dumps from binary files because minified javascript files lack some information.

> [!NOTE]
> Artifact and Underlords protobufs are no longer being updated automatically.
