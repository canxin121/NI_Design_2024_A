1. NE555 输出1561Hz的方波：
    $$
    f = \frac{1}{\ln(2) \times (R1 + 2 \times R2) \times C}
    $$
    取 C = 0.01 μF,R1 = 1kΩ,R2 = 45.7106kΩ
2. 滤波产生1次，3次，5次谐波：
    1次谐波使用[ButterWorth](LowpassFilter-2ndOrderButterworth.pdf)低通滤波器(增益为2)
    3,5次谐波使用[DABP](mt-209_cn_DABP.pdf)带通滤波器(增益为2)
    
    然后对各次输出进行适当移向，使其相位与方波一致
3. 