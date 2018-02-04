# getwarrants
1. 權證網頁spec
{"INSTR_STKID":權證id,"INSTR_NAME":權證名,
"BID1_PRICE":買價,"BID1_VOLUME":買量,"DEAL":成交價,"HIGH":最高價,"LOW":最低價,
"CHANGE_PERCENT":漲跌幅,"VOLUME":成交量,"BID_ASK_SPREAD_PERCENT":買賣價差比,
"BID_IMP_VOL":BIV,"ASK_IMP_VOL":SIV,"LEVERAGE":槓桿,"DELTA":delta,
"THETA":-0.00486980008076462,"INSWRT_EXECRATE":行使比例,"INSWRT_STRIKE":履約價,
"LAST_DAYS":剩餘天數,"IN_OUT_PERCENT":價內外,"OUTSTANDING_PERCENT":流通率,
"UND_INSTR_INSNBR":網頁index,"UND_INSTR_STKID":標的id,"UND_INSTR_NAME":標的名,
"UND_DEAL":標的成交價}

2. getgoodwarrants(stockid, type, part, lev, vol, day, swrt, inout):
用此function得到warrants資訊
stockid:標的id(ex.8299) 
type:權證種類(b:購, s:g=售)
part:挑選的範圍(all:全部, part:依照條件篩選的部分)
lev:槓桿
vol:成交量
day:剩餘天數
swrt:行使比例
inout:價內外
條件篩選為邏輯＋數字
大於more 小於less 介於between（兩數字間用and分隔）
因次大於100為more100

ex. ret = getwarrants.getgoodwarrants(8299, s, part, more3.8, more100, more30, more0.01, between-13and50)
