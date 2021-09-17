# DevOps-Git-Task-2
Пусть есть ветка master с 3-мя коммитами (Init commit, incorrect master commit 1, incorrect master commit 2)
Порядок действий для восстановления требуемого состояния следующий:
1. От ветки master отводим ветку, например, develop. Таким образом, ветка develop будет содержать те же 3 коммита.
2. Переключаемся на ветку master. Делаем для нее hard reset до нужного коммита, который должен оставаться в master. (В данном случае hard reset до Init commit). После этого ветка master будет содержать Init commit, а ветка develop - 3 коммита.
3. Открываем PR на влитие ветки develop в ветку master. Этот PR будет содержать в себе diff, как раз состоящий из нужных 2-х коммитов (Incorrect master commit 1, 2).

Необходимые команды:
1. git branch develop - создается ветка develop со всеми коммитами
2. git reset --hard HEAD~2 - для ветки master 2 последних коммита стираются
После этого открываем PR develop -> master.
