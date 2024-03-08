```
 H0 = {<= ,>= , =}
 H1 = {< ,> ,!=}

ดู ที่ H1
 !=  = twotailed 
 <   = left tailed
 >   = right tailed


```

```
p_val  > alpha  = H0
p_val <= alpha  = H1

right :
.sf(_cal)  to p_val
.isf(p_val) to cal

left :
.cdf(_cal) to p_val 
.ppf(p_val) to cal

twotailed :
left_crit = .ppf(alpha/2)
right_crit = .isf(alpha/2)

2*.sf(abs(_cal)) = p_val   (Z,t)

2*min(.cdf(X2_cal),.sf(X2_cal)) = p_val  (X2) (ทบทวนแต่ไม่มีใช้ในเรื่องนี้)

```

# ทดสอบค่าเฉลี่ย ประชากร 1 กลุ่ม

```
know variance  = Z

dont know variance
- n>=30 -> Z
- n<30  -> t

Z :
Z_cal ,p_val = ztest(x1=
                    value =  (ค่าเฉลี่ยโจทย์)
                    alternative = (larger , smaller , twotailed) ดูในเอกสารอีกที
                        )
t  คล้ายๆกัน ดูในเอกสารอีกที
            
```

# ทดสอบค่าเฉลี่ย ประชากร 2 กลุ่ม ที่เป็นอิสระ

```
มี 4 แบบ
1 know variance = Z
dont know variance 
2 n1,n2>=30 = Z
3 <30 var1==var2 = t
4 <30 var1!=var2 = t

stats.ttest_ind(a= 
                b= 
                alternative
                equal_var = 
                )


```

# สัดส่วนประชากร 1 กลุ่ม

```
use Z

z_cal ,p_val  = proportions_ztest(count = ตัวอย่าง
                                nobs = ทั้งหมด
                                value = P
                                alternative = 
                                prop_var = value)

```

# สัดส่วนประชากร 2 กลุ่ม

```
use Z

z_cal ,p_val  = proportions_ztest(count = [ตัวอย่าง1,ตัวอย่าง2]
                                nobs = [ทั้งหมด1,ทั้งหมด2]
                                value = P (0 ถ้าไม่แตกต่างกัน)
                                alternative = 
                                )


```

# ทดสอบแปรปรวนของประชากร 1 กลุ่ม

```
ใช้ X2


```

# ทดสอบแปรปรวนของประชากร 2 กลุ่ม อิสระต่อกัน
```
use F
```

