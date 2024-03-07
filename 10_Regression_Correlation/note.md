# Correlation Coefficient
## สัมประสิทธ์สหสัมพันธ์อย่างง่าย

```
1 : df.corr()
2 : r,p_val = stats.pearsonr(x, y) ***

t_cal = r/Sr , Sr = np.sqrt((1-r**2)/(n-2)) , v=n-2
two tailed
t_crit_left = stats.ppf(alpha/2 , df = v)
t_crit_right = stats.isf(alpha/2, df = v)
p_val = 2*stats.t.sf(abs(t_cal),df = v)
```

# Regression Analysis
## วิเคราะห์การถดถอย
```
y_hat = b0+b1*x // y_hat = สัดส่วน % , x= กำไร

b0=0  , y at origin
b0<0  , y lower than origin
b0>0  , y upper than origin

b1=0  , x และ y ไม่มีความสัมพันธ์กัน
b1>0  , same direction
b1<0  , dif  direction

x
y
x_wconst = sm.add_constant(x)
lr = sm.OLS(y,x_wconst).fit()
print(lr.summary())

```

# การทดสอบสมมติฐานค่า B1 โดยการวิเคราะห์ความแปรปรวน
```
H0 : B1  = 0  อิสระ
H1 : B1 != 0  ไม่อิสระ

F = MSR/MSE

MSR = SSR/1 
MSE = SSE/(n-2)

เป็นright tailed **


