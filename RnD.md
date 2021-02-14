# TODO

## Useful info

- In Torghast? 
  ```lua
  C_Map.GetMapInfo(C_Map.GetBestMapForUnit("player")).name == "Torghast"
  ```

## Items to Track

- Anima Powers
  ```lua
  local name, icon, count, _, _, _, _, _, _, spellID = UnitAura("player", INDEX, "MAW")
  local desc = GetSpellDescription(spellID)
  ```
- Anima gained
  - EVENT: "PLAYER_CHOICE_UPDATE"
- Chests Opened
  - TODO
- Phantasma gained
  - ItemID: 1728?
  - EVENT: "CURRENCY_DISPLAY_UPDATE"
- Mawrats killed
  - EVENT: "COMBAT_LOG_EVENT_UNFILTERED" - SUBEVENT: "UNIT_DIED" (Name="Mawrat")
- Rares killed
  - TODO
- Jars broken
  - EVENT: "COMBAT_LOG_EVENT_UNFILTERED" - SUBEVENT: "SPELL_AURA_REMOVED" (Name="Ashen Phylactery")
- Soul Remnant's Blessing
  ```lua
  local name, icon, count, _, _, _, _, _, _, spellID = AuraUtil.FindAuraByName("Soul Remnant's Blessing", "player")
  ```
- Deaths
  - EVENT: "PLAYER_DEAD"
- DETAILS! APIs (For combat related things)
  - https://www.curseforge.com/wow/addons/details/pages/api-combat-containers-actors
    - Damage Done
    - Healed
    - Taken
    - Biggest Hit
- Clear Time (Timer) (Store all clears)
  - EVENT: "PLAYER_ENTERING_WORLD"
- Time per Floor
- Best Time 
  - Top clear time
- Total Clears
- Best Streak?
- Class / Spec
  - Class
    ```lua
    local name, realm = UnitName("player")
    local localizedClass, englishClass, classIndex = UnitClass("player")
    ```
  - Spec
    ```lua
    local id, name, description, icon, role, primaryStat = GetSpecializationInfo(GetSpecialization())
    ```
- iLvL
    ```lua
    local overall, equipped = GetAverageItemLevel()
    ```
- Talents
  - Talent Info
    ```lua
    for talentTier = 1, MAX_TALENT_TIERS do
            for talentNum = 1, 3 do
                local talentID, name, texture, selected, available, spellID, unknown, row, column, known, grantedByAura = GetTalentInfo(talentTier, talentNum, 1)
                if (selected) then
                    return etc etc etc
                end
            end
        end
    ```
- Solo/Party (# in party)
  ```lua
  local members = GetNumGroupMembers()
  ```
- Zone / Layer
  ```lua
  TODO
  ```
- Final Boss (Perhaps grab from Details API)
  ```lua
  TODO
  ```
