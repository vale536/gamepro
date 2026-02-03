//% color="#54CE76" icon="\uf0022"
namespace gamePro {
    declare const info: any
    declare const game: any
    declare const GameOverReason: any
    declare function pause(ms: number): void

    export enum Mode {
        //% block="all"
        All = 0,
        //% block="pause"
        Pause = 1,
        //% block="reset"
        Reset = 2
    }

    // ===== 12 REPORTERS =====

    //% block="random $min to $max"
    //% min.defl=0 max.defl=100
    //% blockId="r1"
    //% group="Math"
    //% weight=100
    export function rnd(min: number, max: number): number {
        return Math.floor(Math.random() * (max - min + 1)) + min
    }

    //% block="abs $n"
    //% n.defl=0
    //% blockId="r2"
    //% group="Math"
    //% weight=99
    export function abs(n: number): number {
        return Math.abs(n)
    }

    //% block="sqrt $n"
    //% n.defl=16
    //% blockId="r3"
    //% group="Math"
    //% weight=98
    export function sqrt(n: number): number {
        return Math.sqrt(n)
    }

    //% block="pow $a to $b"
    //% a.defl=2 b.defl=3
    //% blockId="r4"
    //% group="Math"
    //% weight=97
    export function pow(a: number, b: number): number {
        return Math.pow(a, b)
    }

    //% block="round $n"
    //% n.defl=3.5
    //% blockId="r5"
    //% group="Math"
    //% weight=96
    export function rnd2(n: number): number {
        return Math.round(n)
    }

    //% block="floor $n"
    //% n.defl=3.9
    //% blockId="r6"
    //% group="Math"
    //% weight=95
    export function flr(n: number): number {
        return Math.floor(n)
    }

    //% block="ceiling $n"
    //% n.defl=3.1
    //% blockId="r7"
    //% group="Math"
    //% weight=94
    export function ceil(n: number): number {
        return Math.ceil(n)
    }

    //% block="max $a $b"
    //% a.defl=10 b.defl=5
    //% blockId="r8"
    //% group="Math"
    //% weight=93
    export function mx(a: number, b: number): number {
        return Math.max(a, b)
    }

    //% block="min $a $b"
    //% a.defl=5 b.defl=10
    //% blockId="r9"
    //% group="Math"
    //% weight=92
    export function mn(a: number, b: number): number {
        return Math.min(a, b)
    }

    //% block="sin $d deg"
    //% d.defl=45
    //% blockId="r10"
    //% group="Math"
    //% weight=91
    export function sin(d: number): number {
        return Math.sin((d * Math.PI) / 180)
    }

    //% block="cos $d deg"
    //% d.defl=0
    //% blockId="r11"
    //% group="Math"
    //% weight=90
    export function cos(d: number): number {
        return Math.cos((d * Math.PI) / 180)
    }

    //% block="$a mod $b"
    //% a.defl=10 b.defl=3
    //% blockId="r12"
    //% group="Math"
    //% weight=89
    export function mod(a: number, b: number): number {
        return a % b
    }

    // ===== 12 BOOLEANS =====

    //% block="$a = $b"
    //% a.defl=5 b.defl=5
    //% blockId="b1"
    //% group="Logic"
    //% weight=88
    export function eq(a: number, b: number): boolean {
        return a === b
    }

    //% block="$a > $b"
    //% a.defl=10 b.defl=5
    //% blockId="b2"
    //% group="Logic"
    //% weight=87
    export function gt(a: number, b: number): boolean {
        return a > b
    }

    //% block="$a < $b"
    //% a.defl=3 b.defl=5
    //% blockId="b3"
    //% group="Logic"
    //% weight=86
    export function lt(a: number, b: number): boolean {
        return a < b
    }

    //% block="$n even"
    //% n.defl=4
    //% blockId="b4"
    //% group="Logic"
    //% weight=85
    export function evn(n: number): boolean {
        return n % 2 === 0
    }

    //% block="$n odd"
    //% n.defl=5
    //% blockId="b5"
    //% group="Logic"
    //% weight=84
    export function odd(n: number): boolean {
        return n % 2 !== 0
    }

    //% block="$n pos"
    //% n.defl=5
    //% blockId="b6"
    //% group="Logic"
    //% weight=83
    export function pos(n: number): boolean {
        return n > 0
    }

    //% block="$n neg"
    //% n.defl=-5
    //% blockId="b7"
    //% group="Logic"
    //% weight=82
    export function neg(n: number): boolean {
        return n < 0
    }

    //% block="$n zero"
    //% n.defl=0
    //% blockId="b8"
    //% group="Logic"
    //% weight=81
    export function zero(n: number): boolean {
        return n === 0
    }

    //% block="$t1 = $t2"
    //% t1.defl="hi" t2.defl="hi"
    //% blockId="b9"
    //% group="Logic"
    //% weight=80
    export function teq(t1: string, t2: string): boolean {
        return t1 === t2
    }

    //% block="$n in $min to $max"
    //% n.defl=5 min.defl=0 max.defl=10
    //% blockId="b10"
    //% group="Logic"
    //% weight=79
    export function rng(n: number, min: number, max: number): boolean {
        return n >= min && n <= max
    }

    //% block="true"
    //% blockId="b11"
    //% group="Logic"
    //% weight=78
    export function tru(): boolean {
        return true
    }

    //% block="false"
    //% blockId="b12"
    //% group="Logic"
    //% weight=77
    export function fls(): boolean {
        return false
    }

    // ===== 5 ACTION BLOCKS =====

    //% block="sprite $s at $x $y"
    //% s.shadow=variables_get
    //% x.defl=80 y.defl=60
    //% blockId="a1"
    //% group="Sprites"
    //% weight=76
    export function pos_s(s: any, x: number, y: number): void {
        s.setPosition(x, y)
    }

    //% block="sprite $s move $dx $dy"
    //% s.shadow=variables_get
    //% dx.defl=10 dy.defl=10
    //% blockId="a2"
    //% group="Sprites"
    //% weight=75
    export function mv_s(s: any, dx: number, dy: number): void {
        s.x += dx
        s.y += dy
    }

    //% block="sprite $s scale $n"
    //% s.shadow=variables_get
    //% n.defl=100
    //% blockId="a3"
    //% group="Sprites"
    //% weight=74
    export function scl_s(s: any, n: number): void {
        s.setScale(n / 100)
    }

    //% block="destroy $s"
    //% s.shadow=variables_get
    //% blockId="a4"
    //% group="Sprites"
    //% weight=73
    export function dst(s: any): void {
        s.destroy()
    }

    //% block="score add $n"
    //% n.defl=10
    //% blockId="a5"
    //% group="Game"
    //% weight=72
    export function sco(n: number): void {
        info.changeScoreBy(n)
    }

    // ===== 5 CONNECTABLE BLOCKS =====

    //% block="do $h"
    //% blockId="c1"
    //% group="Control"
    //% handlerStatement=1
    //% weight=71
    export function do1(h: () => void): void {
        if (h) h()
    }

    //% block="repeat $n times $h"
    //% n.defl=4
    //% blockId="c2"
    //% group="Control"
    //% handlerStatement=2
    //% weight=70
    export function rep(n: number, h: () => void): void {
        for (let i = 0; i < n; i++) if (h) h()
    }

    //% block="if $c then $h"
    //% blockId="c3"
    //% group="Control"
    //% handlerStatement=2
    //% weight=69
    export function if1(c: boolean, h: () => void): void {
        if (c && h) h()
    }

    //% block="if $c then $h1 else $h2"
    //% blockId="c4"
    //% group="Control"
    //% handlerStatement=2
    //% handlerStatement=3
    //% weight=68
    export function ife(c: boolean, h1: () => void, h2: () => void): void {
        if (c) { if (h1) h1() } else { if (h2) h2() }
    }

    //% block="wait $t ms"
    //% t.defl=1000
    //% blockId="c5"
    //% group="Control"
    //% weight=67
    export function wt(t: number): void {
        pause(t)
    }

    // ===== 4 MORE REPORTERS =====

    //% block="get score"
    //% blockId="r13"
    //% group="Game"
    //% weight=66
    export function get_s(): number {
        return info.score()
    }

    //% block="get life"
    //% blockId="r14"
    //% group="Game"
    //% weight=65
    export function get_l(): number {
        return info.life()
    }

    //% block="sprite $s x"
    //% s.shadow=variables_get
    //% blockId="r15"
    //% group="Sprites"
    //% weight=64
    export function x_s(s: any): number {
        return s.x
    }

    //% block="sprite $s y"
    //% s.shadow=variables_get
    //% blockId="r16"
    //% group="Sprites"
    //% weight=63
    export function y_s(s: any): number {
        return s.y
    }

    // ===== 4 CAP BLOCKS =====

    //% block="stop $m"
    //% blockId="cap1"
    //% group="End"
    //% weight=62
    export function stp(m: Mode): void {
        if (m === Mode.All) game.over(GameOverReason.Timeout)
        else if (m === Mode.Pause) game.pause()
        else game.reset()
    }

    //% block="win"
    //% blockId="cap2"
    //% group="End"
    //% weight=61
    export function win(): void {
        game.over(GameOverReason.Win)
    }

    //% block="lose"
    //% blockId="cap3"
    //% group="End"
    //% weight=60
    export function los(): void {
        game.over(GameOverReason.Lose)
    }

    //% block="reset"
    //% blockId="cap4"
    //% group="End"
    //% weight=59
    export function rst(): void {
        game.reset()
    }
}
