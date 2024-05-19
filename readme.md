## 流程
1. NE555 输出1561Hz的方波：
    ```math
    f = \frac{1}{\ln(2) \times (R1 + 2 \times R2) \times C}
    ```
    取
    ```math
    C = 0.01 μF,R1 = 1kΩ,R2 = 45.7106kΩ    
    ```
3. 对方波滤波产生1次，3次，5次谐波：
    1次谐波使用[ButterWorth](LowpassFilter-2ndOrderButterworth.pdf)低通滤波器(增益为1)
    3,5次谐波使用[DABP](mt-209_cn_DABP.pdf)带通滤波器(增益为1)
    然后对各次输出进行适当移向，使其相位与方波一致
    得到![各次谐波与方波对比图](pics/各次谐波与方波对比图.png)
4. 将各次谐波使用同向放大器相加，得到合成方波.
    得到![合成波形](pics/合成方波.png)
5. 对3中合成波形进行 先反向积分后反向放大，使Vpp=8V
    得到![三角波形](pics/三角波.png)
6. 合成李沙育波形:
    使用方波产生模块+基波ADBP模块+向后(0-180°)的移相模块
    使用20k和1G两个滑动变阻器串联控制移向角度
    接入电阻值实际是Max * (1-percent)
    20k: 100% 1G: 100% 移相0°
    ![李沙育0°](pics/李沙育0°.png)
    20k: 80% 1G: 100% 移相45°
    ![李沙育45°](pics/李沙育45°.png)
    20k: 50% 1G: 100% 移相90°
    ![李沙育90°](pics/李沙育90°.png)
    20k: 20% 1G: 100% 移相135°
    ![李沙育135°](pics/李沙育135°.png)
    20k: 0% 1G: 0% 移相180°
    ![李沙育180°](pics/李沙育180°.png)
## 参考
1. [运放移相电路](https://blog.csdn.net/daijingxin/article/details/89365295)
2. [DABP带通滤波器](https://www.analog.com/media/cn/training-seminars/tutorials/mt-209_cn.pdf)
3. [Butterworth低通滤波器 设计结果](LowpassFilter-2ndOrderButterworth.pdf)
    来自[Ni滤波器设计](https://webench.ti.com/filter-design-tool/)
4. [NE555方波生成电路](https://blog.csdn.net/XJIALun/article/details/125594374)
