# Task – Tx Validate

Публичная задачка из бесплатной социальной сети твиттер точка ком от Владислава Козули - [Исходный тред](https://twitter.com/vladkozulya/status/1755209744057299174/photo/1) (осторожно там есть спойлеры решения)


[Да кто такой, этот ваш Козуля?](https://www.youtube.com/watch?v=pfyn8dgPBUg)

-----

## Предыстория 
Сижу на дейли, случайно открываю пост Владислава. 
Ощущаю как олипмиадное альетэго вырывается из груди и дальше всё как в тумане..... 

Придумываю решение, потом придумываю тексты по которым решение не проходит, потому думаю дальше. Через час удовлетворяюсь всем зеленым тестам и думаю ну не выкидывать же наработанное, вдруг кому пригодится.

Добро пожаловать 🖖

## Условия от Владислава

Написать метод, который принимает список транзакий и баланс пользователя 

```typescript
type Transaction = {
  id: number;
  orderId: number;
  amount: number;
  txType: 'Bet' | 'Win';
}
```

- Вернуть произвольную структуру, где каждая транзакция помечена как валидная или невалиданая.
- Транзакции обрабатываются от меньшего id к большему.
- Bet уменьшает баланс на сумму в amount, Win увеличивает.
- Если баланс ушел в минус, транзакция считается невалидной.
- Если транзакция не валидна, последующие транзакции с тем же orderId тоже считаются невалидными.
- Если id транзакции повторяется, такая транзакция тоже не валидна, но остальные с тем же orderId должен быть обработаны.

[Исходный тред](https://twitter.com/vladkozulya/status/1755209744057299174/photo/1)

## Как решать

Владислав - человек занятой, поэтому я сделал этот шаблон с CI проверкой тестов за него. И [тесты](https://github.com/isuvorov/tx-validate/blob/main/tests/tx-validate.test.ts) написал. (Правда не факт что они верные 😁 Если вдруг чего не учел – дополняйте).

И так, как решать эту задачку:

1. Форкаете и клонируете этот репозиторий
2. Устанавливаете зависимости `npm i` or `pnpm i`
3. Редактируете код решения в файле `src/tx-validate.ts`
4. Проверяете что ваш код вообще собирается `npm run build` (или в режиме watch `npm run dev`)
5. Запускаете тесты `npm test` (или в режиме watch `npm run test:watch`)
6. Как только все тесты проходят, оформляете pull request в этот репозиторий в ветку `main`
7. Github Actions запустит тесты и проверит ваше решение 

## Дополнения от меня 

1. Тесты будут дополняться по мере поступления решений 😈
2. Помимо самих тестов будут прогоняться eslint
3. После PR решения, предлагаю пройтись во всем остальным PR и похвалить/покритиковать/повзламывать чужие решения
4. Предлагайте свои варианты тестов, если считаете что текущие не покрывают все случаи
5. Если у вас остались вопросы, или есть предложения пишите мне в телеграм [@isuvorov](https://t.me/isuvorov)

P.S. **Не публичная оферта**. Прохождение задачки не гарантирует трудоустройство.
