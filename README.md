# Analiza predšolske vzgoje v Sloveniji

Repozitorij z gradivi pri predmetu APPR v študijskem letu 2019/20

* [![Shiny](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/jaanos/APPR-2019-20/master?urlpath=shiny/APPR-2019-20/projekt.Rmd) Shiny
* [![RStudio](http://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/jaanos/APPR-2019-20/master?urlpath=rstudio) RStudio

## Tematika

V projektni nalogi bom analizirala vključenost otrok v predšolskih zavodih v Sloveniji po statističnih regijah.
Primerjala bom število otrok glede na vrtec in število otrok glede na vzgojitelja in pomočnika vzgojitelja, koliko predšolskih zavodov imamo v Sloveniji glede na število otrok, ter koliko je otrok v vrtcih glede na starost in spol. Pogledala si bom tudi kakšni so javni izdatki za formalno izobraževanje glede na raven izobraževanja in njeni porabi.

Podatke bom pridobila na spletni strani Statističnega urada Republike Slovenije, kjer bodo podatki prikazani od šolskega leta 2006/07 do šolskega leta 2018/19.


### Tabele

* TABELA 1: Otroci, vključeni v vrtec, po statistični regiji stalnega prebivališča in spolu, Slovenija, letno

* TABELA 2: Otroci, vključeni v vrtec, po statistični regiji zavoda, vrsti vrtca (lastnina) in starosti otrok, Slovenija, letno

* TABELA 3: Število Vrtcev glede na število otrok, po statistični regiji zavoda, Slovenija, letno

* TABELA 4:Število otrok na vrtec in število otrok na vzgojitelja in pomočnika vzgojitelja, statistične regije, Slovenija, letno

* TABELA 5: Izbrani podatki o otrocih in strokovnih delavcih v vrtcih, Slovenija, letno

* TABELA 6: Delež otrok, vključenih v vrtce, po statistični regiji stalnega prebivališča in starostnih obdobjih, Slovenija, letno

* TABELA 7: Javni izdatki za formalno izobraževanje po ravneh izobraževanja in namenu porabe (1000 EUR), Slovenija, letno

### Viri

Podatke bom pridobila na spletni strani Statističnega urada Republike Slovenije.

* https://pxweb.stat.si/SiStatDb/pxweb/sl/10_Dem_soc/10_Dem_soc__09_izobrazevanje__03_predsol_vzgoja__01_09525_otroci_vrtci/0952532S.px/

* https://pxweb.stat.si/SiStatDb/pxweb/sl/10_Dem_soc/10_Dem_soc__09_izobrazevanje__03_predsol_vzgoja__01_09525_otroci_vrtci/0952542S.px/

* https://pxweb.stat.si/SiStatDb/pxweb/sl/10_Dem_soc/10_Dem_soc__09_izobrazevanje__03_predsol_vzgoja__01_09525_otroci_vrtci/0952573S.px/

* https://pxweb.stat.si/SiStatDb/pxweb/sl/10_Dem_soc/10_Dem_soc__09_izobrazevanje__03_predsol_vzgoja__03_09714_vrtci_kazalniki/0971417S.px/

* https://pxweb.stat.si/SiStatDb/pxweb/sl/HITRE_Repozitorij/HITRE_Repozitorij/H094S.px/


* https://pxweb.stat.si/SiStatDb/pxweb/sl/10_Dem_soc/10_Dem_soc__09_izobrazevanje__03_predsol_vzgoja__03_09714_vrtci_kazalniki/0971413S.px/

* https://pxweb.stat.si/SiStatDb/pxweb/sl/10_Dem_soc/10_Dem_soc__09_izobrazevanje__10_drugi_podatki__04_09733_izdatki_izobrazevanje/0973301S.px/


## Program

Glavni program in poročilo se nahajata v datoteki `projekt.Rmd`.
Ko ga prevedemo, se izvedejo programi, ki ustrezajo drugi, tretji in četrti fazi projekta:

* obdelava, uvoz in čiščenje podatkov: `uvoz/uvoz.r`
* analiza in vizualizacija podatkov: `vizualizacija/vizualizacija.r`
* napredna analiza podatkov: `analiza/analiza.r`

Vnaprej pripravljene funkcije se nahajajo v datotekah v mapi `lib/`.
Podatkovni viri so v mapi `podatki/`.
Zemljevidi v obliki SHP, ki jih program pobere,
se shranijo v mapo `../zemljevidi/` (torej izven mape projekta).

## Potrebni paketi za R

Za zagon tega vzorca je potrebno namestiti sledeče pakete za R:

* `knitr` - za izdelovanje poročila
* `rmarkdown` - za prevajanje poročila v obliki RMarkdown
* `shiny` - za prikaz spletnega vmesnika
* `DT` - za prikaz interaktivne tabele
* `rgdal` - za uvoz zemljevidov
* `rgeos` - za podporo zemljevidom
* `digest` - za zgoščevalne funkcije (uporabljajo se za shranjevanje zemljevidov)
* `readr` - za branje podatkov
* `rvest` - za pobiranje spletnih strani
* `tidyr` - za preoblikovanje podatkov v obliko *tidy data*
* `dplyr` - za delo s podatki
* `gsubfn` - za delo z nizi (čiščenje podatkov)
* `ggplot2` - za izrisovanje grafov
* `mosaic` - za pretvorbo zemljevidov v obliko za risanje z `ggplot2`
* `maptools` - za delo z zemljevidi
* `extrafont` - za pravilen prikaz šumnikov (neobvezno)

## Binder

Zgornje [povezave](#analiza-podatkov-s-programom-r-201819)
omogočajo poganjanje projekta na spletu z orodjem [Binder](https://mybinder.org/).
V ta namen je bila pripravljena slika za [Docker](https://www.docker.com/),
ki vsebuje večino paketov, ki jih boste potrebovali za svoj projekt.

Če se izkaže, da katerega od paketov, ki ji potrebujete, ni v sliki,
lahko za sprotno namestitev poskrbite tako,
da jih v datoteki [`install.R`](install.R) namestite z ukazom `install.packages`.
Te datoteke (ali ukaza `install.packages`) **ne vključujte** v svoj program -
gre samo za navodilo za Binder, katere pakete naj namesti pred poganjanjem vašega projekta.

Tako nameščanje paketov se bo izvedlo pred vsakim poganjanjem v Binderju.
Če se izkaže, da je to preveč zamudno,
lahko pripravite [lastno sliko](https://github.com/jaanos/APPR-docker) z želenimi paketi.

Če želite v Binderju delati z git,
v datoteki `gitconfig` nastavite svoje ime in priimek ter e-poštni naslov
(odkomentirajte vzorec in zamenjajte s svojimi podatki) -
ob naslednjem zagonu bo mogoče delati commite.
Te podatke lahko nastavite tudi z `git config --global` v konzoli
(vendar bodo veljale le v trenutni seji).
