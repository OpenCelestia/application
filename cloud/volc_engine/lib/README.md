# Volcengine RTC library

`anypi_nova` and `anypi_nova_dev` leave `CONFIG_APP_CLOUD_VOLC` and `CONFIG_APP_TABLET_VOLC_ENGINE` off. The sources under `application/cloud/volc_engine` and `application/packages/tablet/volc_engine` stay as an integration reference and are not built.

`libVolcEngineRTCLite.so` is not stored in this directory. The public header `../include/volc_engine_rtclite.h` is marked MIT and stays.

Turn both switches back to `y` to build. The link then uses, in order:

1. A private `libVolcEngineRTCLite.so` placed in this directory. Do not commit it.
2. The product rootfs copy kept with the board overlay, for example `project/anypi_nova/system/AnyCloud39AV200/V1.04/patch/rootfs/utils/usr/lib/libVolcEngineRTCLite.so`.

Runtime credentials belong in `app_volc_config.ini` placeholders or environment variables, not in source.

`anypi_nova` 与 `anypi_nova_dev` 关闭 `CONFIG_APP_CLOUD_VOLC` 和 `CONFIG_APP_TABLET_VOLC_ENGINE`。`application/cloud/volc_engine` 与 `application/packages/tablet/volc_engine` 的源码保留，只作对接参考，不参与编译。

`libVolcEngineRTCLite.so` 不放在本目录。公开头 `../include/volc_engine_rtclite.h` 标明 MIT，予以保留。

两个开关改回 `y` 才会编译。链接按这个顺序找库：

1. 放到本目录的私有 `libVolcEngineRTCLite.so`，不要提交。
2. 产品 rootfs 里随板级 overlay 保留的那份，例如 `project/anypi_nova/system/AnyCloud39AV200/V1.04/patch/rootfs/utils/usr/lib/libVolcEngineRTCLite.so`。

运行时凭据用 `app_volc_config.ini` 占位符或环境变量。
