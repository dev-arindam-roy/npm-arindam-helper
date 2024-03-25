# Awesome Helpers
### A js library that have many awesome helper functions

## How to Install?

```js
npm i arindam-awesome-helpers

or 

npm install arindam-awesome-helpers
```

## How to use?

> In Node Js

```js
const helpers = require('arindam-awesome-helpers');

console.log(helpers.AwesomeHelpers.randomCode1());

console.log(helpers.AwesomeHelpers.randomStr1());

console.log(helpers.AwesomeHelpers.randomStr1(30));

console.log(helpers.AwesomeHelpers.randomToken2());

console.log(helpers.AwesomeHelpers.getFormat2('2024-06-12'));

console.log(helpers.AwesomeHelpers.isDateValid('03/12/2022'));
```

> In React, Vue, Angular & others..

```js
import { AwesomeHelpers } from './arindam-awesome-helpers'

console.log(AwesomeHelpers.randomCode1());

console.log(AwesomeHelpers.randomStr1());

console.log(AwesomeHelpers.randomStr1(30));

console.log(AwesomeHelpers.randomToken2());

console.log(AwesomeHelpers.getFormat2('2024-06-12'));

console.log(AwesomeHelpers.isDateValid('03/12/2022'));
```

## Awesome Functions

```js
export class AwesomeHelpers {

    static randomCode1():string {
        return (Math.random() + 1).toString(36).substring(7);
    }

    static randomCode2():string {
        return Math.random().toString(36).slice(2, 7);
    }

    static randomCode3():string {
        return Math.random().toString(36).slice(-5);
    }

    static randomCode4():string {
        return (+new Date * Math.random()).toString(36).substring(0, 6);
    }

    static randomStr1(strLen:number = 16):string {
        let result = '';
        const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
        const charactersLength = characters.length;
        let counter = 0;
        while (counter < strLen) {
            result += characters.charAt(Math.floor(Math.random() * charactersLength));
            counter += 1;
        }
        return result;
    }

    static randomStr2(strLen:number = 36):string {
        let result = '';
        for( ; result.length < strLen; result  += Math.random().toString(36).slice(2));
        return  result.slice(0, strLen);
    }

    static randomStr3(strLen:number = 8):string {
        return Math.random().toString(36).slice(2, strLen);
    }

    static randomBtoa():string {
        return btoa(Math.random().toString());
    }

    static randomToken1():string {
        let result = '';
        for(let i = 0; i < 6 ; i++) {
            result += Math.random().toString(36).slice(2);
        }
        return result;
    }

    static randomToken2(strLen:number = 36):string {
        let result = '';
        var charset = "abcdef#@*$!=ghijklmnopq#@*$!rstuvwxyz0123456789";
        for (let i = 0; i < strLen; i++)
            result += charset.charAt(Math.floor(Math.random() * charset.length));
        return result;
    }

    static uuid():string {
        return crypto.randomUUID();
    }

    static isDateValid(dateStr:string):boolean {
        return !isNaN(new Date(dateStr) as any);
    }

    static todayDate(format:string = '-'):string {
        const date = new Date();

        let day = date.getDate();
        let month = date.getMonth() + 1;
        let year = date.getFullYear();

        return `${day}${format}${month}${format}${year}`;
    }

    static todayMonthNameLong():string {
        return new Date().toLocaleString('default', { month: 'long' });
    }

    static todayMonthNameShort():string {
        return new Date().toLocaleString('default', { month: 'short' });
    }

    static todayDayNameFull():string {
        return new Date().toLocaleString('en-us', {weekday:'long'});
    }

    static todayDayNameShort():string {
        return new Date().toLocaleString('en-us', {weekday:'short'});
    }

    static todayOnlyDate():string {
        const date = new Date();
        return date.getDate().toString();
    }

    static todayOnlyMonth():string {
        const date = new Date();
        return (date.getMonth() + 1).toString();
    }

    static todayOnlyYear():string {
        const date = new Date();
        return date.getFullYear().toString();
    }

    static todayFormat1():string {
        return new Date().toLocaleString('en-us',{month:'long', year:'numeric', day:'numeric'});
    }

    static todayFormat2():string {
        return new Date().toLocaleString('en-us',{month:'short', year:'numeric', day:'numeric'});
    }

    static todayUsDate():string {
        return new Date().toLocaleDateString('en-us');
    }

    static todayMonthYear():string {
        return new Date().toLocaleString('en-us',{month:'short', year:'numeric'});
    }

    static todayLongFormat1():string {
        return `${this.todayDayNameFull()}, ${this.todayFormat1()}`;
    }

    static todayLongFormat2():string {
        return `${this.todayDayNameFull()}, ${this.todayFormat2()}`;
    }

    static todayLongFormat3():string {
        return `${this.todayDayNameShort()}, ${this.todayFormat2()}`;
    }

    static todayLongFormat4():string {
        return new Date().toLocaleString('en-US', {weekday:'short', day:'2-digit', month: 'short', year:'2-digit'});
    }

    static todayLongFormat5():string {
        return new Date().toLocaleString('en-US', {weekday:'short', day:'2-digit', month: 'short', year:'numeric'});
    }

    static todayLongFormat6():string {
        return `${this.todayDayNameFull()}, ${this.todayDate()}`;
    }

    static todayLongFormat7():string {
        return `${this.todayDayNameFull()}, ${this.todayDate('/')}`;
    }

    static todayLongFormat8():string {
        return `${this.todayDayNameShort()}, ${this.todayDate()}`;
    }

    static todayLongFormat9():string {
        return `${this.todayDayNameShort()}, ${this.todayDate('-')}`;
    }

    static todayHoursMinute():string {
        return new Date().toLocaleString('en-US', {hour:'numeric', minute:'numeric'});
    }

    static todayHoursMinuteSecond():string {
        return new Date().toLocaleString('en-US', {hour:'numeric', minute:'numeric', second:'numeric'});
    }

    static todayOnlyHours():string {
        return new Date().toLocaleString('en-US', {hour:'numeric'});
    }

    static todayOnlyMinute():string {
        return new Date().toLocaleString('en-US', {minute:'numeric'});
    }

    static todayOnlySecond():string {
        return new Date().toLocaleString('en-US', {second:'numeric'});
    }

    static getDate(dateStr:string, format:string = '-'):string {
        const date = new Date(dateStr);

        let day = date.getDate();
        let month = date.getMonth() + 1;
        let year = date.getFullYear();

        return `${day}${format}${month}${format}${year}`;
    }

    static getMonthNameLong(dateStr:string):string {
        return new Date(dateStr).toLocaleString('default', { month: 'long' });
    }

    static getMonthNameShort(dateStr:string):string {
        return new Date(dateStr).toLocaleString('default', { month: 'short' });
    }

    static getDayNameFull(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-us', {weekday:'long'});
    }

    static getDayNameShort(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-us', {weekday:'short'});
    }

    static getOnlyDate(dateStr:string):string {
        const date = new Date(dateStr);
        return date.getDate().toString();
    }

    static getOnlyMonth(dateStr:string):string {
        const date = new Date(dateStr);
        return (date.getMonth() + 1).toString();
    }

    static getOnlyYear(dateStr:string):string {
        const date = new Date(dateStr);
        return date.getFullYear().toString();
    }

    static getFormat1(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-us',{month:'long', year:'numeric', day:'numeric'});
    }

    static getFormat2(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-us',{month:'short', year:'numeric', day:'numeric'});
    }

    static getUsDate(dateStr:string):string {
        return new Date(dateStr).toLocaleDateString('en-us');
    }

    static getMonthYear(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-us',{month:'short', year:'numeric'});
    }

    static getLongFormat1(dateStr:string):string {
        return `${this.getDayNameFull(dateStr)}, ${this.getFormat1(dateStr)}`;
    }

    static getLongFormat2(dateStr:string):string {
        return `${this.getDayNameFull(dateStr)}, ${this.getFormat2(dateStr)}`;
    }

    static getLongFormat3(dateStr:string):string {
        return `${this.getDayNameShort(dateStr)}, ${this.getFormat2(dateStr)}`;
    }

    static getLongFormat4(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {weekday:'short', day:'2-digit', month: 'short', year:'2-digit'});
    }

    static getLongFormat5(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {weekday:'short', day:'2-digit', month: 'short', year:'numeric'});
    }

    static getLongFormat6(dateStr:string):string {
        return `${this.getDayNameFull(dateStr)}, ${this.getDate(dateStr)}`;
    }

    static getLongFormat7(dateStr:string):string {
        return `${this.getDayNameFull(dateStr)}, ${this.getDate(dateStr, '/')}`;
    }

    static getLongFormat8(dateStr:string):string {
        return `${this.getDayNameShort(dateStr)}, ${this.getDate(dateStr)}`;
    }

    static getLongFormat9(dateStr:string):string {
        return `${this.getDayNameShort(dateStr)}, ${this.getDate(dateStr, '-')}`;
    }

    static getHoursMinute(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {hour:'numeric', minute:'numeric'});
    }

    static getHoursMinuteSecond(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {hour:'numeric', minute:'numeric', second:'numeric'});
    }

    static getOnlyHours(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {hour:'numeric'});
    }

    static getOnlyMinute(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {minute:'numeric'});
    }

    static getOnlySecond(dateStr:string):string {
        return new Date(dateStr).toLocaleString('en-US', {second:'numeric'});
    }
}
```

## Thanks!!

