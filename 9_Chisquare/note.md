#คุณภาพ
# chisquare test only have right tailed

# อัตราส่วน

```
only have right tailed
H0 : อัตราส่วน = 1:1
H1 : อัตราส่วน != 1:1
O = np.array([70,30])
p = np.array([2/3,1/3])
E = n *p

chi2_cal , p_val  =stats.chisquare(f_obs = 0 , f_exp=E)


```

# ทดสอบการแจกแจง ปกติหรือไม่

```
เปลี่ยน เป็น Z จาก Z = (X - x_bar) / s

O  = np.array([1,2,3,4])
x_l = np.array([1,2,3,4])
x_r = np.array([2,3,4,5])
x = (x_l+x_r)/2

x_bar = sum(O*x)/sum(O)
s= np.sqrt(sum(O*x - x_bar)**2 /(n-1))
z_l = (x_l-x_bar) / s
z_r= (x_r-x_bar) / s
pz = stats.norm.cdf(z_r) - stats.norm.cdf(z_l)
E = n*pz
E_adj = np.append(E[0:-2],E[-1]+E[-2])
O_adj = np.append(O[0:-2],O[-1]+O[-2])

chi2_cal , p_val = stats.chisquare(f_obs = O_adj, 
                                    f_exp =E_adj,
                                    ddof = 2) 
# ddof = 2 =default

```

#  ทดสอบความเป็นอิสระ

```
O =  np.array([[1,2,3,4,5],[2,3,4,5,6]])

chi2_cal  , p_val ,dof ,E = stats.chi2_contingency (O , correction  = False)


```


# ขนาดความสัมพันธ์
```
V = np.sqrt(X**2/(N*min(r-1,c-1)))
```

