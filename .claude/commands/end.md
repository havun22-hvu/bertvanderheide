# End Session Command

Voer de volgende stappen uit om de sessie netjes af te ronden:

## 1. Update MD bestanden
- Update CLAUDE.md met relevante wijzigingen uit deze sessie
- Check of andere docs bijgewerkt moeten worden

## 2. Git commit & push
- `git add .`
- Maak een duidelijke commit message met samenvatting van de wijzigingen
- `git push origin master`

## 3. Branch cleanup
- Check op open branches: `git branch -a`
- Verwijder gemergte lokale branches: `git branch --merged | grep -v master | xargs git branch -d`
- Check open pull requests: `gh pr list`
- Sluit/merge open PRs indien gereed

## 4. Bevestig aan gebruiker
- Geef korte samenvatting van wat er gedaan is
- Vermeld eventuele openstaande items
