clear
*Data input
input time n_male n_female p_bw_male p_bw_female p_bd_male p_bd_female p_bn_male p_bn_female
9 34 38 0.08 0.12 0 0 0 0
12 46 50 0.32 0.39 0 0 0 0
18 85 79  0.57 0.65 0.10 0.16 0.02 0.06
24 152 150 0.73 0.83 0.17 0.22 0.07 0.09
36 162 161 0.96 0.98 0.18 0.18 0.16 0.22
48 163 161 0.98 0.97 0.89 0.89 0.86 0.86
60 143 146 0.98 0.99 0.92 0.92 0.86 0.89
72 152 156 0.99 0.99 0.97 0.97 0.90 0.94
end
*Bowel movement
gen pct_bw_male = 100*p_bw_male
gen pct_bw_female = 100*p_bw_female
graph twoway (line pct_bw_male time, lcolor(blue) ) (line pct_bw_female time, lcolor(red) ) ///
 (scatter pct_bw_male time, color(blue) msize(small)) (scatter pct_bw_female time, color(red) msize(small)) ///
 , legend(off) ///
 xtitle(月齢) ytitle(排便コントロール完了 (%)) ///
 xlabel(6(6)72) xline(12 24 36 48 60 72, lcolor(gray) lpattern(dot)) ///
 graphregion( color(white) ) plotregion(  fcolor(white) )
*Daily bladder movement
gen pct_bd_male = 100*p_bd_male
gen pct_bd_female = 100*p_bd_female +1
graph twoway (line pct_bd_male time, lcolor(blue) lwidth(thin) ) (line pct_bd_female time, lcolor(red) lwidth(thin) ) ///
 (scatter pct_bd_male time, color(blue) msize(small)) (scatter pct_bd_female time, color(red) msize(small)) ///
 , legend(off) ///
 xtitle(月齢) ytitle(日中の排尿コントロール完了 (%)) ///
 xlabel(6(6)72) xline(12 24 36 48 60 72, lcolor(gray) lpattern(dot)) ///
 graphregion( color(white) ) plotregion(  fcolor(white) )
*Night bladder movement
gen pct_bn_male = 100*p_bn_male
gen pct_bn_female = 100*p_bn_female
graph twoway (line pct_bn_male time, lcolor(blue) lwidth(thin) ) (line pct_bn_female time, lcolor(red) lwidth(thin) ) ///
 (scatter pct_bn_male time, color(blue) msize(small)) (scatter pct_bn_female time, color(red) msize(small)) ///
 , legend(off) ///
 xtitle(月齢) ytitle(夜間の排尿コントロール完了 (%)) ///
 xlabel(6(6)72) xline(12 24 36 48 60 72, lcolor(gray) lpattern(dot)) ///
 graphregion( color(white) ) plotregion(  fcolor(white) )
