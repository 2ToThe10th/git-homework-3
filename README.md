# git homework 3

Для начала создадим master с 3 комитами и запушим его:

```
touch log.txt
echo "Initial commit to main" >> log.txt
git add log.txt
git commit -m "master"
echo "feature 1" >> log.txt
git commit -am "dev 1"
echo "feature 2" >> log.txt
git commit -am "dev 2"
git push
```


Получился такой граф:

![img.png](https://github.com/2ToThe10th/git-homework-3/raw/solution/images/start%20network.png)

Теперь начинаем решать задачу.
Для начала исправим все локально (находимся в ветке master):

```
git checkout -b dev
git checkout master
git reset d036debb # хэш последнего коммита который должен быть в мастере
```

Теперь зальем на сервер:

```
git push --force
git checkout dev
git push --set-upstream origin dev
```

Теперь граф выглядит: 

![img.png](https://github.com/2ToThe10th/git-homework-3/blob/solution/images/finish%20network.png)

Теперь можно создать [merge-request](https://github.com/2ToThe10th/git-homework-3/pull/1)
