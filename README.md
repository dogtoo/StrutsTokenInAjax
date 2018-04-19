# StrutsTokenInAjax
透過Ajax的方式使用Struts的Token Interceptor

token Interceptor是struts2攔截器中一個功能，主要避免像login、register這樣的頁面使用者按回到上一頁或reload時重覆執行造成問題。
<p>
    運作方式為在login.jsp或register.jsp裡放上<s:token/>在使用者進入頁面時Server會對該session產生一個長字串，也就是Token Value，畫面中的<s:token/>
會轉換成<input type='hidden' name='token' value='XXXXXXXXXXXXXXXXXX'/>。
<p>
    當使用者執行login或註冊時將該值與資料一併送到AP，AP會比對該值是否與目前的Token Value是相同的，若值為相同會將程序invoke到action Class 或下一個攔截器並將該token Value設為無效。比對不符即result 到設定的錯誤程序裡。

為
