
komandinės eilutės įrankiai 1
CLI klaidos 2
Failai ir jų naudojimo teisės 3
Procesai ir jų valdymas 4
Git Sistema 5
BASH skriptai 6


Aprašomos temos - "Versiju valdymo įranga git",  akcentai


Pakalbėti ir susipažinti kas yra failų versijų valdymo sistema git, kadangi dauguma žmonių, 
kurie sieks karjeros programuojant, tikėtina, jog naudos git sistemą.

Git – tai versijų valdymo sistema, leidžianti stebėti kompiuterinių failų keitimą ir koordinuoti skirtingų žmonių darbą su jais. Git sistemą naudojasi didelės kompanijos kaip “Facebook”, “Google”, “Microsoft”

Daugiausia naudojama išeities kodų priežiūrai kuriant programinę įrangą, bet galima naudoti bet kokių failų keitimo priežiūrai. Išeities kodas – taisyklių, nurodančių ką turi daryti kompiuteris, rinkinys, parašytas kokia nors programavimo kalba. 

Git – tai paskirstyta taisymų kontrolės sistema, sukurta siekiant greito naudojimo, duomenų integralumo ir paskirstytos, netiesinės darbo eigos.
„Paskirstyta sistema“ reiškia, kad kiekvienas kompiuteris turi visus taisymus.
Serverio-kliento sąsaja leidžia iš kito kompiuterio atsisiųsti įdiegtus pakeitimus ir nusiųsti kitam kompiuteriui savo peržiūras.
Paprastai būna vienas centrinis serveris, su kuriuo viskas sinchronizuojama.

Git naudoja paskirstytą talpyklų sistemą. Kopijuodamiesi kodą, gaunate visą kodą   Tai reiškia, kad kiekvienas vartotojas turi serverio failų atsarginę versiją.
Failai gali turėti tris būsenas: Užregistruotas („committed“) – failo versija yra jūsų vietinėje talpykloje („visam“ laikui), Pakeistas („modified“) – jūs pakeitėte failo turinį, bet dar neužregistravote, failas yra jūsų darbiniame kataloge, Pažymėtas („staged“) – failo versija yra pažymėta užregistravimui

Taikant kriptografinius metodus, kiekvienas failas ir kiekvienas atnaujinimas yra pažymimas maišos (angl. „hash“) kodu.  Tai garantuoja duomenų perdavimo tikslumą  Bet koks pakeitimas yra registruojamas – jūs visada pamatysite kas įvyksta pagrindinėje talpykloje.

Git sistema leidžia turėti kelias failo versijas ir skirtingas vystymo šakas (angl. „branches“). Lengva aktyvuoti bet kurią failo versiją ar persijungti iš vienos šakos į kitą.
Kai dirbame su keliomis šakomis arba tuos pačius failus redaguoja keli žmonės, kartais problemų nekyla – ir pakeitimus sklandžiai įdiegia pati git sistema ( failų sujungimo apraše matome „fast forward“ ). Tačiau kartais įvyksta versijų konfliktai: git sistema negali pati nuspręsti, kurią versiją reikia laikyti galutine. Tada sistema pažymi atsiradusį konfliktą ir prašo vartotojo jį išspręsti ( failų sujungimo apraše matome „merge conflict“).



Referuojamsos temos - "Git aplinkos paruošimas" bei “Git komandinė eilutė”, akcentai.

Paruošti git sistemos aplinką. Jei pagrindinių nustatymų - vardo ir e-adreso nebūtų, git sistema mums tą nuolatos primintų. Reikalingos komandos, tai įvykdyti:
git config --global user.name "Vardas Pavardė" - Nustatykite autoriaus (Git naudodojo) vardą
git config --global user.email vardas.pavarde@mail.com 	- Nustatykite autoriaus (Git naudodojo) el. paštą
git config –list - Patikrinti vartotojo profilį

Pamėginti naudoti git komandas savo kompiuteryje ir įrodyti, jog turėdami dvi vienos talpyklos kopijas jos nėra tiesiogiai susijusios.

Git komandinis žodinėlis: 
git init - Inicializuoti lokalią Git repoziciją (saugyklą) dabartiniame kataloge
git clone <url-adresas>	- Sukurti lokalią kopiją nuotolinės repozicijos
git status - Patikrinti repozicijos statusą
git add <failo-vardas> - Pridėti (angl. stage) naują/modifikuotą failą (į index sritį) kitam commit'ui
git commit - Commit'inti išsaugotus (stage'intus) failus (index srityje)
git commit -a - dvi komandos: git commit + git add vienoje
git rm -r <failo-vardas>	- Ištrinti failą/katalogą iš Git repozicijos
git log - Parodyti repozicijos commit'ų istoriją naudojant standartinį formatą
git diff - Parodyti unstaged skirtumus tarp index srities ir darbinio katalogo
git push - Siūsti atnaujinimus į nuotolinę repoziciją serveryje (į įsimintą branch'ą)
git pull - Atnaujinti lokalią repozicją pagal nuotolinę versiją (atsisiūsti commit'us iš serverio)
git push origin <branch-vardas>	- Siūsti branch'ą į nuotolinę repoziciją

