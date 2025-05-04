!-- 4.  Satılan araçların marka ve modelini bulmak için gerekli SQL ifadesini yazınız.

select a.marka,a.model from satislar s inner join 
araclar a on a.Aracno = s.Aracno

!-- 5.	Toplam satış ve toplam alım tutarlarını ve bunların farkını bulmak için gerekli SQL ifadesini yazınız.
select (SELECT COUNT(S_Fiyat) from satislar) as toplam_satis,
(SELECT COUNT(A_Fiyat) from alislar) as toplam_alım,
(SELECT COUNT(S_Fiyat) from satislar) - (SELECT COUNT(A_Fiyat) from alislar) as fark

!-- 6.	Hiç satışı yapılmamış araçları listelemek için gerekli SQL ifadesini yazınız.
SELECT a.* FROM araclar a 
left join alislar al ON a.Aracno = al.Aracno
WHERE a.Aracno is null
