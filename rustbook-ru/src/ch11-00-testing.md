# Написание автоматизированных тестов

В своём эссе 1972 года “The Humble Programmer,” Edsger W. Dijkstra сказал, что «Тестирование программы может быть очень эффективным способом показать наличие ошибок, но это безнадёжно неадекватно для показа их отсутствия». Это не значит, что мы не должны пытаться тестировать столько, сколько мы можем!

Правильность в наших программах - это степень, в которой наш код выполняет то для чего он предназначен. Rust разработан с высокой степенью заботы о правильности программ, но правильность сложна и её не легко доказать. Система типов Rust несёт огромную часть этого бремени, но система типов не может обнаружить каждый вид некорректности. Таким образом, Rust включает в себя поддержку написания автоматизированных программных тестов внутри языка.

В качестве примера, скажем, мы пишем функцию с именем `add_two` которая добавляет 2 к любому числу передаваемому в неё. Сигнатура этой функции принимает параметром целое число и возвращает в результате целое число. Когда мы реализуем и компилируем такую функцию, Rust выполняет все проверки типов и заимствований про которые вы уже узнали, чтобы убедиться, например, что мы не передаём значение `String` или неверную ссылку в эту функцию. Но Rust *не может* проверить, что данная функция будет делать именно то, что мы намереваемся получить, что она возвращает входной параметр плюс 2, а не скажем, параметр плюс 10 или параметр минус 50! Это то, где тесты приходят на помощь.

Мы можем написать тесты, которые утверждают, например, что когда мы передаём `3` в функцию `add_two`, возвращаемое значение будет `5`. Мы можем запускать эти тесты всякий раз, когда мы вносим изменения в наш код, чтобы убедиться, что любое существующее правильное поведение не изменилось.

Тестирование - сложный навык: мы не сможем охватить все детали написания хороших тестов в одной главе, но мы обсудим основные подходы к тестированию в Rust. Мы поговорим об аннотациях и макросах, доступных вам для написания тестов, о поведении по умолчанию и параметрах, предусмотренных для запуска тестов, а также о том, как организовать тесты в модульные тесты и интеграционные тесты.
