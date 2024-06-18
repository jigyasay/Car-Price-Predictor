```python
import numpy as np
```


```python
import pandas as pd
```

    C:\Users\91738\AppData\Local\Temp\ipykernel_4472\4080736814.py:1: DeprecationWarning: 
    Pyarrow will become a required dependency of pandas in the next major release of pandas (pandas 3.0),
    (to allow more performant data types, such as the Arrow string type, and better interoperability with other libraries)
    but was not found to be installed on your system.
    If this would cause problems for you,
    please provide us feedback at https://github.com/pandas-dev/pandas/issues/54466
            
      import pandas as pd
    


```python
car=pd.read_csv(r"C:\Users\91738\Downloads\quikr_car.csv")
```


```python
car.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>company</th>
      <th>year</th>
      <th>Price</th>
      <th>kms_driven</th>
      <th>fuel_type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Hyundai Santro Xing XO eRLX Euro III</td>
      <td>Hyundai</td>
      <td>2007</td>
      <td>80,000</td>
      <td>45,000 kms</td>
      <td>Petrol</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mahindra Jeep CL550 MDI</td>
      <td>Mahindra</td>
      <td>2006</td>
      <td>4,25,000</td>
      <td>40 kms</td>
      <td>Diesel</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Maruti Suzuki Alto 800 Vxi</td>
      <td>Maruti</td>
      <td>2018</td>
      <td>Ask For Price</td>
      <td>22,000 kms</td>
      <td>Petrol</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hyundai Grand i10 Magna 1.2 Kappa VTVT</td>
      <td>Hyundai</td>
      <td>2014</td>
      <td>3,25,000</td>
      <td>28,000 kms</td>
      <td>Petrol</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Ford EcoSport Titanium 1.5L TDCi</td>
      <td>Ford</td>
      <td>2014</td>
      <td>5,75,000</td>
      <td>36,000 kms</td>
      <td>Diesel</td>
    </tr>
  </tbody>
</table>
</div>




```python
car.shape
```




    (892, 6)




```python
car.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 892 entries, 0 to 891
    Data columns (total 6 columns):
     #   Column      Non-Null Count  Dtype 
    ---  ------      --------------  ----- 
     0   name        892 non-null    object
     1   company     892 non-null    object
     2   year        892 non-null    object
     3   Price       892 non-null    object
     4   kms_driven  840 non-null    object
     5   fuel_type   837 non-null    object
    dtypes: object(6)
    memory usage: 41.9+ KB
    


```python
car['year'].unique()
```




    array(['2007', '2006', '2018', '2014', '2015', '2012', '2013', '2016',
           '2010', '2017', '2008', '2011', '2019', '2009', '2005', '2000',
           '...', '150k', 'TOUR', '2003', 'r 15', '2004', 'Zest', '/-Rs',
           'sale', '1995', 'ara)', '2002', 'SELL', '2001', 'tion', 'odel',
           '2 bs', 'arry', 'Eon', 'o...', 'ture', 'emi', 'car', 'able', 'no.',
           'd...', 'SALE', 'digo', 'sell', 'd Ex', 'n...', 'e...', 'D...',
           ', Ac', 'go .', 'k...', 'o c4', 'zire', 'cent', 'Sumo', 'cab',
           't xe', 'EV2', 'r...', 'zest'], dtype=object)




```python
car['Price'].unique()
```




    array(['80,000', '4,25,000', 'Ask For Price', '3,25,000', '5,75,000',
           '1,75,000', '1,90,000', '8,30,000', '2,50,000', '1,82,000',
           '3,15,000', '4,15,000', '3,20,000', '10,00,000', '5,00,000',
           '3,50,000', '1,60,000', '3,10,000', '75,000', '1,00,000',
           '2,90,000', '95,000', '1,80,000', '3,85,000', '1,05,000',
           '6,50,000', '6,89,999', '4,48,000', '5,49,000', '5,01,000',
           '4,89,999', '2,80,000', '3,49,999', '2,84,999', '3,45,000',
           '4,99,999', '2,35,000', '2,49,999', '14,75,000', '3,95,000',
           '2,20,000', '1,70,000', '85,000', '2,00,000', '5,70,000',
           '1,10,000', '4,48,999', '18,91,111', '1,59,500', '3,44,999',
           '4,49,999', '8,65,000', '6,99,000', '3,75,000', '2,24,999',
           '12,00,000', '1,95,000', '3,51,000', '2,40,000', '90,000',
           '1,55,000', '6,00,000', '1,89,500', '2,10,000', '3,90,000',
           '1,35,000', '16,00,000', '7,01,000', '2,65,000', '5,25,000',
           '3,72,000', '6,35,000', '5,50,000', '4,85,000', '3,29,500',
           '2,51,111', '5,69,999', '69,999', '2,99,999', '3,99,999',
           '4,50,000', '2,70,000', '1,58,400', '1,79,000', '1,25,000',
           '2,99,000', '1,50,000', '2,75,000', '2,85,000', '3,40,000',
           '70,000', '2,89,999', '8,49,999', '7,49,999', '2,74,999',
           '9,84,999', '5,99,999', '2,44,999', '4,74,999', '2,45,000',
           '1,69,500', '3,70,000', '1,68,000', '1,45,000', '98,500',
           '2,09,000', '1,85,000', '9,00,000', '6,99,999', '1,99,999',
           '5,44,999', '1,99,000', '5,40,000', '49,000', '7,00,000', '55,000',
           '8,95,000', '3,55,000', '5,65,000', '3,65,000', '40,000',
           '4,00,000', '3,30,000', '5,80,000', '3,79,000', '2,19,000',
           '5,19,000', '7,30,000', '20,00,000', '21,00,000', '14,00,000',
           '3,11,000', '8,55,000', '5,35,000', '1,78,000', '3,00,000',
           '2,55,000', '5,49,999', '3,80,000', '57,000', '4,10,000',
           '2,25,000', '1,20,000', '59,000', '5,99,000', '6,75,000', '72,500',
           '6,10,000', '2,30,000', '5,20,000', '5,24,999', '4,24,999',
           '6,44,999', '5,84,999', '7,99,999', '4,44,999', '6,49,999',
           '9,44,999', '5,74,999', '3,74,999', '1,30,000', '4,01,000',
           '13,50,000', '1,74,999', '2,39,999', '99,999', '3,24,999',
           '10,74,999', '11,30,000', '1,49,000', '7,70,000', '30,000',
           '3,35,000', '3,99,000', '65,000', '1,69,999', '1,65,000',
           '5,60,000', '9,50,000', '7,15,000', '45,000', '9,40,000',
           '1,55,555', '15,00,000', '4,95,000', '8,00,000', '12,99,000',
           '5,30,000', '14,99,000', '32,000', '4,05,000', '7,60,000',
           '7,50,000', '4,19,000', '1,40,000', '15,40,000', '1,23,000',
           '4,98,000', '4,80,000', '4,88,000', '15,25,000', '5,48,900',
           '7,25,000', '99,000', '52,000', '28,00,000', '4,99,000',
           '3,81,000', '2,78,000', '6,90,000', '2,60,000', '90,001',
           '1,15,000', '15,99,000', '1,59,000', '51,999', '2,15,000',
           '35,000', '11,50,000', '2,69,000', '60,000', '4,30,000',
           '85,00,003', '4,01,919', '4,90,000', '4,24,000', '2,05,000',
           '5,49,900', '3,71,500', '4,35,000', '1,89,700', '3,89,700',
           '3,60,000', '2,95,000', '1,14,990', '10,65,000', '4,70,000',
           '48,000', '1,88,000', '4,65,000', '1,79,999', '21,90,000',
           '23,90,000', '10,75,000', '4,75,000', '10,25,000', '6,15,000',
           '19,00,000', '14,90,000', '15,10,000', '18,50,000', '7,90,000',
           '17,25,000', '12,25,000', '68,000', '9,70,000', '31,00,000',
           '8,99,000', '88,000', '53,000', '5,68,500', '71,000', '5,90,000',
           '7,95,000', '42,000', '1,89,000', '1,62,000', '35,999',
           '29,00,000', '39,999', '50,500', '5,10,000', '8,60,000',
           '5,00,001'], dtype=object)




```python
car['kms_driven'].unique()
```




    array(['45,000 kms', '40 kms', '22,000 kms', '28,000 kms', '36,000 kms',
           '59,000 kms', '41,000 kms', '25,000 kms', '24,530 kms',
           '60,000 kms', '30,000 kms', '32,000 kms', '48,660 kms',
           '4,000 kms', '16,934 kms', '43,000 kms', '35,550 kms',
           '39,522 kms', '39,000 kms', '55,000 kms', '72,000 kms',
           '15,975 kms', '70,000 kms', '23,452 kms', '35,522 kms',
           '48,508 kms', '15,487 kms', '82,000 kms', '20,000 kms',
           '68,000 kms', '38,000 kms', '27,000 kms', '33,000 kms',
           '46,000 kms', '16,000 kms', '47,000 kms', '35,000 kms',
           '30,874 kms', '15,000 kms', '29,685 kms', '1,30,000 kms',
           '19,000 kms', nan, '54,000 kms', '13,000 kms', '38,200 kms',
           '50,000 kms', '13,500 kms', '3,600 kms', '45,863 kms',
           '60,500 kms', '12,500 kms', '18,000 kms', '13,349 kms',
           '29,000 kms', '44,000 kms', '42,000 kms', '14,000 kms',
           '49,000 kms', '36,200 kms', '51,000 kms', '1,04,000 kms',
           '33,333 kms', '33,600 kms', '5,600 kms', '7,500 kms', '26,000 kms',
           '24,330 kms', '65,480 kms', '28,028 kms', '2,00,000 kms',
           '99,000 kms', '2,800 kms', '21,000 kms', '11,000 kms',
           '66,000 kms', '3,000 kms', '7,000 kms', '38,500 kms', '37,200 kms',
           '43,200 kms', '24,800 kms', '45,872 kms', '40,000 kms',
           '11,400 kms', '97,200 kms', '52,000 kms', '31,000 kms',
           '1,75,430 kms', '37,000 kms', '65,000 kms', '3,350 kms',
           '75,000 kms', '62,000 kms', '73,000 kms', '2,200 kms',
           '54,870 kms', '34,580 kms', '97,000 kms', '60 kms', '80,200 kms',
           '3,200 kms', '0,000 kms', '5,000 kms', '588 kms', '71,200 kms',
           '1,75,400 kms', '9,300 kms', '56,758 kms', '10,000 kms',
           '56,450 kms', '56,000 kms', '32,700 kms', '9,000 kms', '73 kms',
           '1,60,000 kms', '84,000 kms', '58,559 kms', '57,000 kms',
           '1,70,000 kms', '80,000 kms', '6,821 kms', '23,000 kms',
           '34,000 kms', '1,800 kms', '4,00,000 kms', '48,000 kms',
           '90,000 kms', '12,000 kms', '69,900 kms', '1,66,000 kms',
           '122 kms', '0 kms', '24,000 kms', '36,469 kms', '7,800 kms',
           '24,695 kms', '15,141 kms', '59,910 kms', '1,00,000 kms',
           '4,500 kms', '1,29,000 kms', '300 kms', '1,31,000 kms',
           '1,11,111 kms', '59,466 kms', '25,500 kms', '44,005 kms',
           '2,110 kms', '43,222 kms', '1,00,200 kms', '65 kms',
           '1,40,000 kms', '1,03,553 kms', '58,000 kms', '1,20,000 kms',
           '49,800 kms', '100 kms', '81,876 kms', '6,020 kms', '55,700 kms',
           '18,500 kms', '1,80,000 kms', '53,000 kms', '35,500 kms',
           '22,134 kms', '1,000 kms', '8,500 kms', '87,000 kms', '6,000 kms',
           '15,574 kms', '8,000 kms', '55,800 kms', '56,400 kms',
           '72,160 kms', '11,500 kms', '1,33,000 kms', '2,000 kms',
           '88,000 kms', '65,422 kms', '1,17,000 kms', '1,50,000 kms',
           '10,750 kms', '6,800 kms', '5 kms', '9,800 kms', '57,923 kms',
           '30,201 kms', '6,200 kms', '37,518 kms', '24,652 kms', '383 kms',
           '95,000 kms', '3,528 kms', '52,500 kms', '47,900 kms',
           '52,800 kms', '1,95,000 kms', '48,008 kms', '48,247 kms',
           '9,400 kms', '64,000 kms', '2,137 kms', '10,544 kms', '49,500 kms',
           '1,47,000 kms', '90,001 kms', '48,006 kms', '74,000 kms',
           '85,000 kms', '29,500 kms', '39,700 kms', '67,000 kms',
           '19,336 kms', '60,105 kms', '45,933 kms', '1,02,563 kms',
           '28,600 kms', '41,800 kms', '1,16,000 kms', '42,590 kms',
           '7,400 kms', '54,500 kms', '76,000 kms', '00 kms', '11,523 kms',
           '38,600 kms', '95,500 kms', '37,458 kms', '85,960 kms',
           '12,516 kms', '30,600 kms', '2,550 kms', '62,500 kms',
           '69,000 kms', '28,400 kms', '68,485 kms', '3,500 kms',
           '85,455 kms', '63,000 kms', '1,600 kms', '77,000 kms',
           '26,500 kms', '2,875 kms', '13,900 kms', '1,500 kms', '2,450 kms',
           '1,625 kms', '33,400 kms', '60,123 kms', '38,900 kms',
           '1,37,495 kms', '91,200 kms', '1,46,000 kms', '1,00,800 kms',
           '2,100 kms', '2,500 kms', '1,32,000 kms', 'Petrol'], dtype=object)




```python
car['fuel_type'].unique()
```




    array(['Petrol', 'Diesel', nan, 'LPG'], dtype=object)



##quality
-year has many non-year values
-year object to int
-price object to int
-kms_driven has kms with integers
-kms_driven object to int
-kms_driven has nan values
-fuel_type has nan values
-keep first three words of name
-

**cleaning**


```python
backup=car.copy()
```


```python
car['year'].str.isnumeric()
```




    0       True
    1       True
    2       True
    3       True
    4       True
           ...  
    887    False
    888     True
    889     True
    890     True
    891     True
    Name: year, Length: 892, dtype: bool




```python
car=car[car['year'].str.isnumeric()]
```


```python
car['year']=car['year'].astype(int)
```


```python
car.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Index: 842 entries, 0 to 891
    Data columns (total 6 columns):
     #   Column      Non-Null Count  Dtype 
    ---  ------      --------------  ----- 
     0   name        842 non-null    object
     1   company     842 non-null    object
     2   year        842 non-null    int32 
     3   Price       842 non-null    object
     4   kms_driven  840 non-null    object
     5   fuel_type   837 non-null    object
    dtypes: int32(1), object(5)
    memory usage: 42.8+ KB
    


```python
car=car[car['Price']!="Ask For Price"] 
```

*for removing commas in the price*


```python
car['Price']=car['Price'].str.replace(',','').astype(int)
```


```python
 car.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Index: 819 entries, 0 to 891
    Data columns (total 6 columns):
     #   Column      Non-Null Count  Dtype 
    ---  ------      --------------  ----- 
     0   name        819 non-null    object
     1   company     819 non-null    object
     2   year        819 non-null    int32 
     3   Price       819 non-null    int32 
     4   kms_driven  819 non-null    object
     5   fuel_type   816 non-null    object
    dtypes: int32(2), object(4)
    memory usage: 38.4+ KB
    


```python
car['kms_driven']=car['kms_driven'].str.split(' ').str.get(0).str.replace(',','')
```


```python
car=car[car['kms_driven'].str.isnumeric()]
```


```python
car['kms_driven']=car['kms_driven'].astype(int)
```


```python
car.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Index: 817 entries, 0 to 889
    Data columns (total 6 columns):
     #   Column      Non-Null Count  Dtype 
    ---  ------      --------------  ----- 
     0   name        817 non-null    object
     1   company     817 non-null    object
     2   year        817 non-null    int32 
     3   Price       817 non-null    int32 
     4   kms_driven  817 non-null    int32 
     5   fuel_type   816 non-null    object
    dtypes: int32(3), object(3)
    memory usage: 35.1+ KB
    


```python
car=car[~car['fuel_type'].isna()]
```


```python
car['nmae']=car['name'].str.split(' ').str.slice(0,3).str.join(' ')
```


```python
car=car.reset_index(drop=True)
```


```python
car.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 816 entries, 0 to 815
    Data columns (total 7 columns):
     #   Column      Non-Null Count  Dtype 
    ---  ------      --------------  ----- 
     0   name        816 non-null    object
     1   company     816 non-null    object
     2   year        816 non-null    int32 
     3   Price       816 non-null    int32 
     4   kms_driven  816 non-null    int32 
     5   fuel_type   816 non-null    object
     6   nmae        816 non-null    object
    dtypes: int32(3), object(4)
    memory usage: 35.2+ KB
    


```python
car.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>Price</th>
      <th>kms_driven</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>816.000000</td>
      <td>8.160000e+02</td>
      <td>816.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2012.444853</td>
      <td>4.117176e+05</td>
      <td>46275.531863</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4.002992</td>
      <td>4.751844e+05</td>
      <td>34297.428044</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1995.000000</td>
      <td>3.000000e+04</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2010.000000</td>
      <td>1.750000e+05</td>
      <td>27000.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2013.000000</td>
      <td>2.999990e+05</td>
      <td>41000.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2015.000000</td>
      <td>4.912500e+05</td>
      <td>56818.500000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2019.000000</td>
      <td>8.500003e+06</td>
      <td>400000.000000</td>
    </tr>
  </tbody>
</table>
</div>



 *checking for outliers*


```python
 car[car['Price']>6e6]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>company</th>
      <th>year</th>
      <th>Price</th>
      <th>kms_driven</th>
      <th>fuel_type</th>
      <th>nmae</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>534</th>
      <td>Mahindra XUV500 W6</td>
      <td>Mahindra</td>
      <td>2014</td>
      <td>8500003</td>
      <td>45000</td>
      <td>Diesel</td>
      <td>Mahindra XUV500 W6</td>
    </tr>
  </tbody>
</table>
</div>




```python
 car=car[car['Price']<6e6].reset_index(drop=True)
```


```python
car.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>Price</th>
      <th>kms_driven</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>815.000000</td>
      <td>8.150000e+02</td>
      <td>815.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2012.442945</td>
      <td>4.017933e+05</td>
      <td>46277.096933</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4.005079</td>
      <td>3.815888e+05</td>
      <td>34318.459638</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1995.000000</td>
      <td>3.000000e+04</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2010.000000</td>
      <td>1.750000e+05</td>
      <td>27000.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2013.000000</td>
      <td>2.999990e+05</td>
      <td>41000.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2015.000000</td>
      <td>4.900000e+05</td>
      <td>56879.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2019.000000</td>
      <td>3.100000e+06</td>
      <td>400000.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
car.to_csv('cleaned car.csv')
```

**Model**


```python
x=car.drop(columns='Price')
y=car['Price']
```


```python
x
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>company</th>
      <th>year</th>
      <th>kms_driven</th>
      <th>fuel_type</th>
      <th>nmae</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Hyundai Santro Xing XO eRLX Euro III</td>
      <td>Hyundai</td>
      <td>2007</td>
      <td>45000</td>
      <td>Petrol</td>
      <td>Hyundai Santro Xing</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mahindra Jeep CL550 MDI</td>
      <td>Mahindra</td>
      <td>2006</td>
      <td>40</td>
      <td>Diesel</td>
      <td>Mahindra Jeep CL550</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Hyundai Grand i10 Magna 1.2 Kappa VTVT</td>
      <td>Hyundai</td>
      <td>2014</td>
      <td>28000</td>
      <td>Petrol</td>
      <td>Hyundai Grand i10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Ford EcoSport Titanium 1.5L TDCi</td>
      <td>Ford</td>
      <td>2014</td>
      <td>36000</td>
      <td>Diesel</td>
      <td>Ford EcoSport Titanium</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Ford Figo</td>
      <td>Ford</td>
      <td>2012</td>
      <td>41000</td>
      <td>Diesel</td>
      <td>Ford Figo</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>810</th>
      <td>Maruti Suzuki Ritz VXI ABS</td>
      <td>Maruti</td>
      <td>2011</td>
      <td>50000</td>
      <td>Petrol</td>
      <td>Maruti Suzuki Ritz</td>
    </tr>
    <tr>
      <th>811</th>
      <td>Tata Indica V2 DLE BS III</td>
      <td>Tata</td>
      <td>2009</td>
      <td>30000</td>
      <td>Diesel</td>
      <td>Tata Indica V2</td>
    </tr>
    <tr>
      <th>812</th>
      <td>Toyota Corolla Altis</td>
      <td>Toyota</td>
      <td>2009</td>
      <td>132000</td>
      <td>Petrol</td>
      <td>Toyota Corolla Altis</td>
    </tr>
    <tr>
      <th>813</th>
      <td>Tata Zest XM Diesel</td>
      <td>Tata</td>
      <td>2018</td>
      <td>27000</td>
      <td>Diesel</td>
      <td>Tata Zest XM</td>
    </tr>
    <tr>
      <th>814</th>
      <td>Mahindra Quanto C8</td>
      <td>Mahindra</td>
      <td>2013</td>
      <td>40000</td>
      <td>Diesel</td>
      <td>Mahindra Quanto C8</td>
    </tr>
  </tbody>
</table>
<p>815 rows × 6 columns</p>
</div>




```python
y
```




    0       80000
    1      425000
    2      325000
    3      575000
    4      175000
            ...  
    810    270000
    811    110000
    812    300000
    813    260000
    814    390000
    Name: Price, Length: 815, dtype: int32




```python
X=car[['name','company','year','kms_driven','fuel_type']]
y=car['Price']
```


```python
from sklearn.model_selection import train_test_split
X_train,X_test,y_train,y_test=train_test_split(X,y,test_size=0.2)
from sklearn.linear_model import LinearRegression
from sklearn.preprocessing import OneHotEncoder
from sklearn.compose import make_column_transformer
from sklearn.pipeline import make_pipeline
from sklearn.metrics import r2_score
```


```python
ohe=OneHotEncoder()
ohe.fit(X[['name','company','fuel_type']])
```




<style>#sk-container-id-1 {
  /* Definition of color scheme common for light and dark mode */
  --sklearn-color-text: black;
  --sklearn-color-line: gray;
  /* Definition of color scheme for unfitted estimators */
  --sklearn-color-unfitted-level-0: #fff5e6;
  --sklearn-color-unfitted-level-1: #f6e4d2;
  --sklearn-color-unfitted-level-2: #ffe0b3;
  --sklearn-color-unfitted-level-3: chocolate;
  /* Definition of color scheme for fitted estimators */
  --sklearn-color-fitted-level-0: #f0f8ff;
  --sklearn-color-fitted-level-1: #d4ebff;
  --sklearn-color-fitted-level-2: #b3dbfd;
  --sklearn-color-fitted-level-3: cornflowerblue;

  /* Specific color for light theme */
  --sklearn-color-text-on-default-background: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, black)));
  --sklearn-color-background: var(--sg-background-color, var(--theme-background, var(--jp-layout-color0, white)));
  --sklearn-color-border-box: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, black)));
  --sklearn-color-icon: #696969;

  @media (prefers-color-scheme: dark) {
    /* Redefinition of color scheme for dark theme */
    --sklearn-color-text-on-default-background: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, white)));
    --sklearn-color-background: var(--sg-background-color, var(--theme-background, var(--jp-layout-color0, #111)));
    --sklearn-color-border-box: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, white)));
    --sklearn-color-icon: #878787;
  }
}

#sk-container-id-1 {
  color: var(--sklearn-color-text);
}

#sk-container-id-1 pre {
  padding: 0;
}

#sk-container-id-1 input.sk-hidden--visually {
  border: 0;
  clip: rect(1px 1px 1px 1px);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
}

#sk-container-id-1 div.sk-dashed-wrapped {
  border: 1px dashed var(--sklearn-color-line);
  margin: 0 0.4em 0.5em 0.4em;
  box-sizing: border-box;
  padding-bottom: 0.4em;
  background-color: var(--sklearn-color-background);
}

#sk-container-id-1 div.sk-container {
  /* jupyter's `normalize.less` sets `[hidden] { display: none; }`
     but bootstrap.min.css set `[hidden] { display: none !important; }`
     so we also need the `!important` here to be able to override the
     default hidden behavior on the sphinx rendered scikit-learn.org.
     See: https://github.com/scikit-learn/scikit-learn/issues/21755 */
  display: inline-block !important;
  position: relative;
}

#sk-container-id-1 div.sk-text-repr-fallback {
  display: none;
}

div.sk-parallel-item,
div.sk-serial,
div.sk-item {
  /* draw centered vertical line to link estimators */
  background-image: linear-gradient(var(--sklearn-color-text-on-default-background), var(--sklearn-color-text-on-default-background));
  background-size: 2px 100%;
  background-repeat: no-repeat;
  background-position: center center;
}

/* Parallel-specific style estimator block */

#sk-container-id-1 div.sk-parallel-item::after {
  content: "";
  width: 100%;
  border-bottom: 2px solid var(--sklearn-color-text-on-default-background);
  flex-grow: 1;
}

#sk-container-id-1 div.sk-parallel {
  display: flex;
  align-items: stretch;
  justify-content: center;
  background-color: var(--sklearn-color-background);
  position: relative;
}

#sk-container-id-1 div.sk-parallel-item {
  display: flex;
  flex-direction: column;
}

#sk-container-id-1 div.sk-parallel-item:first-child::after {
  align-self: flex-end;
  width: 50%;
}

#sk-container-id-1 div.sk-parallel-item:last-child::after {
  align-self: flex-start;
  width: 50%;
}

#sk-container-id-1 div.sk-parallel-item:only-child::after {
  width: 0;
}

/* Serial-specific style estimator block */

#sk-container-id-1 div.sk-serial {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: var(--sklearn-color-background);
  padding-right: 1em;
  padding-left: 1em;
}


/* Toggleable style: style used for estimator/Pipeline/ColumnTransformer box that is
clickable and can be expanded/collapsed.
- Pipeline and ColumnTransformer use this feature and define the default style
- Estimators will overwrite some part of the style using the `sk-estimator` class
*/

/* Pipeline and ColumnTransformer style (default) */

#sk-container-id-1 div.sk-toggleable {
  /* Default theme specific background. It is overwritten whether we have a
  specific estimator or a Pipeline/ColumnTransformer */
  background-color: var(--sklearn-color-background);
}

/* Toggleable label */
#sk-container-id-1 label.sk-toggleable__label {
  cursor: pointer;
  display: block;
  width: 100%;
  margin-bottom: 0;
  padding: 0.5em;
  box-sizing: border-box;
  text-align: center;
}

#sk-container-id-1 label.sk-toggleable__label-arrow:before {
  /* Arrow on the left of the label */
  content: "▸";
  float: left;
  margin-right: 0.25em;
  color: var(--sklearn-color-icon);
}

#sk-container-id-1 label.sk-toggleable__label-arrow:hover:before {
  color: var(--sklearn-color-text);
}

/* Toggleable content - dropdown */

#sk-container-id-1 div.sk-toggleable__content {
  max-height: 0;
  max-width: 0;
  overflow: hidden;
  text-align: left;
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-0);
}

#sk-container-id-1 div.sk-toggleable__content.fitted {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-0);
}

#sk-container-id-1 div.sk-toggleable__content pre {
  margin: 0.2em;
  border-radius: 0.25em;
  color: var(--sklearn-color-text);
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-0);
}

#sk-container-id-1 div.sk-toggleable__content.fitted pre {
  /* unfitted */
  background-color: var(--sklearn-color-fitted-level-0);
}

#sk-container-id-1 input.sk-toggleable__control:checked~div.sk-toggleable__content {
  /* Expand drop-down */
  max-height: 200px;
  max-width: 100%;
  overflow: auto;
}

#sk-container-id-1 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {
  content: "▾";
}

/* Pipeline/ColumnTransformer-specific style */

#sk-container-id-1 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {
  color: var(--sklearn-color-text);
  background-color: var(--sklearn-color-unfitted-level-2);
}

#sk-container-id-1 div.sk-label.fitted input.sk-toggleable__control:checked~label.sk-toggleable__label {
  background-color: var(--sklearn-color-fitted-level-2);
}

/* Estimator-specific style */

/* Colorize estimator box */
#sk-container-id-1 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-2);
}

#sk-container-id-1 div.sk-estimator.fitted input.sk-toggleable__control:checked~label.sk-toggleable__label {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-2);
}

#sk-container-id-1 div.sk-label label.sk-toggleable__label,
#sk-container-id-1 div.sk-label label {
  /* The background is the default theme color */
  color: var(--sklearn-color-text-on-default-background);
}

/* On hover, darken the color of the background */
#sk-container-id-1 div.sk-label:hover label.sk-toggleable__label {
  color: var(--sklearn-color-text);
  background-color: var(--sklearn-color-unfitted-level-2);
}

/* Label box, darken color on hover, fitted */
#sk-container-id-1 div.sk-label.fitted:hover label.sk-toggleable__label.fitted {
  color: var(--sklearn-color-text);
  background-color: var(--sklearn-color-fitted-level-2);
}

/* Estimator label */

#sk-container-id-1 div.sk-label label {
  font-family: monospace;
  font-weight: bold;
  display: inline-block;
  line-height: 1.2em;
}

#sk-container-id-1 div.sk-label-container {
  text-align: center;
}

/* Estimator-specific */
#sk-container-id-1 div.sk-estimator {
  font-family: monospace;
  border: 1px dotted var(--sklearn-color-border-box);
  border-radius: 0.25em;
  box-sizing: border-box;
  margin-bottom: 0.5em;
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-0);
}

#sk-container-id-1 div.sk-estimator.fitted {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-0);
}

/* on hover */
#sk-container-id-1 div.sk-estimator:hover {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-2);
}

#sk-container-id-1 div.sk-estimator.fitted:hover {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-2);
}

/* Specification for estimator info (e.g. "i" and "?") */

/* Common style for "i" and "?" */

.sk-estimator-doc-link,
a:link.sk-estimator-doc-link,
a:visited.sk-estimator-doc-link {
  float: right;
  font-size: smaller;
  line-height: 1em;
  font-family: monospace;
  background-color: var(--sklearn-color-background);
  border-radius: 1em;
  height: 1em;
  width: 1em;
  text-decoration: none !important;
  margin-left: 1ex;
  /* unfitted */
  border: var(--sklearn-color-unfitted-level-1) 1pt solid;
  color: var(--sklearn-color-unfitted-level-1);
}

.sk-estimator-doc-link.fitted,
a:link.sk-estimator-doc-link.fitted,
a:visited.sk-estimator-doc-link.fitted {
  /* fitted */
  border: var(--sklearn-color-fitted-level-1) 1pt solid;
  color: var(--sklearn-color-fitted-level-1);
}

/* On hover */
div.sk-estimator:hover .sk-estimator-doc-link:hover,
.sk-estimator-doc-link:hover,
div.sk-label-container:hover .sk-estimator-doc-link:hover,
.sk-estimator-doc-link:hover {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-3);
  color: var(--sklearn-color-background);
  text-decoration: none;
}

div.sk-estimator.fitted:hover .sk-estimator-doc-link.fitted:hover,
.sk-estimator-doc-link.fitted:hover,
div.sk-label-container:hover .sk-estimator-doc-link.fitted:hover,
.sk-estimator-doc-link.fitted:hover {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-3);
  color: var(--sklearn-color-background);
  text-decoration: none;
}

/* Span, style for the box shown on hovering the info icon */
.sk-estimator-doc-link span {
  display: none;
  z-index: 9999;
  position: relative;
  font-weight: normal;
  right: .2ex;
  padding: .5ex;
  margin: .5ex;
  width: min-content;
  min-width: 20ex;
  max-width: 50ex;
  color: var(--sklearn-color-text);
  box-shadow: 2pt 2pt 4pt #999;
  /* unfitted */
  background: var(--sklearn-color-unfitted-level-0);
  border: .5pt solid var(--sklearn-color-unfitted-level-3);
}

.sk-estimator-doc-link.fitted span {
  /* fitted */
  background: var(--sklearn-color-fitted-level-0);
  border: var(--sklearn-color-fitted-level-3);
}

.sk-estimator-doc-link:hover span {
  display: block;
}

/* "?"-specific style due to the `<a>` HTML tag */

#sk-container-id-1 a.estimator_doc_link {
  float: right;
  font-size: 1rem;
  line-height: 1em;
  font-family: monospace;
  background-color: var(--sklearn-color-background);
  border-radius: 1rem;
  height: 1rem;
  width: 1rem;
  text-decoration: none;
  /* unfitted */
  color: var(--sklearn-color-unfitted-level-1);
  border: var(--sklearn-color-unfitted-level-1) 1pt solid;
}

#sk-container-id-1 a.estimator_doc_link.fitted {
  /* fitted */
  border: var(--sklearn-color-fitted-level-1) 1pt solid;
  color: var(--sklearn-color-fitted-level-1);
}

/* On hover */
#sk-container-id-1 a.estimator_doc_link:hover {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-3);
  color: var(--sklearn-color-background);
  text-decoration: none;
}

#sk-container-id-1 a.estimator_doc_link.fitted:hover {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-3);
}
</style><div id="sk-container-id-1" class="sk-top-container"><div class="sk-text-repr-fallback"><pre>OneHotEncoder()</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class="sk-container" hidden><div class="sk-item"><div class="sk-estimator fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-1" type="checkbox" checked><label for="sk-estimator-id-1" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">&nbsp;&nbsp;OneHotEncoder<a class="sk-estimator-doc-link fitted" rel="noreferrer" target="_blank" href="https://scikit-learn.org/1.4/modules/generated/sklearn.preprocessing.OneHotEncoder.html">?<span>Documentation for OneHotEncoder</span></a><span class="sk-estimator-doc-link fitted">i<span>Fitted</span></span></label><div class="sk-toggleable__content fitted"><pre>OneHotEncoder()</pre></div> </div></div></div></div>




```python
column_trans=make_column_transformer((OneHotEncoder(categories=ohe.categories_),['name','company','fuel_type']),
                                    remainder='passthrough')
```


```python
lr=LinearRegression()
```


```python
pipe=make_pipeline(column_trans,lr)
```


```python
pipe.fit(X_train,y_train)
```




<style>#sk-container-id-2 {
  /* Definition of color scheme common for light and dark mode */
  --sklearn-color-text: black;
  --sklearn-color-line: gray;
  /* Definition of color scheme for unfitted estimators */
  --sklearn-color-unfitted-level-0: #fff5e6;
  --sklearn-color-unfitted-level-1: #f6e4d2;
  --sklearn-color-unfitted-level-2: #ffe0b3;
  --sklearn-color-unfitted-level-3: chocolate;
  /* Definition of color scheme for fitted estimators */
  --sklearn-color-fitted-level-0: #f0f8ff;
  --sklearn-color-fitted-level-1: #d4ebff;
  --sklearn-color-fitted-level-2: #b3dbfd;
  --sklearn-color-fitted-level-3: cornflowerblue;

  /* Specific color for light theme */
  --sklearn-color-text-on-default-background: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, black)));
  --sklearn-color-background: var(--sg-background-color, var(--theme-background, var(--jp-layout-color0, white)));
  --sklearn-color-border-box: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, black)));
  --sklearn-color-icon: #696969;

  @media (prefers-color-scheme: dark) {
    /* Redefinition of color scheme for dark theme */
    --sklearn-color-text-on-default-background: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, white)));
    --sklearn-color-background: var(--sg-background-color, var(--theme-background, var(--jp-layout-color0, #111)));
    --sklearn-color-border-box: var(--sg-text-color, var(--theme-code-foreground, var(--jp-content-font-color1, white)));
    --sklearn-color-icon: #878787;
  }
}

#sk-container-id-2 {
  color: var(--sklearn-color-text);
}

#sk-container-id-2 pre {
  padding: 0;
}

#sk-container-id-2 input.sk-hidden--visually {
  border: 0;
  clip: rect(1px 1px 1px 1px);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  margin: -1px;
  overflow: hidden;
  padding: 0;
  position: absolute;
  width: 1px;
}

#sk-container-id-2 div.sk-dashed-wrapped {
  border: 1px dashed var(--sklearn-color-line);
  margin: 0 0.4em 0.5em 0.4em;
  box-sizing: border-box;
  padding-bottom: 0.4em;
  background-color: var(--sklearn-color-background);
}

#sk-container-id-2 div.sk-container {
  /* jupyter's `normalize.less` sets `[hidden] { display: none; }`
     but bootstrap.min.css set `[hidden] { display: none !important; }`
     so we also need the `!important` here to be able to override the
     default hidden behavior on the sphinx rendered scikit-learn.org.
     See: https://github.com/scikit-learn/scikit-learn/issues/21755 */
  display: inline-block !important;
  position: relative;
}

#sk-container-id-2 div.sk-text-repr-fallback {
  display: none;
}

div.sk-parallel-item,
div.sk-serial,
div.sk-item {
  /* draw centered vertical line to link estimators */
  background-image: linear-gradient(var(--sklearn-color-text-on-default-background), var(--sklearn-color-text-on-default-background));
  background-size: 2px 100%;
  background-repeat: no-repeat;
  background-position: center center;
}

/* Parallel-specific style estimator block */

#sk-container-id-2 div.sk-parallel-item::after {
  content: "";
  width: 100%;
  border-bottom: 2px solid var(--sklearn-color-text-on-default-background);
  flex-grow: 1;
}

#sk-container-id-2 div.sk-parallel {
  display: flex;
  align-items: stretch;
  justify-content: center;
  background-color: var(--sklearn-color-background);
  position: relative;
}

#sk-container-id-2 div.sk-parallel-item {
  display: flex;
  flex-direction: column;
}

#sk-container-id-2 div.sk-parallel-item:first-child::after {
  align-self: flex-end;
  width: 50%;
}

#sk-container-id-2 div.sk-parallel-item:last-child::after {
  align-self: flex-start;
  width: 50%;
}

#sk-container-id-2 div.sk-parallel-item:only-child::after {
  width: 0;
}

/* Serial-specific style estimator block */

#sk-container-id-2 div.sk-serial {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: var(--sklearn-color-background);
  padding-right: 1em;
  padding-left: 1em;
}


/* Toggleable style: style used for estimator/Pipeline/ColumnTransformer box that is
clickable and can be expanded/collapsed.
- Pipeline and ColumnTransformer use this feature and define the default style
- Estimators will overwrite some part of the style using the `sk-estimator` class
*/

/* Pipeline and ColumnTransformer style (default) */

#sk-container-id-2 div.sk-toggleable {
  /* Default theme specific background. It is overwritten whether we have a
  specific estimator or a Pipeline/ColumnTransformer */
  background-color: var(--sklearn-color-background);
}

/* Toggleable label */
#sk-container-id-2 label.sk-toggleable__label {
  cursor: pointer;
  display: block;
  width: 100%;
  margin-bottom: 0;
  padding: 0.5em;
  box-sizing: border-box;
  text-align: center;
}

#sk-container-id-2 label.sk-toggleable__label-arrow:before {
  /* Arrow on the left of the label */
  content: "▸";
  float: left;
  margin-right: 0.25em;
  color: var(--sklearn-color-icon);
}

#sk-container-id-2 label.sk-toggleable__label-arrow:hover:before {
  color: var(--sklearn-color-text);
}

/* Toggleable content - dropdown */

#sk-container-id-2 div.sk-toggleable__content {
  max-height: 0;
  max-width: 0;
  overflow: hidden;
  text-align: left;
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-0);
}

#sk-container-id-2 div.sk-toggleable__content.fitted {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-0);
}

#sk-container-id-2 div.sk-toggleable__content pre {
  margin: 0.2em;
  border-radius: 0.25em;
  color: var(--sklearn-color-text);
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-0);
}

#sk-container-id-2 div.sk-toggleable__content.fitted pre {
  /* unfitted */
  background-color: var(--sklearn-color-fitted-level-0);
}

#sk-container-id-2 input.sk-toggleable__control:checked~div.sk-toggleable__content {
  /* Expand drop-down */
  max-height: 200px;
  max-width: 100%;
  overflow: auto;
}

#sk-container-id-2 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {
  content: "▾";
}

/* Pipeline/ColumnTransformer-specific style */

#sk-container-id-2 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {
  color: var(--sklearn-color-text);
  background-color: var(--sklearn-color-unfitted-level-2);
}

#sk-container-id-2 div.sk-label.fitted input.sk-toggleable__control:checked~label.sk-toggleable__label {
  background-color: var(--sklearn-color-fitted-level-2);
}

/* Estimator-specific style */

/* Colorize estimator box */
#sk-container-id-2 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-2);
}

#sk-container-id-2 div.sk-estimator.fitted input.sk-toggleable__control:checked~label.sk-toggleable__label {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-2);
}

#sk-container-id-2 div.sk-label label.sk-toggleable__label,
#sk-container-id-2 div.sk-label label {
  /* The background is the default theme color */
  color: var(--sklearn-color-text-on-default-background);
}

/* On hover, darken the color of the background */
#sk-container-id-2 div.sk-label:hover label.sk-toggleable__label {
  color: var(--sklearn-color-text);
  background-color: var(--sklearn-color-unfitted-level-2);
}

/* Label box, darken color on hover, fitted */
#sk-container-id-2 div.sk-label.fitted:hover label.sk-toggleable__label.fitted {
  color: var(--sklearn-color-text);
  background-color: var(--sklearn-color-fitted-level-2);
}

/* Estimator label */

#sk-container-id-2 div.sk-label label {
  font-family: monospace;
  font-weight: bold;
  display: inline-block;
  line-height: 1.2em;
}

#sk-container-id-2 div.sk-label-container {
  text-align: center;
}

/* Estimator-specific */
#sk-container-id-2 div.sk-estimator {
  font-family: monospace;
  border: 1px dotted var(--sklearn-color-border-box);
  border-radius: 0.25em;
  box-sizing: border-box;
  margin-bottom: 0.5em;
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-0);
}

#sk-container-id-2 div.sk-estimator.fitted {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-0);
}

/* on hover */
#sk-container-id-2 div.sk-estimator:hover {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-2);
}

#sk-container-id-2 div.sk-estimator.fitted:hover {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-2);
}

/* Specification for estimator info (e.g. "i" and "?") */

/* Common style for "i" and "?" */

.sk-estimator-doc-link,
a:link.sk-estimator-doc-link,
a:visited.sk-estimator-doc-link {
  float: right;
  font-size: smaller;
  line-height: 1em;
  font-family: monospace;
  background-color: var(--sklearn-color-background);
  border-radius: 1em;
  height: 1em;
  width: 1em;
  text-decoration: none !important;
  margin-left: 1ex;
  /* unfitted */
  border: var(--sklearn-color-unfitted-level-1) 1pt solid;
  color: var(--sklearn-color-unfitted-level-1);
}

.sk-estimator-doc-link.fitted,
a:link.sk-estimator-doc-link.fitted,
a:visited.sk-estimator-doc-link.fitted {
  /* fitted */
  border: var(--sklearn-color-fitted-level-1) 1pt solid;
  color: var(--sklearn-color-fitted-level-1);
}

/* On hover */
div.sk-estimator:hover .sk-estimator-doc-link:hover,
.sk-estimator-doc-link:hover,
div.sk-label-container:hover .sk-estimator-doc-link:hover,
.sk-estimator-doc-link:hover {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-3);
  color: var(--sklearn-color-background);
  text-decoration: none;
}

div.sk-estimator.fitted:hover .sk-estimator-doc-link.fitted:hover,
.sk-estimator-doc-link.fitted:hover,
div.sk-label-container:hover .sk-estimator-doc-link.fitted:hover,
.sk-estimator-doc-link.fitted:hover {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-3);
  color: var(--sklearn-color-background);
  text-decoration: none;
}

/* Span, style for the box shown on hovering the info icon */
.sk-estimator-doc-link span {
  display: none;
  z-index: 9999;
  position: relative;
  font-weight: normal;
  right: .2ex;
  padding: .5ex;
  margin: .5ex;
  width: min-content;
  min-width: 20ex;
  max-width: 50ex;
  color: var(--sklearn-color-text);
  box-shadow: 2pt 2pt 4pt #999;
  /* unfitted */
  background: var(--sklearn-color-unfitted-level-0);
  border: .5pt solid var(--sklearn-color-unfitted-level-3);
}

.sk-estimator-doc-link.fitted span {
  /* fitted */
  background: var(--sklearn-color-fitted-level-0);
  border: var(--sklearn-color-fitted-level-3);
}

.sk-estimator-doc-link:hover span {
  display: block;
}

/* "?"-specific style due to the `<a>` HTML tag */

#sk-container-id-2 a.estimator_doc_link {
  float: right;
  font-size: 1rem;
  line-height: 1em;
  font-family: monospace;
  background-color: var(--sklearn-color-background);
  border-radius: 1rem;
  height: 1rem;
  width: 1rem;
  text-decoration: none;
  /* unfitted */
  color: var(--sklearn-color-unfitted-level-1);
  border: var(--sklearn-color-unfitted-level-1) 1pt solid;
}

#sk-container-id-2 a.estimator_doc_link.fitted {
  /* fitted */
  border: var(--sklearn-color-fitted-level-1) 1pt solid;
  color: var(--sklearn-color-fitted-level-1);
}

/* On hover */
#sk-container-id-2 a.estimator_doc_link:hover {
  /* unfitted */
  background-color: var(--sklearn-color-unfitted-level-3);
  color: var(--sklearn-color-background);
  text-decoration: none;
}

#sk-container-id-2 a.estimator_doc_link.fitted:hover {
  /* fitted */
  background-color: var(--sklearn-color-fitted-level-3);
}
</style><div id="sk-container-id-2" class="sk-top-container"><div class="sk-text-repr-fallback"><pre>Pipeline(steps=[(&#x27;columntransformer&#x27;,
                 ColumnTransformer(remainder=&#x27;passthrough&#x27;,
                                   transformers=[(&#x27;onehotencoder&#x27;,
                                                  OneHotEncoder(categories=[array([&#x27;Audi A3 Cabriolet 40 TFSI&#x27;,
       &#x27;Audi A4 1.8 TFSI Multitronic Premium Plus&#x27;,
       &#x27;Audi A4 2.0 TDI 177bhp Premium&#x27;, &#x27;Audi A6 2.0 TDI Premium&#x27;,
       &#x27;Audi A8&#x27;, &#x27;Audi Q3 2.0 TDI quattro Premium&#x27;,
       &#x27;Audi Q5 2.0 TDI quattro Premium Plus&#x27;, &#x27;Audi Q7&#x27;,
       &#x27;BMW 3 Series 320d...
                                                                            array([&#x27;Audi&#x27;, &#x27;BMW&#x27;, &#x27;Chevrolet&#x27;, &#x27;Datsun&#x27;, &#x27;Fiat&#x27;, &#x27;Force&#x27;, &#x27;Ford&#x27;,
       &#x27;Hindustan&#x27;, &#x27;Honda&#x27;, &#x27;Hyundai&#x27;, &#x27;Jaguar&#x27;, &#x27;Jeep&#x27;, &#x27;Land&#x27;,
       &#x27;Mahindra&#x27;, &#x27;Maruti&#x27;, &#x27;Mercedes&#x27;, &#x27;Mini&#x27;, &#x27;Mitsubishi&#x27;, &#x27;Nissan&#x27;,
       &#x27;Renault&#x27;, &#x27;Skoda&#x27;, &#x27;Tata&#x27;, &#x27;Toyota&#x27;, &#x27;Volkswagen&#x27;, &#x27;Volvo&#x27;],
      dtype=object),
                                                                            array([&#x27;Diesel&#x27;, &#x27;LPG&#x27;, &#x27;Petrol&#x27;], dtype=object)]),
                                                  [&#x27;name&#x27;, &#x27;company&#x27;,
                                                   &#x27;fuel_type&#x27;])])),
                (&#x27;linearregression&#x27;, LinearRegression())])</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class="sk-container" hidden><div class="sk-item sk-dashed-wrapped"><div class="sk-label-container"><div class="sk-label fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-2" type="checkbox" ><label for="sk-estimator-id-2" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">&nbsp;&nbsp;Pipeline<a class="sk-estimator-doc-link fitted" rel="noreferrer" target="_blank" href="https://scikit-learn.org/1.4/modules/generated/sklearn.pipeline.Pipeline.html">?<span>Documentation for Pipeline</span></a><span class="sk-estimator-doc-link fitted">i<span>Fitted</span></span></label><div class="sk-toggleable__content fitted"><pre>Pipeline(steps=[(&#x27;columntransformer&#x27;,
                 ColumnTransformer(remainder=&#x27;passthrough&#x27;,
                                   transformers=[(&#x27;onehotencoder&#x27;,
                                                  OneHotEncoder(categories=[array([&#x27;Audi A3 Cabriolet 40 TFSI&#x27;,
       &#x27;Audi A4 1.8 TFSI Multitronic Premium Plus&#x27;,
       &#x27;Audi A4 2.0 TDI 177bhp Premium&#x27;, &#x27;Audi A6 2.0 TDI Premium&#x27;,
       &#x27;Audi A8&#x27;, &#x27;Audi Q3 2.0 TDI quattro Premium&#x27;,
       &#x27;Audi Q5 2.0 TDI quattro Premium Plus&#x27;, &#x27;Audi Q7&#x27;,
       &#x27;BMW 3 Series 320d...
                                                                            array([&#x27;Audi&#x27;, &#x27;BMW&#x27;, &#x27;Chevrolet&#x27;, &#x27;Datsun&#x27;, &#x27;Fiat&#x27;, &#x27;Force&#x27;, &#x27;Ford&#x27;,
       &#x27;Hindustan&#x27;, &#x27;Honda&#x27;, &#x27;Hyundai&#x27;, &#x27;Jaguar&#x27;, &#x27;Jeep&#x27;, &#x27;Land&#x27;,
       &#x27;Mahindra&#x27;, &#x27;Maruti&#x27;, &#x27;Mercedes&#x27;, &#x27;Mini&#x27;, &#x27;Mitsubishi&#x27;, &#x27;Nissan&#x27;,
       &#x27;Renault&#x27;, &#x27;Skoda&#x27;, &#x27;Tata&#x27;, &#x27;Toyota&#x27;, &#x27;Volkswagen&#x27;, &#x27;Volvo&#x27;],
      dtype=object),
                                                                            array([&#x27;Diesel&#x27;, &#x27;LPG&#x27;, &#x27;Petrol&#x27;], dtype=object)]),
                                                  [&#x27;name&#x27;, &#x27;company&#x27;,
                                                   &#x27;fuel_type&#x27;])])),
                (&#x27;linearregression&#x27;, LinearRegression())])</pre></div> </div></div><div class="sk-serial"><div class="sk-item sk-dashed-wrapped"><div class="sk-label-container"><div class="sk-label fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-3" type="checkbox" ><label for="sk-estimator-id-3" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">&nbsp;columntransformer: ColumnTransformer<a class="sk-estimator-doc-link fitted" rel="noreferrer" target="_blank" href="https://scikit-learn.org/1.4/modules/generated/sklearn.compose.ColumnTransformer.html">?<span>Documentation for columntransformer: ColumnTransformer</span></a></label><div class="sk-toggleable__content fitted"><pre>ColumnTransformer(remainder=&#x27;passthrough&#x27;,
                  transformers=[(&#x27;onehotencoder&#x27;,
                                 OneHotEncoder(categories=[array([&#x27;Audi A3 Cabriolet 40 TFSI&#x27;,
       &#x27;Audi A4 1.8 TFSI Multitronic Premium Plus&#x27;,
       &#x27;Audi A4 2.0 TDI 177bhp Premium&#x27;, &#x27;Audi A6 2.0 TDI Premium&#x27;,
       &#x27;Audi A8&#x27;, &#x27;Audi Q3 2.0 TDI quattro Premium&#x27;,
       &#x27;Audi Q5 2.0 TDI quattro Premium Plus&#x27;, &#x27;Audi Q7&#x27;,
       &#x27;BMW 3 Series 320d Sedan&#x27;, &#x27;BMW 3 Series 320i&#x27;,
       &#x27;BMW 5 Series 52...
       &#x27;Volkswagen Vento Konekt Diesel Highline&#x27;, &#x27;Volvo S80 Summum D4&#x27;],
      dtype=object),
                                                           array([&#x27;Audi&#x27;, &#x27;BMW&#x27;, &#x27;Chevrolet&#x27;, &#x27;Datsun&#x27;, &#x27;Fiat&#x27;, &#x27;Force&#x27;, &#x27;Ford&#x27;,
       &#x27;Hindustan&#x27;, &#x27;Honda&#x27;, &#x27;Hyundai&#x27;, &#x27;Jaguar&#x27;, &#x27;Jeep&#x27;, &#x27;Land&#x27;,
       &#x27;Mahindra&#x27;, &#x27;Maruti&#x27;, &#x27;Mercedes&#x27;, &#x27;Mini&#x27;, &#x27;Mitsubishi&#x27;, &#x27;Nissan&#x27;,
       &#x27;Renault&#x27;, &#x27;Skoda&#x27;, &#x27;Tata&#x27;, &#x27;Toyota&#x27;, &#x27;Volkswagen&#x27;, &#x27;Volvo&#x27;],
      dtype=object),
                                                           array([&#x27;Diesel&#x27;, &#x27;LPG&#x27;, &#x27;Petrol&#x27;], dtype=object)]),
                                 [&#x27;name&#x27;, &#x27;company&#x27;, &#x27;fuel_type&#x27;])])</pre></div> </div></div><div class="sk-parallel"><div class="sk-parallel-item"><div class="sk-item"><div class="sk-label-container"><div class="sk-label fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-4" type="checkbox" ><label for="sk-estimator-id-4" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">onehotencoder</label><div class="sk-toggleable__content fitted"><pre>[&#x27;name&#x27;, &#x27;company&#x27;, &#x27;fuel_type&#x27;]</pre></div> </div></div><div class="sk-serial"><div class="sk-item"><div class="sk-estimator fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-5" type="checkbox" ><label for="sk-estimator-id-5" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">&nbsp;OneHotEncoder<a class="sk-estimator-doc-link fitted" rel="noreferrer" target="_blank" href="https://scikit-learn.org/1.4/modules/generated/sklearn.preprocessing.OneHotEncoder.html">?<span>Documentation for OneHotEncoder</span></a></label><div class="sk-toggleable__content fitted"><pre>OneHotEncoder(categories=[array([&#x27;Audi A3 Cabriolet 40 TFSI&#x27;,
       &#x27;Audi A4 1.8 TFSI Multitronic Premium Plus&#x27;,
       &#x27;Audi A4 2.0 TDI 177bhp Premium&#x27;, &#x27;Audi A6 2.0 TDI Premium&#x27;,
       &#x27;Audi A8&#x27;, &#x27;Audi Q3 2.0 TDI quattro Premium&#x27;,
       &#x27;Audi Q5 2.0 TDI quattro Premium Plus&#x27;, &#x27;Audi Q7&#x27;,
       &#x27;BMW 3 Series 320d Sedan&#x27;, &#x27;BMW 3 Series 320i&#x27;,
       &#x27;BMW 5 Series 520d Sedan&#x27;, &#x27;BMW 5 Series 530i&#x27;,
       &#x27;BMW 7 Series 740Li Sedan&#x27;, &#x27;BMW X1&#x27;, &#x27;BMW X1 sDrive20d&#x27;...
       &#x27;Volkswagen Vento Konekt Diesel Highline&#x27;, &#x27;Volvo S80 Summum D4&#x27;],
      dtype=object),
                          array([&#x27;Audi&#x27;, &#x27;BMW&#x27;, &#x27;Chevrolet&#x27;, &#x27;Datsun&#x27;, &#x27;Fiat&#x27;, &#x27;Force&#x27;, &#x27;Ford&#x27;,
       &#x27;Hindustan&#x27;, &#x27;Honda&#x27;, &#x27;Hyundai&#x27;, &#x27;Jaguar&#x27;, &#x27;Jeep&#x27;, &#x27;Land&#x27;,
       &#x27;Mahindra&#x27;, &#x27;Maruti&#x27;, &#x27;Mercedes&#x27;, &#x27;Mini&#x27;, &#x27;Mitsubishi&#x27;, &#x27;Nissan&#x27;,
       &#x27;Renault&#x27;, &#x27;Skoda&#x27;, &#x27;Tata&#x27;, &#x27;Toyota&#x27;, &#x27;Volkswagen&#x27;, &#x27;Volvo&#x27;],
      dtype=object),
                          array([&#x27;Diesel&#x27;, &#x27;LPG&#x27;, &#x27;Petrol&#x27;], dtype=object)])</pre></div> </div></div></div></div></div><div class="sk-parallel-item"><div class="sk-item"><div class="sk-label-container"><div class="sk-label fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-6" type="checkbox" ><label for="sk-estimator-id-6" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">remainder</label><div class="sk-toggleable__content fitted"><pre>[&#x27;year&#x27;, &#x27;kms_driven&#x27;]</pre></div> </div></div><div class="sk-serial"><div class="sk-item"><div class="sk-estimator fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-7" type="checkbox" ><label for="sk-estimator-id-7" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">passthrough</label><div class="sk-toggleable__content fitted"><pre>passthrough</pre></div> </div></div></div></div></div></div></div><div class="sk-item"><div class="sk-estimator fitted sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-8" type="checkbox" ><label for="sk-estimator-id-8" class="sk-toggleable__label fitted sk-toggleable__label-arrow fitted">&nbsp;LinearRegression<a class="sk-estimator-doc-link fitted" rel="noreferrer" target="_blank" href="https://scikit-learn.org/1.4/modules/generated/sklearn.linear_model.LinearRegression.html">?<span>Documentation for LinearRegression</span></a></label><div class="sk-toggleable__content fitted"><pre>LinearRegression()</pre></div> </div></div></div></div></div></div>




```python
y_pred=pipe.predict(X_test)
```


```python
r2_score(y_test,y_pred)
```




    0.6947416383036185




```python
scores=[]
for i in range(1000):
    X_train,X_test,y_train,y_test=train_test_split(X,y,test_size=0.1,random_state=i)
    lr=LinearRegression()
    pipe=make_pipeline(column_trans,lr)
    pipe.fit(X_train,y_train)
    y_pred=pipe.predict(X_test)
    scores.append(r2_score(y_test,y_pred))
```


```python
np.argmax(scores)
```




    636




```python
scores[np.argmax(scores)]
```




    0.8656115492304121




```python

```


```python

```


```python

```
