# EMQX kafka bridge

version info：
- erlang otp： otp-22.3
- emqx-rel： v4.0.0

## how to use

- clone emqx-rel source code
```
git clone -b v4.0.0 https://github.com/emqx/emqx-rel.git
```

- edit rebar.config
```
cd exqx-rel/ 
vi rebar.config
```
append emqx_kafka_bridge in `deps` item, see below:
```
{deps,
 [emqx,
  emqx_retainer,
  emqx_management,
  emqx_dashboard,
  emqx_bridge_mqtt,
  emqx_sn,
  emqx_coap,
  emqx_stomp,
  emqx_auth_clientid,
  emqx_auth_username,
  emqx_auth_http,
  emqx_auth_jwt,
  emqx_auth_mysql,
  emqx_web_hook,
  emqx_delayed_publish,
  emqx_recon,
  emqx_rule_engine,
  {emqx_kafka_bridge, {git, "https://github.com/PearceDuan/emqx-kafka-bridge", {branch, "master"}}}
 ]}.
```
append emqx_kafka_bridge in `release` item, see below:
```
{emqx_kafka_bridge, load}
```
- compile && run
```
make
./_build/emqx/rel/emqx/bin/emqx console
./_build/emqx/rel/emqx/bin/emqx_ctl plugins load emqx_kafka_bridge
```
