# Muzelog interface copy from the design mock-ups

Design handoff, 2026-11-28 (see `HANDOFF.md`). This file lists the interface copy of the design canvas "Muzelog: UX audit, redesign and brand identity" (boards D01 to D05, S01 to S11, CompNav, CompStates, CompControls and Voice) next to the message catalogue in `apps/web/messages/nl.json` and `en.json` as it stood on `main` that day. It was extracted from the mock-ups with a script (text nodes, `aria-label`, `placeholder`, `alt`, `title`); every `existing` row was checked against `nl.json` for an exact match. It is input for the build, not a source file: the strings land in `apps/web/messages/` (A§15.2), and `check-i18n` holds them there. Where an EN cell says `to write`, the build writes the English.

Sample data is left out: museum names, places, review texts, member names and handles, scores, prices, counts, dates and the canvas annotations. Sentence patterns keep placeholders such as `{count}`, `{total}`, `{month}`, `{date}`, `{name}`; the brand appears as `{brand}`.

**Status.** `existing <key>`: nl.json has exactly this text. `changed <key>: was "<old>"`: the key clearly holds the same element with other words. `new`: no key holds it (a `cf` note names the nearest key). **EN.** From the English board (S11MuseumEN) or the Voice board when it gives the text, otherwise from en.json when the key exists (for a changed key that is the old English, marked), otherwise `to write`.

**Conventions.** Each string is listed once, under the first screen that uses it, and the Where column says "also on" for the others. The header, menu and footer strings are the exception: they appear on every board, so they are in the section "Header, menu and footer". The twelve province names are one row. The placeholder names (`{count}` and the like) were chosen for this file; the catalogue's names win where a key exists. In the app the brand is never written out: it comes from `MJK_BRAND_NAME` (CLAUDE.md).

**Uncertain rows.** Telling copy from sample data was not always clear: the badge names ("Tien musea", "Vijfentwintig", "Vijftig") may be a pattern ("{n} musea"); the milestone line "Vijfentwintig musea. Je kent de weg inmiddels." is only on the Voice board; the member home's "Lijst van {month}" and "van {total} provincies", the sort control's "Sorteer: {order}" and the photo credit "Foto: {maker} · {licence} · Wikimedia Commons" are patterns read from one sample each. The English board keeps some Dutch (an alt text, "€ 13,50" with a comma), and it differs from `en.json` on two buttons ("Add to my wishlist", "Show on the map"); both rows show both.

## Home

Boards: S01HomeVisitor, S01HomeMember, D01Home (the desktop board adds no copy). The review-card strings are listed here and are also used on the museum page, the review page and the profile.

| Where | NL | Status | EN |
|---|---|---|---|
| H1 (visitor) | Alle musea van Nederland in één paspoort | changed `home_heading`: was "Alle musea van Nederland" | Every museum in the Netherlands _(en.json, old wording)_ |
| Intro (visitor) | Vind een museum, kijk waar de Museumkaart geldig is en houd bij waar je bent geweest. Gratis, zonder advertenties. | changed `home_intro`: was "Zoek en ontdek de musea van Nederland op naam, plaats, provincie of thema." | Search and explore the museums of the Netherlands by name, place, province or theme. _(en.json, old wording)_ |
| Search field label / placeholder (also on No results, Not found) | Zoek een museum of plaats | changed `field_q`: was "Zoekterm" | Search term _(en.json, old wording)_ |
| Search button (also on No results, Not found) | Zoek | changed `action_search`: was "Zoeken" | Search _(en.json, old wording)_ |
| Button "near me" (visitor) | Bij mij in de buurt | changed `near_button`: was "Musea bij mij in de buurt" | Museums near me _(en.json, old wording)_ |
| Link "on the map" (visitor) | Op de kaart | changed `home_map`: was "Musea op de kaart" | Museums on the map _(en.json, old wording)_ |
| Heading of the passport preview (visitor) | Zo ziet een paspoort eruit | new | to write |
| Text under the passport preview (visitor) | Log je bezoeken, zie hoe ver je bent met de Museumkaart en verzamel een stempel per museum. | new | to write |
| Beta notice (also on Sign-in, Sign-up, Empty and error states; Voice board) | {brand} is in bèta. Een account maken kan nu alleen met een uitnodiging. | new (brand as `{brand}`) | {brand} is in beta. For now you need an invitation to make an account. |
| Link under the preview (visitor) | Hoe werkt het paspoort? | new | to write |
| Section heading, recent reviews (visitor) | Recente reviews | new | to write |
| Review card: visit line (also on Museum page, Reviews, Profile) | Bezocht in {month} | new (cf `review_visited_on` "Bezocht op {date}") | Visited in {month} |
| Review card: stars (also on Museum page, Reviews, Profile; the review form uses `review_form_stars`) | {rating} van 5 | existing `score_stars` | {rating} out of 5 |
| Review card: aspect label (also on Museum page, Reviews, Profile) | Collectie | existing `score_aspect_collection` | Collection |
| Review card: aspect label | Presentatie | existing `score_aspect_presentation` | Presentation |
| Review card: aspect label | Prijs-kwaliteit | existing `score_aspect_value_for_money` | Value for money |
| Review card: helpful count (also on Museum page, Reviews, Profile) | Nuttig · {count} | new | Helpful · {count} |
| Review card: reply link (also on Museum page, Reviews, Profile) | Reageer | new | Reply |
| Review card: report link (also on Museum page, Reviews, Profile) | Meld | new | Report |
| Link under the recent reviews (visitor) | Meer reviews | new | to write |
| Section heading, provinces (visitor) | Musea per provincie | existing `home_provinces` | Museums by province |
| The 12 province names in the list (visitor; `province_*`, also on Passport, Museum page) | Drenthe | existing `province_drenthe` (and the other 11 `province_*` keys, texts checked) | Drenthe |
| Greeting (member) | Hallo {name} | new | to write |
| Progress: label after the count (member; also on Passport, Profile, Empty passport) | van {total} musea met Museumkaart | new | to write |
| Progress: list caption (member; also on Passport, Profile, Empty passport) | Lijst van {month} | new (cf `profile_progress_of_list` "{visited} van {n} · lijst {date}") | to write |
| Progress figure label (member; also on Passport, Profile) | ooit bezocht | changed `profile_progress_all_time`: was "Ooit bezocht: {n}" | Ever visited: {n} _(en.json, old wording)_ |
| Progress figure label (member; also on Passport, Profile) | dit jaar | changed `profile_progress_year`: was "{year}: {n}" | {year}: {n} _(en.json, old wording)_ |
| Progress figure label (member; also on Passport, Profile) | van {total} provincies | new (cf `profile_progress_province`) | to write |
| Link (member) | Naar je paspoort | existing `welcome_to_passport` | Go to your passport |
| Heading, last stamps (member; also on Passport, Profile) | Laatste stempels | new | to write |
| Heading, next on the wishlist (member) | Hierna op je verlanglijst | new | to write |
| Museum card: Museumkaart status (also on Museum list, Museum page, Map, Wishlist, Header) | Museumkaart geldig | existing `mk_participating` | Museumkaart valid |
| Museum card: rating line (also on Museum list, Map, Wishlist) | van 5 · {count} | new (the mean is shown large in front; cf `score_mean`, `score_count_other`) | to write |
| Wishlist toggle, accessible name (also on Museum list, Map, Wishlist) | Verlanglijst: {name} | existing `marks_wishlist_for` | Wishlist: {name} |
| Link (member) | Hele verlanglijst ({count}) | new | to write |
| Section heading (member) | Musea bij mij in de buurt | existing `near_heading` | Museums near me |

## Museum list and filters

Boards: S02List, S02ListFilters, D02List (the desktop board adds the heading "Filters" and the button text with 226).

| Where | NL | Status | EN |
|---|---|---|---|
| H1 (also on No results) | Musea | existing `page_museums` | Museums |
| Filters button on a phone | Filters · {count} | new (cf `action_filter` "Filteren") | to write |
| Heading of the filter column (desktop) | Filters | new | to write |
| Removable filter chip, accessible name (also on Controls) | {filter}: filter verwijderen | new | to write |
| Result count (also on Map, No results, Controls) | {count} musea | changed `list_total`: was "Aantal musea: {count}" | Number of museums: {count} _(en.json, old wording)_ |
| Sort control (also on Map, Controls) | Sorteer: {order} | new (only the value "aanbevolen" is shown; the other options are not on the boards) | to write |
| Search field in the filter panel (also on Controls) | Zoek op naam of plaats | new | to write |
| Filter label (also on Controls) | Provincie | existing `field_province` | Province |
| Filter label (also on Controls) | Categorie | existing `field_category` | Category |
| Option "all" (also on Controls) | Alle | existing `option_all` | All |
| Filter label (also on Controls) | Minimale beoordeling | changed `score_filter_min`: was "Minimale beoordeling (sterren)" | Minimum rating (stars) _(en.json, old wording)_ |
| Checkbox (also on Controls) | Alleen waar de Museumkaart geldig is | changed `field_mk`: was "Alleen musea waar de Museumkaart geldig is" | Only museums where the Museumkaart is valid _(en.json, old wording)_ |
| Checkbox (also on Controls) | Kindvriendelijk (4 of hoger) | existing `score_filter_kid` | Kid-friendly (4 or higher) |
| Button in the filter panel (also on Controls) | Toon {count} musea | new | to write |
| Clear link (also on Controls) | Wis alles | new | to write |
| Photo placeholder, alt text (also on Map) | Foto | new | to write |
| Card: place line | {place} · {province} | new | to write |
| Card: no place | Plaats niet bekend | new | to write |
| Card: Museumkaart unknown (also on Wishlist, Museum page) | Museumkaart onbekend | existing `mk_unknown` | Museumkaart unknown |
| Card: closure line (also on Museum page) | Tijdelijk gesloten tot {date} | existing `museum_temp_closed_until` | Temporarily closed until {date} |
| Pager: navigation, accessible name (also on Map, Reviews, Controls) | Pagina’s | new | to write |
| Pager: previous (also on Map, Reviews, Controls) | Vorige | new | to write |
| Pager: next (also on Map, Reviews, Controls) | Volgende | changed `pager_next`: was "Volgende pagina" | Next page _(en.json, old wording)_ |
| Pager: position (also on Map, Reviews, Controls) | {from}–{to} van {total} | new | to write |

## Museum page

Boards: S03Museum, S11MuseumEN (English board), S07ReviewPrompt (the same page after a visit), D03Museum.

| Where | NL | Status | EN |
|---|---|---|---|
| Photo credit, image name (also on Reviews and review form) | Foto van Wikimedia Commons | new | (kept in Dutch on the English board) |
| Photo credit line (also on Reviews and review form) | Foto: {maker} · {licence} · Wikimedia Commons | new | Photo: {maker} · {licence} · Wikimedia Commons |
| Status line: list date | lijst {date} | existing `mk_list_date` | list {date} |
| Badge | Geregistreerd museum | existing `museum_registered` | Registered museum |
| Button: log a visit (also on Wishlist) | Ik ben hier geweest | new | I have been here |
| Button: wishlist | Op mijn verlanglijst | existing `filter_wishlist` (HANDOFF: "Op mijn verlanglijst") | Add to my wishlist _(English board; en.json `filter_wishlist` says "On my wishlist")_ |
| Closure notice (the notice ends with a full stop) | Tijdelijk gesloten tot {date} | existing `museum_temp_closed_until` | Temporarily closed until {date}. _(English board)_ |
| Longer text for an unknown card status | Museumkaart onbekend: we hebben dit museum nog niet nagekeken. | new (Voice board; cf `mk_unknown`) | Museumkaart unknown: we have not checked this museum yet. |
| Section heading | Praktisch | new | Practical |
| Fact label | Adres | existing `fact_address` | Address |
| Fact label: admission | Entree volwassene | new (cf `settings_card_adult` "Volwassene") | Adult admission |
| Admission: check date | nagekeken {date} | new | checked {date} |
| Fact label (also on Museum list filters) | Categorie | existing `fact_categories` | Category |
| Fact label | Website | existing `fact_website` | Website |
| Link | Bekijk op de kaart | existing `museum_on_map` | Show on the map _(English board; en.json says "View on the map")_ |
| Section heading (also on Reviews) | Beoordelingen | existing `score_h` | Ratings |
| Score line | {mean} van 5 · {count} beoordelingen | new (cf `score_mean`, `score_count_other`) | {mean} out of 5 · {count} ratings |
| Aspect label | Kindvriendelijk | existing `score_aspect_kid_friendly` | Kid-friendly |
| Aspect label | Toegankelijkheid | existing `score_aspect_accessibility` | Accessibility |
| Aspect label | Voorzieningen | existing `score_aspect_facilities` | Facilities |
| Aspect value when there are too few ratings | te weinig beoordelingen | existing `score_few` | too few ratings |
| Link to all reviews | Lees de {count} reviews | changed `review_read`: was "Lees de reviews ({count})" | Read the {count} reviews _(English board)_ |
| Section heading (also on Profile as `review_profile_h`) | Reviews | existing `review_list_h` | Reviews |
| Link under the two reviews | Lees alle {count} reviews | changed `review_all_of`: was "Alle reviews van dit museum" | Read all {count} reviews _(English board)_ |
| Section heading, remaining facts | Meer gegevens | changed `museum_facts`: was "Gegevens" | More details _(English board)_ |
| Fact label | Gemeente | existing `fact_municipality` | Municipality |
| Fact label | Provincie | existing `fact_province` | Province |
| Fact label | Pagina op museum.nl | existing `fact_museumnl` | Page on museum.nl |
| Value when unknown | niet bekend in de open bronnen | existing `fact_unknown` | not known in the open sources |

## Map

Boards: S04Map, D04Map.

| Where | NL | Status | EN |
|---|---|---|---|
| H1 (also in the menu) | Kaart | existing `page_map` | Map |
| Zoom button, accessible name | Inzoomen | existing `map_zoom_in` | Zoom in |
| Locate-me control, accessible name | Musea bij mij in de buurt | existing `near_button` | Museums near me |
| Close button of the selected-museum card, accessible name | Sluiten | existing `map_card_close` | Close |
| Button of the selected-museum card | Bekijk het museum | existing `map_card_view` | View the museum |
| Legend, accessible name | Legenda | new | to write |
| Legend item (marker with the card) | Museumkaart | new | to write |
| Legend item | Ander museum | new | to write |
| Legend item (also on Passport) | Bezocht | existing `marks_visited` | Visited |
| Legend item (also the wishlist everywhere else) | Verlanglijst | existing `marks_wishlist` | Wishlist |
| Legend item: cluster disc | Groep musea | new | to write |
| Near-me result line | {count} musea dichtbij, de dichtstbijzijnde eerst | changed `near_found`: was "Musea dichtbij, de dichtstbijzijnde eerst: {count}" | Museums nearby, the closest first: {count} _(en.json, old wording)_ |
| Distance in the near-me list | {km} km | new | to write |
| Heading of the list under the map | Dezelfde musea als lijst | existing `map_list_heading` | The same museums as a list |

## Passport

Boards: S05Passport, D05Passport. The progress block (count, list caption, three figures) and "Laatste stempels" are listed under Home.

| Where | NL | Status | EN |
|---|---|---|---|
| H1 | Paspoort | existing `page_passport` | Passport |
| Province grid heading | Per provincie | new | to write |
| Province bar: figure | / {total} | new | to write |
| Link under the stamps | Alle {count} bezoeken | new | to write |
| Section heading, badges (also on Profile) | Badges | new | to write |
| Badge name (milestone) | Tien musea | new (uncertain: a pattern like "{n} musea"? only 10, 25 and 50 are shown) | to write |
| Badge name (milestone) | Vijfentwintig | new | to write |
| Badge name (milestone) | Vijftig | new | to write |
| Badge name (province completed) | Heel {province} | new | to write |
| Badge state: earned | behaald | new | to write |
| Badge state: still to go | nog {count} | new | to write |
| Section heading of the saving (the board prefixes the year) | Bespaard | existing `passport_saved` | Saved |
| Saving card title | {year} · Bespaard met de kaart | changed `passport_h_savings`: was "Bespaard met de kaart" | Saved with the card _(en.json, old wording)_ |
| Caption under the net figure | netto | changed `passport_net`: was "Netto" | Net _(en.json, old wording)_ |
| Breakdown line: admissions | Entree bij {count} musea | new | to write |
| Breakdown line: card price | Prijs van de Museumkaart | changed `passport_card_price`: was "Prijs van de kaart" | Card price _(en.json, old wording)_ |
| Breakdown line: result | Netto bespaard | new (cf `passport_net`) | to write |
| Estimate note | Een schatting: we rekenen voor iedereen met de volwassenenprijs. Alleen jij ziet dit, tot je het zelf deelt. | changed `passport_savings_note`: was "Een schatting per kalenderjaar: voor iedereen rekenen we met de volwassenenprijs van het museum." | An estimate per calendar year: we use each museum's adult price for everyone. _(en.json, old wording)_ |
| Saving still negative (Voice board, CompStates) | Nog € {amount} en de kaart heeft zichzelf terugverdiend. | new | € {amount} to go and the card has paid for itself. |
| Milestone message (Voice board; uncertain whether it is UI or an example) | Vijfentwintig musea. Je kent de weg inmiddels. | new | Twenty-five museums. You know your way around by now. |
| Section heading | Mijn bezoeken | existing `passport_h_visits` | My visits |
| Edit button of a visit, accessible name | {name}: bezoek wijzigen | new | to write |
| Date fallback in a visit or stamp (also on Home, Profile) | Datum onbekend | existing `passport_date_unknown` | Date unknown |
| Button | Meer tonen | existing `passport_more` | Show more |
| Link | Bezoeken toevoegen of importeren | changed `passport_link_onboarding`: was "Bezochte musea toevoegen of importeren" | Add visited museums or import a file _(en.json, old wording; HANDOFF §2 gives the new Dutch)_ |
| Link | Mijn gegevens downloaden | existing `export_h` | Download my data |

## Wishlist

Board: S06Wishlist.

| Where | NL | Status | EN |
|---|---|---|---|
| H1 (also in the menu) | Verlanglijst | existing `page_wishlist` | Wishlist |
| Intro line | {count} musea waar je nog heen wilt. | new | to write |
| Link to the map | Verlanglijst op de kaart | new | to write |

## Reviews and review form

Boards: S07Reviews, S07ReviewForm, S07ReviewPrompt. The review-card strings are listed under Home; the photo credit under Museum page.

| Where | NL | Status | EN |
|---|---|---|---|
| H1 of the reviews page | Reviews van {name} | existing `review_head_title` | Reviews of {name} |
| Form heading | Beoordeel {name} | existing `review_form_h` | Review {name} |
| Field label | Welk bezoek? | existing `review_form_visit` | Which visit? |
| Hint under the visit field | “Bezocht in {month}” staat bij je beoordeling en is openbaar. | changed `review_form_public_date`: was "Bezocht op {date} staat bij je beoordeling en is openbaar." | Visited on {date} shows with your review and is public. _(en.json, old wording)_ |
| Group label | Algemene beoordeling (verplicht) | existing `review_form_rating` | Overall rating (required) |
| Star option label (the form uses `review_form_stars`) | {n} van 5 | existing `review_form_stars` | {n} of 5 |
| Disclosure summary | Meer onderdelen (optioneel) | changed `review_form_aspects_h`: was "Onderdelen (optioneel)" | Aspects (optional) _(en.json, old wording)_ |
| Aspect value "none" | geen | existing `review_form_none` | none |
| Text under the disclosure summary | Vier onderdelen meer: presentatie, toegankelijkheid, voorzieningen, prijs-kwaliteit. | new | to write |
| Field label | Je beoordeling in woorden (optioneel) | existing `review_form_body` | Your review in words (optional) |
| Hint under the text field | Maximaal 5.000 tekens. | new | to write |
| Submit button | Beoordeling opslaan | new (cf `action_save`) | to write |
| Cancel button (also on Controls) | Annuleren | existing `action_cancel` | Cancel |
| Panel heading after a visit is saved (also a success notice; Voice board) | Bezoek opgeslagen. Weer eentje erbij. | changed `marks_visit_saved`: was "Bezoek gelogd." | Visit saved. One more for the book. _(Voice board)_ |
| Panel: date line | Vandaag, {date} | new | to write |
| Panel: primary button | Geef een beoordeling | new | to write |
| Panel: link | Datum of notitie aanpassen | new | to write |
| Panel: dismiss button | Niet nu | new | to write |

## Sign-in and sign-up

Boards: S08SignIn, S08SignUp. The beta notice is listed under Home.

| Where | NL | Status | EN |
|---|---|---|---|
| H1, sign-in (also in the menu and the back link of sign-up) | Inloggen | existing `page_signin` | Sign in |
| Passkey button | Inloggen met een passkey | existing `action_signin_passkey` | Sign in with a passkey |
| Divider | of met je e-mailadres | new | to write |
| Field label (also on Sign-up) | E-mailadres | existing `field_email` | Email address |
| Hint under the email field | We sturen een code van 6 cijfers. Een wachtwoord is niet nodig. | changed `auth_code_intro`: was "We sturen een code van 6 cijfers naar je e-mailadres. Zo hoef je geen wachtwoord te onthouden." | We send a 6-digit code to your email address, so you do not need to remember a password. _(en.json, old wording)_ |
| Button | Stuur een code | existing `action_send_code` | Send a code |
| Link that reveals the password field | Gebruik een wachtwoord | new (cf `auth_password_heading`) | to write |
| Heading of the second card | Uitnodiging ontvangen? | new | to write |
| Button of the second card | Account maken met een uitnodiging | existing `auth_signup_heading` | Create an account with an invite |
| H1, sign-up | Account maken | changed `auth_signup_heading`: was "Account maken met een uitnodiging" | Create an account with an invite _(en.json, old wording)_ |
| Field label | Uitnodigingscode | existing `field_invite` | Invite code |
| Hint | 16 tekens. Hoofdletters en streepjes maken niet uit. | changed `field_hint_invite`: was "16 tekens. Hoofdletters, kleine letters en streepjes maken niet uit." | 16 characters. Capitals, lower case and hyphens do not matter. _(en.json, old wording)_ |
| Field label | Gebruikersnaam | existing `field_handle` | Username |
| Hint (Controls shows the shorter "3 tot 30 tekens: kleine letters, cijfers en _.") | 3 tot 30 tekens: kleine letters, cijfers en _. Dit is je openbare naam. | changed `field_hint_handle`: was "3 tot 30 tekens: kleine letters, cijfers en een underscore (_). Dit is je openbare naam." | 3 to 30 characters: lower-case letters, digits and an underscore (_). This is your public name. _(en.json, old wording)_ |
| Field label | Weergavenaam | existing `field_display_name` | Display name |
| Hint | Hoogstens 50 tekens. Anderen zien deze naam. | existing `field_hint_display_name` | At most 50 characters. Others see this name. |
| Checkbox | Ik ben 16 jaar of ouder | existing `auth_age` | I am 16 or older |
| Checkbox (one string; the key holds the part before the link) | Ik ga akkoord met de voorwaarden | changed `auth_terms_agree`: was "Ik ga akkoord met de" | I agree to the _(en.json, old wording)_ |
| Note above the button (the key holds the part before the link) | Lees ook onze privacyverklaring: geen trackers, geen advertenties. | changed `auth_privacy_lead`: was "Lees ook onze" | Please also read our _(en.json, old wording)_ |
| Submit button | Account maken | existing `action_signup` | Create account |
| Link | Ik heb al een account | existing `auth_have_account` | I already have an account |

## Profile

Board: S09Profile. Progress block, badges and last stamps are listed under Home and Passport; the review card under Home.

| Where | NL | Status | EN |
|---|---|---|---|
| Line under the name | Lid sinds {month} | existing `profile_member_since` (the board prefixes "@{handle} · ") | Member since {month} |
| Section heading | Bezochte musea | existing `profile_visits_h` | Museums visited |

## Empty and error states

Boards: S10EmptyPassport, S10Error, S10NoResults, S10NotFound, CompStates, Voice. The beta notice is under Home, the closure notice under Museum page, "Bezoek opgeslagen" under Reviews.

| Where | NL | Status | EN |
|---|---|---|---|
| Empty passport: heading | Nog geen stempels | new | No stamps yet. _(Voice board, with the next line)_ |
| Empty passport: text | Waar ben je al geweest? Vink je musea aan en je paspoort vult zich. | new | Where have you been? _(Voice board; only the first sentence)_ |
| Empty passport: button | Musea aanvinken | new | to write |
| Empty passport: link | Of importeer een lijst (CSV) | new | to write |
| Empty wishlist (Voice board) | Je verlanglijst is leeg. Waar wil je nog heen? | changed `wishlist_empty`: was "Je verlanglijst is leeg." | Your wishlist is empty. Where to next? _(Voice board)_ |
| 404: heading | Deze zaal bestaat niet (meer) | changed `page_not_found`: was "Pagina niet gevonden" | This room does not exist (any more). _(Voice board)_ |
| 404: text | Zoek een museum of ga terug naar het begin. | changed `not_found_body`: was "Deze pagina bestaat niet (meer)." | Search for a museum or go back to the start. _(Voice board)_ |
| Link to the home page (404, error) | Naar het begin | changed `back_home`: was "Naar de homepage" | Back to the home page _(en.json, old wording)_ |
| Error page heading | Er ging iets mis | existing `page_error` | Something went wrong |
| Error page text | Dat lukte niet. De pagina kon niet worden geladen. | changed `error_body`: was "Er ging iets mis: herlaad de pagina." | Something went wrong: reload the page. _(en.json, old wording)_ |
| Retry button | Opnieuw proberen | existing `auth_retry` | Try again |
| Plain error notice (Voice board, CompStates) | Dat lukte niet. Probeer het later opnieuw. | existing `marks_failed` | That did not work. Please try again later. |
| No results: heading | Niets gevonden voor “{q}” | changed `list_empty`: was "Geen musea gevonden. Pas de filters of de zoekterm aan." | No museums found. Change the filters or the search term. _(en.json, old wording)_ |
| No results: hint | Controleer de spelling, of zoek op een plaats. | new | to write |
| No results: button | Alle musea bekijken | new (cf `home_all_museums` "Alle musea") | to write |
| Loading state (CompStates) | Laden… | existing `loading` | Loading… |

## Header, menu and footer

Boards: CompNav and the chrome of every screen. These strings appear on every board, so they are listed here and not under Home.

| Where | NL | Status | EN |
|---|---|---|---|
| Logo, accessible name | {brand} | new (from the configured brand name, never hard-coded) | to write |
| Search button, accessible name (also on Controls) | Zoeken | existing `page_search` | Search _(English board)_ |
| Menu button, accessible name | Menu | new | Menu _(English board)_ |
| Close button of the open menu, accessible name | Menu sluiten | new | to write |
| Menu panel, accessible name | Hoofdmenu | existing `nav_main` | Main menu |
| Menu item (also the H1 of the list) | Musea | existing `page_museums` | Museums |
| Menu item | Kaart | existing `page_map` | Map |
| Menu item | Paspoort | existing `page_passport` | Passport |
| Menu item | Verlanglijst | existing `page_wishlist` | Wishlist |
| Menu item (visitor; also the H1 of Sign-in) | Inloggen | existing `page_signin` | Sign in |
| Menu item (member) | Mijn account | changed `nav_account`: was "Account" | Account _(en.json, old wording)_ |
| Language link | English | existing `lang_switch` | Nederlands _(English board; en.json value)_ |
| Footer promise | Geen advertenties, geen trackers | new | No ads, no trackers |
| Footer promise | Gratis, en dat blijft zo | new | Free, and it stays that way |
| Footer promise | Een onafhankelijk hobbyproject | new | An independent hobby project |
| Footer line | Niet verbonden aan de Museumvereniging of de Museumkaart. | existing `footer_not_affiliated` | Not affiliated with the Museumvereniging or the Museumkaart. |
| Footer line | Museuminformatie zonder garantie. | existing `footer_disclaimer` | Museum information without guarantee. |
| Footer navigation, accessible name | Over deze site | existing `nav_footer` | About this site |
| Footer link | Over {brand} | new (new page "Over", HANDOFF §4) | About {brand} _(English board)_ |
| Footer link | Contact | existing `page_contact` | Contact |
| Footer link | Privacy | existing `page_privacy` | Privacy |
| Footer link | Voorwaarden | existing `page_terms` | Terms |
| Footer link | Hoe wij reviews controleren | existing `page_reviews` | How we check reviews |

## Controls

Board: CompControls. Most strings are listed under the screens that use them (filters and pager under Museum list and filters). Only what appears first here is listed.

| Where | NL | Status | EN |
|---|---|---|---|
| Button | Bezoek opslaan | existing `marks_visit_submit` | Save visit |
| Button | Verwijderen | existing `passport_delete` (`wishlist_remove` and `action_remove` hold the same text) | Delete |
| Button (primary) | Opslaan | existing `action_save` | Save |
| Toggle text (also the H1 of the wishlist) | Verlanglijst | existing `marks_wishlist` | Wishlist |
| Error under a field | Vul een geldig e-mailadres in. | existing `auth_err_field_email` | Enter a valid email address. |

## Totals

Rows: 217 · existing 96 · changed 37 · new 84. The province row counts once (twelve strings).
