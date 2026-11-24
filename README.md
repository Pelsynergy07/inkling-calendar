# Inkling festival calendar

The festival dates the [Inkling](https://github.com/Pelsynergy07) app downloads about once a month,
so festivals that follow the moon (Diwali, Holi, Eid and the rest) stay right without an app
update. It's a plain public file: the app sends nothing about its user, it just reads this one.

The app reads `festivals.json` from
`https://raw.githubusercontent.com/Pelsynergy07/inkling-calendar/main/festivals.json`.

## Format

- `app` must be `"inkling-calendar"`, or the file is ignored.
- `festivals` maps each festival's name to its dates, ISO style (`2027-10-29`), one per year.
  Names: `SANKRANTI`, `LUNAR_NEW_YEAR`, `HOLI`, `EID_FITR`, `VAISAKHI`, `EID_ADHA`, `RAKHI`,
  `ONAM`, `JANMASHTAMI`, `GANESH`, `NAVRATRI`, `DUSSEHRA`, `DIWALI`, `GURPURAB`, `HANUKKAH`.
- A date here wins over the app's built-in one for the same year. Unknown names, bad dates and
  years outside 2020–2100 are skipped.
- New Year, Christmas and Easter are worked out in the app, so they aren't listed.
- Hanukkah is the evening of the first candle. Navratri is the first day of Sharad Navratri.

## Updating

Bump `updated` whenever you change it. Eid dates move a day either way once the moon is sighted,
so they're worth a check each year. Guru Nanak Jayanti is only listed through 2029 and Vaisakhi
through 2030 for now; add later years once they're confirmed.

Dates were checked against timeanddate.com, Hebcal and published Indian festival calendars.
