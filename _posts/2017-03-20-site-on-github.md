---
layout: post
title:  "Привязка домена к репозиторию с GitHub-pages"
date:   2017-03-20 17:00:00 +0300
category: [Life]
icon: www
link: life
---
<p>Данный цикл статей посвящён созданию сайта на <a href="//github.com">GitHub</a> и его оптимизации.</p>
<p>Итак, мы купили домен и решили выложить пару сайтов, а денег нет. Что делать? Как известно, <a href="//github.com">GitHub</a> даёт бесплатный хостинг для статических сайтов, а также даёт избежать кода на стороне сервера. Причём ограничений на объём никаких нет.</p>
<p>Сегодня мы попробуем создать простой лендинг и привязать его к домену.</p>
<ol>
	<li>Создаём репозиторий, называем YOUR-USERNAME.github.io. В данном случае у нас vikapitoshka.github.io.<img class="image featured" src="/post-img/life/1.png"/></li>
	<li>Создаём простую страничку со стилями:<img class="image featured" src="/post-img/life/2.png"/></li>
	<li>Далее пишем CNAME-запись в репозитории, где будет записан адрес нашего сайта:
	<img class="image featured" src="/post-img/life/3.png"/></li>
	<li>Переходим на настройки репозитория, находим блок GitHub Pages и включаем Source. Я выбрала ветку master. <img class="image featured" src="/post-img/life/4.png"/> На этом пока работа с GitHub закончена. </li>
	<li>Приступим к настройке DNS-зоны. Небольшое прмечание: бывают такие регистраторы, которые не предоставляют настройку DNS-зоны, только NS-записи. Таким регистратором является fozzy.com. Чтобы настроить DNS-зону, можно делегировать права на <a href="http://cloudflare.com">CloudFlare</a> и настраивать записи через него. Так и сделаем.
Во-первых, добавим две A-записи на два адреса: <code>192.30.252.153</code> и <code>192.30.252.154</code>. Во-вторых, добавим CNAME-запись на www со значением YOUR-USERNAME.github.io. Вот какие записи мы получили:<img class="image featured" src="/post-img/life/5.png"/>
</li>
	<li>Теперь осталось подождать, когда DNS-записи вступят в силу, обычно нужно ждать до 24 часов. Можно перейти в настройки репозитория GitHub, где мы увидим следующее: <img class="image featured" src="/post-img/life/6.png"/><strong>Примечание.</strong> Если у вас есть другие репозитории в качестве github-pages, то ссылка на сайт будет в виде: ваш-домен/название-репозитория даже без CNAME-файла в каждом из репозиториев.<a href="//vikapitoshka.ru/example-gh-pages">Пример.</a></li>
</ol>
<p>Пока на этом всё, <a href="//github.com/ViKapitoshka/vikapitoshka.github.io">здесь</a> вы можете посмотреть исходный код. В <a href="//blog.vikapitoshka.ru/life/2017/subdomen.html">следующей статье</a> создадим субдомен сайта.</p>