# 基本功问题

`<< endl;` 是用于换行的，没有它也可以结句

# 程序改进

1. 中间数的存在与否

   自己写的看起来有点长，计算量小；人家写的很简练，但每次计算量都很大；

   ```c++
   int day = seconds / sec_per_min / min_per_hour / hour_per_day;
   int remain = seconds % (sec_per_min * min_per_hour * hour_per_day);
   int hour = remain / (sec_per_min * min_per_hour);
   remain = seconds % (sec_per_min * min_per_hour);
   int min = remain / sec_per_min;
   remain = remain % sec_per_min;
   
   //聪明的答案
   int day, hour, min, remain;
   day = seconds / sec_per_min/ min_per_hour / hour_per_day;
   hour = seconds / sec_per_min / min_per_hour % hour_per_day;
   min = seconds / sec_per_min % min_per_hour;
   remain = seconds % sec_per_min;
   ```

   