			i-7013D 基本协议说明

 'START----------------------------------------------------------START
    '设置工作参数协议
    '%AANN20CCFF[CheckSum](CR)   / TT 为模块类型，i-7013D 固定为 20
    'AA 地址，NN 新地址，CC 波特率：
    'Code      03   04   05   06   07    08    09    0A
    'Baud rate 1200 2400 4800 9600 19200 38400 57600 115200
    'FF: 00 无校验，40 累加和
    'Response:
    'Valid Command: !NN[CHKSUM](CR)
    'Invalid Command: ?NN[CHKSUM](CR)
    '注意：修改波特率和校验方式必须在 INIT 模式下，
    '但修改模块地址不必在 INIT 模式下
    'END--------------------------------------------------------------END


    'START----------------------------------------------------------START
    '查询模块 EEPROM 中的工作参数
    '$AA2
    '返回：!AATTCCFF, 错误：?AA
    'END--------------------------------------------------------------END


    'START----------------------------------------------------------START
    '读取温度
    '#AA
    '#为本协议的标志，AA为模块地址，如此即可读取当前温度。
    '返回：>(Data)，例如：“>+020.9597”，但数码管只有 5 个
    '错误：?AA
    'END--------------------------------------------------------------END