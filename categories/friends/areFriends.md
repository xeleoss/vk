---
layout: default
title: Метод Friends.AreFriends
permalink: friends/areFriends/
comments: true
---
# Метод Friends.AreFriends
Возвращает информацию о том добавлен ли текущий пользователь в друзья у указанных пользователей.
Также возвращает информацию о наличии исходящей или входящей заявки в друзья (подписки).

# Синтаксис
```csharp
public IDictionary<long, FriendStatus> AreFriends(IEnumerable<long> uids)
```

## Параметры
+ **uids** - Список идентификаторов пользователей.

## Результат
Метод возвращает словарь, ключом которого является идентификатор пользователя (uid), а значением значение типа FriendStatus.

## Исключения
+ **AccessTokenInvalidException** - не задан или используется неверный AccessToken.
+ **ArgumentNullException** - параметр uids имеет значение null.

## Пример
```csharp
// Получение информации о том добавлен ли текущий пользователь в друзья у указанных пользователей и проверяет наличие исходящей или входящей заявки в друзья (подписки).
var uids = new long[] {176382, 298320, 389320};
var dict = vk.Friends.AreFriends(uids);
if (dict[298320] == FriendStatus.NotFriend)
{
  .....
}
```