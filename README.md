# Treeniloki 🏋️

AI-avusteinen treenipäiväkirja (PWA). Toimii selaimessa ja asentuu puhelimen kotinäytölle, toimii myös offline.

## Ominaisuudet

- Treenin suunnittelu: 90 liikkeen suomenkielinen liikepankki haulla ja ryhmäsuodattimilla
- Kirjaus salilla isoilla ±-napeilla, arvot esitäytettyinä — kesken jäänyt treeni säilyy muistissa
- Progressioehdotukset double progression -mallilla (tavoite täyttyi → +2,5 kg; vajaaksi jäi → samat painot; 3× vajaa → -10 %)
- Treenigeneraattori: 1 raskas moninivelinen pääliike + apu-/eristävät liikkeet tavoitteen (lihaskasvu, voima, peruskunto, lihaskestävyys, toiminnallinen) mukaan
- Viikkobalanssi: työntävät/vetävät/jalat/keskivartalo-sarjojen tasapainovaroitukset
- Kehityskäyrät liikekohtaisesti: max paino, arvioitu 1RM (Epley), volyymi
- Valinnainen AI-brief treenin jälkeen (oma Anthropic API-avain asetuksissa)
- Profiilit (usea käyttäjä samalla laitteella), tumma/vaalea teema, JSON-varmuuskopio

## Julkaisu GitHub Pagesiin

1. Luo uusi julkinen repo (esim. `treeniloki`)
2. Lataa repoon kaikki tämän paketin tiedostot juureen:
   `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`,
   `icon-512-maskable.png`, `apple-touch-icon.png`, `README.md`
3. Settings → Pages → Source: **Deploy from a branch**, Branch: **main**, kansio **/ (root)** → Save
4. Sovellus löytyy hetken päästä osoitteesta `https://<käyttäjä>.github.io/treeniloki/`

## Asennus kotinäytölle

- **Android/Chrome:** valikko ⋮ → *Lisää aloitusnäyttöön* / *Asenna sovellus*
- **iPhone/Safari:** Jaa-nappi → *Lisää Koti-valikkoon*

## Päivittäminen

Kun päivität `index.html`-tiedostoa, **nosta versionumeroa** tiedostossa `sw.js`
(rivi `const CACHE = "treeniloki-v1"` → `-v2` jne.), muuten selaimet tarjoavat
vanhaa välimuistiversiota.

## Tietojen tallennus

Kaikki data tallentuu selaimen localStorageen laitekohtaisesti — mitään ei
lähetetä palvelimelle. Ota säännöllisesti JSON-varmuuskopio asetuksista;
sillä myös siirrät historian laitteelta toiselle. AI-briefin API-avain
tallentuu vain omaan selaimeen (kutsu menee suoraan Anthropicin
rajapintaan selaimesta).
