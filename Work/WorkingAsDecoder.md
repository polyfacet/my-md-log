# Jobbet som avkodare

## Innehåll

1. Inledning
2. Varför ska du läsa det här
3. Ett kort stycke programmerarhistorik
4. WIP: Avkodning av specifikationer/lösningsförlag till krav
5. TODO:Illvilligt avkoda programkod till krav
6. TODO:Välvilligt avkoda programkod till krav (och refakturera)
7. Varför skriver jag det här


## Inledning
<p>
    Först hade jag tänkt att skriva en artikel om den svåraste kodtolkningen som jag har ställts inför, men snubblade över lite andra godbitar/äckelbitar som fick in mig på ett annat spår.<br/>
    Slutligen kom jag fram till att den skulle handla om vad jag arbetar med och hur jag ska titulera mitt jobb framöver, inofficiellt. Det jag har kommit fram till är <strong>avkodare</strong> eller kanske omkodare(?).<br/>
</p>

<P>
    Det finns en uppsjö av titlar som skulle passa in på mig: VD, IT-konsult, Fullstack Developer, Technical Project Leader, Lösningsarkitekt, Programmerare, Devop, Backend-programmerare, PLM-konsult med mera. Ingen av dem är fel, men ingen enskild säger tillräckligt mycket för att täcka in jobbet eller är för intetsägande (IT-konsult, PLM-konsult). VD-hatten tar jag bara på mig ett par gånger om året och teknisk projektledning har jag inte gjort på ett tag nu.<br/>
</p>

<img  src="../images/hats_1_small.jpg"></img>
<p>
    Just nu jobbar jag mest som programmerare - eller det är i alla fall vad kunden tror/säger. Egentligen jobbar jag som just avkodare.
    Om jag säger att jag jobbar som programmerare, så tror jag många får bilden av att jag sitter och skriver kod hela dagarna. Att skriva kod en hel dag är en sällan förekommande företelse. Angående programmeringskod, så sägs det att cirka 90% av tiden läggs på att läsa kod och resterande 10% på att skriva kod. Detta innebär inte att jag sitter och läser programmeringskod 90% av tiden, men mer om det senare. Först tar vi en titt på definition av kod/code <a href="https://www.merriam-webster.com/dictionary/code" _target="blank" >www.merriam-webster.com/dictionary/code</a>.
</p>
    

<pre>
    code noun
    
    plural codes
    Definition of code 
        
                
    1 : a systematic statement of a body of law especially : one given statutory force
    
    2 : a system of principles or rules moral code
    
    3
        <span style="background-color:rgb(255, 246, 124)">a : a system of signals or symbols for communication</span>
    
        b : a system of symbols (such as letters or numbers) used to represent assigned and often secret meanings
    
        c : coded language : a word or phrase chosen in place of another word ....

    ...
</pre>


<p>
    Förhoppningsvis kan du avkoda den makerade första definition från engelska till svenska, eller bara tolka det direkt. Det skrivna språket är ju en slags tolkning/kod av/för det talade språket, som vi som barn får lära oss efter att vi fått lära oss det talade språket. En annan typ av kod är kroppspråket, något sagt med en blinkning med ena ögat kan vara en kod för att det man säger är ironiskt/sarkastiskt eller inte sant som exempel. Klädkoder är ett annat exempel där meddelanden kommuniceras, vilka också kan vara mer eller mindre lätta att avkoda korrekt. För den oinvigde kan det som exempel vara svårt att se skillnad på att "jag är Gothare", "jag är Emo" och "jag är Hårdrockare". 
</p>

##  Varför ska du läsa det här
   
<p>
    Varför är min älsklingsfråga, som jag förmodligen kommer att få revidera då min dotter når Varför-åldern. :) <a href="https://sv.wikipedia.org/wiki/5_x_Varf%C3%B6r%3F" target="_blank">5xVarför</a> tycker jag är ett bra verktyg att ha med sig i sin vertygslåda.<br/>
    <h3>Argumenten varför du ska läsa det här om:</h3>         
    <ol class="toc">
        <li>
            Du inte alls jobbar med programmering/mjukvara
            <ul class="toc">
                <li>Kanske få en lite tydligare bild av vad en programmerare egenligen gör om dagarna</li>
                <ul class="toc2">
                    <li>Programmerare är det vanligaste yrket i Stockholmsregionen <a href="https://www.chamber.se/cldocpart/2596.pdf">Stockholms handelskammare 2014:3 (PDF)</a></li>
                    <li>Du interagerar dagligen med saker som är programmerade, allt från en modern bil med 100 miljoner rader kod, till programkod i tvättmaskinen</li>
                </ul>
            </ul>
        </li>
        <li>
            Du jobbar med mjukvara
            <ul class="toc">
                <li>Få inblick i en annan mjukis situation och antingen känna igen det eller få se en annan sida av det.</li>
            </ul>
        </li>
    </ol>
    <p>
    Anledningen till att jag primärt skriver på svenska är att det borde vara lättare för de flesta av de tilltänkta konsumenten att förstå. För icke svenskspråkiga blir det förstås mycket, mycket svårare. Så jag har valt komprimissen att maximera förståelsen för de som kan det svenska språket framför alternativet att skriva på engelska och riskera att försvåra det för dig. Detta ställningstagande kommer att beröras längre ned i stycket "REF".
    </p>
</p>

## Ett kort stycke programmerarhistorik
<div>För att sätta en liten kontext till programmering så summerar jag en liten kort historik på ett par rader.</div>
    <p>
        Den första datorn som kunde programmeras med olika programkoder på liknande sätt som datorer fungerar idag konstruerades i slutet av 1940-talet, vilket var baserat på geniet Alan Turings teorier. Antalet programmerare på 40-talet skulle nog kunna räknas på ena handens fingrar. 2014 finns det estimat på runt 18 miljoner programmerare och att trenden har varit att vart femte år så har antalet professionella programmerare fördubblats. Detta innebär att hälften av alla professionella programmerare har mindre än fem års erfarenhet. Detta tror jag har bidragande orsak till programmerare har den status den har idag och är en bidragande orsak att vattenfallsmodellen (som var menat som ett <a href="https://en.wikipedia.org/wiki/Anti-pattern" target="_blank">anti-pattern</a> av Winston W. Royce som först beskrev modellen) började brukas på 80-talet. (Delvis summering av youtube-videon  <a href="https://youtu.be/ecIWPzGEbFc" target="_blank">"Uncle" Bob Martin - "The Future of Programming"</a>)
    </p>


## WORK IN PROGRESS: Avkodning av specifikationer/lösningsförlag till krav
### för att hitta bättre lösningar än lösningsförlagen
<p>
    Inkompletta specifikationer (har nog aldrig sett en - icke trivial - specifikation som varit komplett)  gör att man måste gissa sig till vad som ska vara mellan raderna. Och då behöver man förstå kraven för att kunna täcka hålen i specifikationerna. Exemplifiera med riktigt exempel och sedan referea till köpa blommor exempel?     
</p>

<p>Uppslag: <br/>
    Angåend disposition, jämför J.R.R Tolkiens Sagan om Ringen som börjar med 30 sidor torr historia om hoberna och släkthistorik för dessama. Snark! Jämför med logg-koden. Och dispostion av krav och kravstruktur</p>
