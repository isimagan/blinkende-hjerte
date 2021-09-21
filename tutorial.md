# Blinkende hjerte

## Intro @showdialog
Vi skal animere et hjerte som skal blinke 10 ganger når den er ferdig.

![Hjerte](https://isimagan.github.io/blinkende-hjerte/hjerte.png)

## Steg 1
Når vi skal animere et hjerte kan vi ikke bruke hjerte-ikonet du finner på ``||basic:vis ikon||``.

Vi må lage det selv, og vi skal bruke ``||basic:vis skjerm||``. Alt dette skal vi sette inn i ``||basic:gjenta for alltid||``.

![Ikke vis ikon](https://isimagan.github.io/blinkende-hjerte/visIkon.jpg)
``` blocks
basic.forever(function(){})
```

## Steg 2
Sett inn ``||basic:vis skjerm||`` og vis kun en prikk i midten på den nederste linja.
``` blocks
basic.forever(function(){
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
})
```

## Steg 3
Sett inn en ny ``||basic:vis skjerm||``, ta med den samme prikken, men vi fortsetter på neste del av hjertet på linja over.
``` blocks
basic.forever(function(){
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
})
```

## Steg 4
Fortsett helt til du er ferdig med **nest siste** bilde.
``` blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . # . # .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
})
```

## Steg 5
Hva mangler? Jo, den siste prikken midt på nest øverste linje. Men her skal vi begynne med blinkingen.

## Steg 6
Under den nederste ``||basic:vis skjerm||`` setter du inn en ``gjenta``-løkke. Gå inn på ``||loops:Løkker||`` og sett inn ``||loops:gjenta 4 ganger||``. Endre ``4``-tallet til ``10``.
``` blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . # . # .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    for (let index = 0; index < 4; index++) {}
})
```

### Steg 6a
Endre ``4``-tallet til ``10``.
``` blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . # . # .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    for (let index = 0; index < 10; index++) {}
})
```

## Steg 7
Inni ``||loops:gjenta||``-blokken setter du inn den siste ``||basic:vis skjerm||`` med den siste biten som mangler.
``` blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . # . # .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    for (let index = 0; index < 10; index++) {
        basic.showLeds(`
        . # . # .
        # . # . #
        # . . . #
        . # . # .
        . . # . .
        `)
    }
})
```

## Steg 8
Så må vi tømme skjermen. Før vi gjør det må vi vente litt så hjertet ikke forsvinner med en gang.
1. Sett inn ``||basic:pause (ms) 100||``, og endre ``100``-tallet til ``200`` eller ``500``.
2. Sett inn ``||basic:tøm skjermen||``
3. Sett inn en ny ``||basic:pause||``, like lang som den forrige.

``` blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . # . # .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    for (let index = 0; index < 10; index++) {
        basic.showLeds(`
        . # . # .
        # . # . #
        # . . . #
        . # . # .
        . . # . .
        `)
        basic.pause(200)
        basic.clearScreen()
        basic.pause(200)
    }
})
```

## Steg 9
Ser du at det funker?

Siden du har satt inn dette i ``||basic:gjenta for alltid||`` vil denne gå hele tiden. Men vi vil ha en liten pause til før den starter på nytt. Så **under** (ikke *inni*) ``||loops:gjenta||``-blokken setter vi inn en pause på 1 sekund (``1000 ms``).
``` blocks
basic.forever(function () {
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . . . . .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . . . .
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        . . . . .
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . . . . .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    basic.showLeds(`
        . # . # .
        # . . . #
        # . . . #
        . # . # .
        . . # . .
        `)
    for (let index = 0; index < 10; index++) {
        basic.showLeds(`
        . # . # .
        # . # . #
        # . . . #
        . # . # .
        . . # . .
        `)
        basic.pause(200)
        basic.clearScreen()
        basic.pause(200)
    }
    basic.pause(1000)
})
```

## Ferdig @showdialog
**Du er ferdig!**

Når du har trykket på **Slutt** tar du skjermbilde og limer inn i BookCreator. Overskriften skal være **Blinkende hjerte**.

## Slutt
Vil du ha den over til micro:biten? Husker du hvordan? Hvis ikke så kan du se på Showbie hvordan det gjøres.

Trykk på **Slutt**.

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("https://makecode.microbit.org/", "isimagan/blinkende-hjerte");</script>
