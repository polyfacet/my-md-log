# Git commits

What is it, how do I use it?

- Tänk igenom hur jag använder mig av git history/commits
  - Hitta information om bakgrund till varför något implementerats på ett visst sätt.
  - Få en överblick av en Release/(förändringar av andra) (Release Notes brukar hantera av Application Owner och har en annan målgrupp och är inte så "seriös"/omfattande )
  - Kopiera mina commit meddelande, för att föra in i "Jira conclusions" 
  - Se historien kring hur förändringar skett inom en fil: 
    - När någon bug introducerades
    - Generellt följa historiken, t.ex. att man velat kring en implemenation, eller haft andra svårigheter
    - Se hur man har implementerat något, så att jag kan göra likadant/på samma sätt
        Då en implemenation kan beröra många "komponenter" - speciellt då Aras, någon client method, server method, form, item type etc. (Ideal ska detta vara dokumenenterat men så är det sällan.)

## Detta borde leda fram till conventional commits likt

### Commit example

feature:(ECO) Adds Critical Part change validations

At state X, a compare of the changed parts and its previous and new contents are evaluated on how the change affects 'critical parts'

JIRA-123

