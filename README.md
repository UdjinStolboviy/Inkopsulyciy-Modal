# Inkopsulyciy-Modal


// НЕ защионие даные 
let app = {
    date: 45 // НЕ защионие даные 
};
console.log(app);

// НЕ защионие даные 
function User(name, age) {
    this.name = name;
    this.age = age;

    this.say = function () {
        console.log(`Имя пользователя ${this.name},возсраст: ${this.age}`);

    };
}

let ivan = new User('Ivan', 25);
console.log(ivan.name);
console.log(ivan.age);

ivan.age = 30;
ivan.name = "Alex";

// Делаем  инкапсуляция  для  защиты  даных

function User(name, age) {
    let userName = name,
     userAge = age;

    this.say = function () {
        console.log(`Имя пользователя ${userName},возсраст: ${userAge}`);

    };
    this.getAge = function () { //добавляем  значение 
        return userAge;
    };
    // Меняем  значение 
    this.setAge = function (age) {
        if (typeof age === 'number' && age > 0 && age < 110) {
            userAge = age;
        } else {
            console.log("Недопустимое  значение ");
        }
    };
}

ivan.setAge(30);

ivan.say();



//MODAL


let number = 1; // глобальная переменая

// Модуль

(function () {
    //1 met Анонимная само вызывающеесся  функция создала  свою  область  видемости.
    let number = 2;
    console.log(number);

    return console.log(number + 3);
}());
 // Функция декларейшен  не может быть безимянной 
 // анонимная функция  то  ето  фанкшен  експрешен может быть беземяная 


 // 2 метот использование  обектного интефейса 
let user = (function () {
    let privat = function () {
        console.log('I am privat');
    };

    return {
        sayHello: function () {
            console.log('hello');
        }
    };
}());

console.log(user);
console.log(user.sayHello());
// 3 метод 

let user1 = (function () {
    let privat = function () {
        console.log('I am privat');
    };
    let sayHello = function () {
        console.log('hello');
    }
    return {
        sayHello: sayHello //возврат  во  внешний мир  приватную  функцию
        
    };
}());

console.log(user1);
console.log(user1.sayHello());
