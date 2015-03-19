#Git Conventions

## Организация за repo-тата
- Използваме [GitLab групата](https://gitlab.com/groups/dev-labs-bg) за всички наши **private** проекти. Не GitLab юзъра (имаме такъв в кирийки), ами групата. До сега използвахме юзър и създавахме част от репотата там, друга част от репотата бяха под лични профили и т. н., което не е най-доброто решение. В групата всички могат да виждат repo-тата, да се колаборира и да се пускат достъпи до определени хора до конкретни проекти и разни други кирийки.
- Имаме [GitHub група](https://github.com/dev-labs-bg) за всички **public** проекти. Идеята да се ползва и GitHub е да не се ограничаваме само до GitLab и неговите специфики, а и плюс това да сме comfortable да работим с повече от 1 git repository provider :)

## Конвенциите за имената на repo-тата
Използвайте само малки букви в имената и тирета за разделение на думите, пример:
```
devlabs-internal-code-conventions
```

## 8те Git-Flow правила важащи ФОФИСА:
1. Не сери/мажи в кода ... сериозно, недей, защото тъй да се каже, [това не е библейско](http://memebg.com/media/created/l5xo1t.jpg).
2. В master всичко е стабилно, в develop са готови features & fixes.
3. Не push-ваме в master (освен ако не правим hotfix или не пускаме release).
4. Всеки feature/промяна започва от develop с име feature/номер-име (пр. feature/01-login).
5. Feature влиза в develop само след Pull Request. Същото важи за bugfix към release.
6. В release само bugfix-и и докуметация. След това се merge с master и develop.
7. Hotfix почва от master и свършва там (след Pull Request). Решава само малки и важни проблеми.
8. Feature бранчовете винаги се качват горе, дори преди да са готови. Като са, се пуска Pull Request.

## GitFlow Chart:
[<img src="http://devlabs-projects.com/docs/Git-Flow-for-DevLabs-1.1.svg" width="790" />](http://devlabs-projects.com/docs/Git-Flow-for-DevLabs-1.1.svg)
