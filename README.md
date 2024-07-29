до миллиарда может быть излишней).

Ответ
function toReadable(number) {
    let dozens;
    let words = {
        0: 'zero',
        1: 'one',
        2: 'two',
        3: 'three',
        4: "four",
        5: 'five',
        6: 'six',
        7: "seven",
        8: 'eight',
        9: 'nine',
        10: 'ten',
        11: 'eleven',
        12: 'twelve',
        13: 'thirteen',
        14: 'fourteen',
        15: 'fifteen',
        16: 'sixteen',
        17: 'seventeen',
        19: 'nineteen',
        18: 'eighteen',
    };
    if (20 <= number) {
        dozens = {
            20: 'twenty',
            30: 'thirty',
            40: 'forty',
            50: 'fifty',
            60: 'sixty',
            70: 'seventy',
            80: 'eighty',
            90: 'ninety',
        };
        const num = String(number).split('');
        if (num.length === 2)
            if (number % 10 == 0) {
                return dozens[number];
            } else {
                if (num[0] == 2) {
                    return 'twenty' + ' ' + words[num[1]];
                }
                if (num[0] == 3) {
                    return 'thirty' + ' ' + words[num[1]];
                }
                if (num[0] == 4) {
                    return 'forty' + ' ' + words[num[1]];
                }
                if (num[0] == 5) {
                    return 'fifty' + ' ' + words[num[1]];
                }
                if (num[0] == 6) {
                    return 'sixty' + ' ' + words[num[1]];
                }
                if (num[0] == 7) {
                    return 'seventy' + ' ' + words[num[1]];
                }
                if (num[0] == 8) {
                    return 'eighty' + ' ' + words[num[1]];
                }
                if (num[0] == 9) {
                    return 'ninety' + ' ' + words[num[1]];
                }
            }
        if (num.length === 3)
            if (number % 100 != 0) {
                if (number % 10 === 0)
                    if (num[1] != 2) {
                        if (num[1] != 3) {
                            if (num[1] == 4) {
                                return words[parseInt(num[0])] + ' hundred ' + dozens[40];
                            }
                            if (num[1] == 5) {
                                return words[parseInt(num[0])] + ' hundred ' + dozens[50];
                            }
                            if (num[1] == 6) {
                                return words[parseInt(num[0])] + ' hundred ' + dozens[60];
                            }
                            if (num[1] == 7) {
                                return words[parseInt(num[0])] + ' hundred ' + dozens[70];
                            }
                            if (num[1] == 8) {
                                return words[parseInt(num[0])] + ' hundred ' + dozens[80];
                            }
                            if (num[1] == 9) {
                                return words[parseInt(num[0])] + ' hundred ' + dozens[90];
                            }
                        } else {
                            return words[parseInt(num[0])] + ' hundred ' + dozens[30];
                        }
                    } else {
                        return words[parseInt(num[0])] + ' hundred ' + dozens[20];
                    }
                if (num[1] == 0) {
                    return words[parseInt(num[0])] + ' hundred ' + words[num[2]];
                }
                if (num[1] == 1) {
                    if (num[2] == 0) {
                        return words[parseInt(num[0])] + ' hundred ' + words[10];
                    }
                    if (num[2] == 1) {
                        return words[parseInt(num[0])] + ' hundred ' + words[11];
                    }
                    if (num[2] == 2) {
                        return words[parseInt(num[0])] + ' hundred ' + words[12];
                    }
                    if (num[2] == 3) {
                        return words[parseInt(num[0])] + ' hundred ' + words[13];
                    }
                    if (num[2] == 4) {
                        return words[parseInt(num[0])] + ' hundred ' + words[14];
                    }
                    if (num[2] == 5) {
                        return words[parseInt(num[0])] + ' hundred ' + words[15];
                    }
                    if (num[2] == 6) {
                        return words[parseInt(num[0])] + ' hundred ' + words[16];
                    }
                    if (num[2] == 7) {
                        return words[parseInt(num[0])] + ' hundred ' + words[17];
                    }
                    if (num[2] == 8) {
                        return words[parseInt(num[0])] + ' hundred ' + words[18];
                    }
                    if (num[2] == 9) {
                        return words[parseInt(num[0])] + ' hundred ' + words[19];
                    }
                }
                if (num[1] == 2) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[20] + ' ' + words[num[2]];
                }
                if (num[1] == 3) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[30] + ' ' + words[num[2]];
                }
                if (num[1] == 4) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[40] + ' ' + words[num[2]];
                }
                if (num[1] == 5) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[50] + ' ' + words[num[2]];
                }
                if (num[1] == 6) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[60] + ' ' + words[num[2]];
                }
                if (num[1] == 7) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[70] + ' ' + words[num[2]];
                }
                if (num[1] == 8) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[80] + ' ' + words[num[2]];
                }
                if (num[1] == 9) {
                    return words[parseInt(num[0])] + ' hundred ' + dozens[90] + ' ' + words[num[2]];
                }
            } else {
                return words[parseInt(num[0])] + ' hundred';
            }
    } else {
        return words[number];
    }
}
