敘述
javax.persistence.Query getSingleResult(),只能返回單個值,但是最近在在使用的時候它總是報錯:NoResultException:No entity found for query或者NonUniqueResultException!一開始遇到這個問題的時候很是鬱悶!

報錯原因:
1、沒有查詢到結果→ 就是你sql 裡面沒檔案!
2、查詢到了多條結果
