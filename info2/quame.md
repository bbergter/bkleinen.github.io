---
title: Info2 Questions & Answers Sommersemester 2015
author: kleinen
layout: page
---

{% include ss2015/info2.md %}

# Questions

See [http://ba-thesis.herokuapp.com/questions](http://ba-thesis.herokuapp.com/questions)

Ask new questions here: [http://ba-thesis.herokuapp.com/questions](http://ba-thesis.herokuapp.com/questions)

# Answers

## Question 3 .:  how can I draw a Rectangle on the screen?

This question was asked on May 26, 2015 10:57.

### Answer:
I've provided a scaffold project which can be found here in case you can't find your sources from last
semester ;-) - [https://github.com/htw-imi-info2/SierpinskyTriangleStart](https://github.com/htw-imi-info2/SierpinskyTriangleStart)

## Question 4+5: static context

This question was asked on May 26, 2015 17:29.

 Ich bekomme ständig die Fehlermeldung "Cannot make a static reference to the non-static field/method [..]". Dieses Problem lässt sich zwar sehr leicht durch ein "static" vor dem entsprechenden Feld bzw. Methode lösen. Ich wüsste aber trotzdem gern was genau hinter "static reference" bzw. "non-static ..." steht.

 Ein Nachtrag zur vorhergehenden Frage (#4): Ebenfalls verwirren mich Fehlermeldungen wie "The static method [..] from the type [..] should be accessed in a static way".

### Answer:

Das Keyword `static` vor einem Feld oder einer Methode bedeutet, dass dieses Feld zur Klasse gehört. Man kann sich das so vorstellen, als sei die Klasse selbst wie ein Objekt, d.h. eine Instanz (in anderen Programmiersprachen sind sie das tatsächlich, z.B. ist in Ruby die Klasse eine Instanz der Klasse `Class`).

D.h. wenn sie z.B eine Klasse "Auto" haben, dann können sie ganz viele Instanzen (Objekte, die zu dieser Klasse gehören) haben: `auto1`, `auto2`, `auto3`, und sie haben immer die
Klasse selbst, `Auto`, die ein bischen wie ein Objekt ist, d.h. sie kann Felder (Klassenvariablen im Unterschied zu Instanzvariablen) und Methoden haben, beides mit `static`gekennzeichnet.

    class Auto{
      static int standardFarbeFuerNeueAutos = Color.BLACK;
      Color farbe;
    }

Jede dieser Instanzen hat einen eigenen Satz von Instanzvariablen (Feldern) - d.h. `auto1.farbe`, `auto2.farbe`, `auto3.farbe` sind verschiedene Variablen und können verschiedene Werte haben.
Wenn eine Variable zur Klasse gehört, d.h. mit static gekennzeichnet ist, dann gehört sie zur Klasse, also zu `Auto` - wie hier `standardFarbeFuerNeueAutos` - diese "hängt" nicht an einer der drei Instanzen, sondern der Klasse selbst, und muss ggfs. entsprechend referenziert werden: `Auto.standardFarbeFuerNeueAutos`.

Den Fehler bekommen Sie vermutlich, weil Sie in der main - Klasse - die immer statisch sein muss, weil man beim Start des Programms noch keine Instanz von irgendwas hat - anfangen zu programmieren.

Eine gute Lösung dafür ist, direkt in den Kontext einer Instanz zu wechseln, z.B.:

    class MyProgram{
      public static void main(String [] args){
        // this is within the static context
        MyProgram theInstance = new MyProgram();
        theInstance.doSomething();
      }
      void doSomething(){
        // and now we are within an instance.
      }

    }

Siehe auch [Understanding Class Members](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html) im Java-Tutorial
oder entsprechende Abschnitte über den Unterschied zwischen Klassen und Objekten und Klassenvariablen in anderen Quellen.

# About

Felix Brix has taken on the project of developing an gamified Q&A application for Info1 and Info2.

Currently, he is collecting Questions to have material for his concept.
Eventually, this will be an App that can be used by IMI (and other students)
for Q&A, maybe somewhat like Stack Overflow with the possibility to upvote
questions and also encouraging students to answer questions and earning credits
for the course if they provided useful answers to their peers.

You can enter questions anonymously here: [http://ba-thesis.herokuapp.com/](http://ba-thesis.herokuapp.com/),
and I'll answer them around Saturday at noon latest for the current week.
You find a list of questions here [http://ba-thesis.herokuapp.com/questions](http://ba-thesis.herokuapp.com/questions) and
their answers there: [QUAME](quame.html)