const units = ["", "один", "два", "три", "четыре", "пять", "шесть", "семь", "восемь", "девять"];
const teens = ["", "одиннадцать", "двенадцать", "тринадцать", "четырнадцать", "пятнадцать", "шестнадцать", "семнадцать", "восемнадцать", "девятнадцать"];
const tens = ["", "десять", "двадцать", "тридцать", "сорок", "пятьдесят", "шестьдесят", "семьдесят", "восемьдесят", "девяносто"];
const thousands = ["", "тысяча", "миллион", "миллиард"];

function toReadable(number) {
    if (number === 0) return 'ноль';

    let words = '';

    function getBelowHundred(n) {
        if (n < 10) return units[n];
        else if (n >= 11 && n <= 19) return teens[n - 10];
        else {
            let ten = Math.floor(n / 10);
            let unit = n % 10;
            return tens[ten] + (unit ? ' ' + units[unit] : '');
        }
    }

    function getBelowThousand(n) {
        let hundred = Math.floor(n / 100);
        let remainder = n % 100;
        let word = '';
        if (hundred) word += units[hundred] + 'сот';
        if (remainder) word += (word ? ' ' : '') + getBelowHundred(remainder);
        return word;
    }

    let thousandCounter = 0;

    while (number > 0) {
        let chunk = number % 1000;
        if (chunk) {
            let chunkWord = getBelowThousand(chunk);
            if (thousands[thousandCounter]) chunkWord += ' ' + thousands[thousandCounter];
            words = chunkWord + (words ? ' ' + words : '');
        }
        number = Math.floor(number / 1000);
        thousandCounter++;
    }

    return words.trim();
}

module.exports = toReadable; Human-Readable-Number
