#Naujienų Sistema
Ši naujienų rekomendacinė sistema naudoja Flask API ir sklearn biblioteką. Ji leidžia vartotojui įkelti failą su naujienomis, aktyvuoti teksto analizę, matyti sąrašą naujienų, esančių faile, pasirinkti dominančią naujieną ir gauti rekomendaciją dar vienai naujienai.

Flask API
Flask API yra pagrindinė programa, kuri veikia kaip serveris ir priima užklausas iš kliento. Šiame projekte yra trys maršrutai: pagrindinis puslapis (/), failo įkėlimo maršrutas (/upload_file) ir teksto apdorojimo maršrutas (/process_text).

Pagrindinis puslapis (/)
Tai yra pagrindinis puslapis, kuris grąžina HTML šabloną template.html.

Failo įkėlimo maršrutas (/upload_file)
Tai yra POST maršrutas, kuris priima failą iš kliento. Failas turėtų būti tekstiniame formate ir turėtų turėti naujienų sąrašą. Kiekviena naujiena turėtų būti naujoje eilutėje. Failas nuskaitomas ir naujienos saugomos serverio atmintyje.

Teksto apdorojimo maršrutas (/process_text)
Tai yra POST maršrutas, kuris priima JSON užklausą su pasirinkto straipsnio indeksu. Jis naudoja TF-IDF vektorizatorių, kad paverstų tekstus į vektorius, o tada naudoja kosinusinį panašumą, kad rastų panašiausią straipsnį į pasirinktą straipsnį. Galiausiai jis grąžina pasirinktą ir rekomenduojamą straipsnį.

HTML šablonas (template.html)
Tai yra HTML failas, kuris yra grąžinamas, kai vartotojas apsilanko pagrindiniame puslapyje. Jis turi teksto įvesties lauką, pasirinkimo lauką naujienoms pasirinkti, mygtuką siųsti tekstą ir rezultatų lauką. Kliento pusės JavaScript kodas siunčia teksto ir pasirinkto straipsnio indekso užklausą į /process_text maršrutą ir atvaizduoja rezultatus.


Kaip naudotis:
Paleiskite Flask API.
Atidarykite naršyklėje http://localhost:5000.
Įkelkite failą su naujienomis paspaudę mygtuką “Įkelti failą”.
Paspauskite mygtuką “Gauti naujienas”, kad atnaujintumėte naujienų sąrašą.
Pasirinkite dominančią naujieną iš sąrašo.
Paspauskite mygtuką “Siųsti tekstą”, kad gautumėte rekomendaciją.
