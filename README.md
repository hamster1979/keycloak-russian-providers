# Провайдеры авторизации для российских социальных сетей.

Библиотека провайдеров российских социальных сетей для [Keycloak](https://www.keycloak.org/)
+ [ВКонтакте](docs/vk.md)
+ [Однокласники](docs/ok.md)
+ [Яндекс](docs/yandex.md)
+ [Мой Мир](docs/mailru.md)

Библиотеку провайдеров скачать можно [здесь](https://nexus.playa.ru/nexus/content/repositories/releases/ru/playa/keycloak/keycloak-russian-providers/).

## Совместимость

Библиотека провайдеров проверялась на следующих версиях:
+ 4.4.0.Final
+ 3.4.3.Final

## Установка провайдеров авторизации в Keycloak

Если вы используете Docker - соберите проект с профилем `docker`, получится готовый образ.
```
  mvn install -Pdocker
```

Также существует возможность установить библиотеку провайдеров самостоятельно.
Для этого:

1. Скопируйте `keycloak-russian.jar` в [директорию](https://www.keycloak.org/docs/latest/server_development/index.html#registering-provider-implementations) `${keycloak.home.dir}/standalone/deployments`.
2. Скопируйте содержимое директории `${keycloak.home.dir}/src/main/resources/theme/base/admin/resources/partials` в `${keycloak.home.dir}/themes/base/admin/resources/partials`
3. В файл `${keycloak.home.dir}/theme/base/admin/messages/admin-messages_en.properties` добавьте следующие строки:
```
ok-public-key=Application's public key
ok.public_key.tooltip=Public key application
vk-api-version=API Version
vk.version.tooltip=VK API version
```
4. В файл `${keycloak.home.dir}/theme/base/admin/messages/admin-messages_ru.properties` добавьте следующие строки:
```
ok-public-key=Application's public key
ok.public_key.tooltip=Публичный ключ приложения
vk-api-version=API Version
vk.version.tooltip=Версия API
```