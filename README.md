<h1 align=center><code>Chat Cleaner</code></h1>

<div align=center>
  <img src=https://img.shields.io/badge/Counter--Strike%202-Metamod%202.0%20(KHook)-orange?style=flat-square alt=metamod>
  <a href=https://github.com/Cookies2122/cs2-chat_cleaner/commits><img src=https://img.shields.io/github/last-commit/Cookies2122/cs2-chat_cleaner?style=flat-square alt="last commit"></a>
  <a href=LICENSE><img src=https://img.shields.io/github/license/Cookies2122/cs2-chat_cleaner?style=flat-square alt=license></a>
</div>
<br>

Убирает из чата радио-команды, сообщения о наградах и деньгах и системные уведомления. Может писать свои сообщения о входе, выходе и смене команды.

> Автор плагина: [ABKAM](https://github.com/ABKAM2023). Здесь версия 1.0.1 под новый SDK и Metamod 2.0, оригинал: [ABKAM2023/cs2-chat_cleaner](https://github.com/ABKAM2023/cs2-chat_cleaner).

## Что нужно

- [Metamod:Source](https://github.com/alliedmodders/metamod-source) 2.0 (KHook)
- [Utils](https://github.com/Pisex/cs2-menus)

## Установка

Соберите плагин (раздел [Сборка](#сборка)) и скопируйте содержимое `build/package` в папку `csgo` на сервере. В пакете лежит:

| Файл | Куда |
| --- | --- |
| `chat_cleaner.so` | `addons/chat_cleaner/` |
| `chat_cleaner.vdf` | `addons/metamod/` |
| `settings.ini` | `addons/configs/chat_cleaner/` |
| `blocked_events.txt` | `addons/configs/chat_cleaner/` |
| `blocked_radio.txt` | `addons/configs/chat_cleaner/` |
| `blocked_text.txt` | `addons/configs/chat_cleaner/` |
| `chat_cleaner.phrases.txt` | `addons/translations/` |

После этого перезапустите сервер или смените карту.

## Настройки

### settings.ini

`addons/configs/chat_cleaner/settings.ini`

| Ключ | По умолчанию | Что делает |
| --- | --- | --- |
| `DebugMode` | `0` | показывать все сообщения в консоли, 1 включить |
| `CustomTeamMessages` | `1` | свои сообщения о смене команды, 1 включить |
| `CustomConnectMessages` | `1` | свои сообщения о входе, 1 включить |
| `CustomDisconnectMessages` | `1` | свои сообщения о выходе, 1 включить |

```
"GameManager"
{
	// Включить режим отладки (показывает все сообщения в консоли)
	"DebugMode"		"0"
	
	// Кастомные сообщения о смене команды (1 = включено, 0 = выключено)
	"CustomTeamMessages"	"1"
	
	// Кастомные сообщения о подключении игрока (1 = включено, 0 = выключено)
	"CustomConnectMessages"	"1"
	
	// Кастомные сообщения об отключении игрока (1 = включено, 0 = выключено)
	"CustomDisconnectMessages"	"1"
}
```

### blocked_events.txt

`addons/configs/chat_cleaner/blocked_events.txt`

Игровые события, которые не попадут в чат, по одному в строке.

```
// Блокируемые игровые события

player_radio
player_team
player_disconnect
player_connect
```

### blocked_radio.txt

`addons/configs/chat_cleaner/blocked_radio.txt`

Радио-сообщения, которые нужно убрать.

<details>
<summary>Весь файл blocked_radio.txt</summary>

```
// Блокируемые радио сообщения

SFUI_TitlesTXT_Fire_in_the_hole
SFUI_TitlesTXT_Flashbang_in_the_hole
SFUI_TitlesTXT_Smoke_in_the_hole
SFUI_TitlesTXT_Decoy_in_the_hole
SFUI_TitlesTXT_Molotov_in_the_hole
SFUI_TitlesTXT_Incendiary_in_the_hole
Cstrike_TitlesTXT_Cover_me
Cstrike_TitlesTXT_Regroup_team
Cstrike_TitlesTXT_You_take_the_point
Cstrike_TitlesTXT_Taking_fire
Cstrike_TitlesTXT_Team_fall_back
Cstrike_TitlesTXT_Stick_together_team
Cstrike_TitlesTXT_Storm_the_front
Cstrike_TitlesTXT_Follow_me
Cstrike_TitlesTXT_Hold_this_position
Cstrike_TitlesTXT_Go_go_go
Cstrike_TitlesTXT_Get_out_of_there
Cstrike_TitlesTXT_Go_A
Cstrike_TitlesTXT_Go_B
Cstrike_TitlesTXT_Report_in_team
Cstrike_TitlesTXT_Reporting_in
Cstrike_TitlesTXT_In_position
Cstrike_TitlesTXT_Sector_clear
Cstrike_TitlesTXT_Enemy_down
Cstrike_TitlesTXT_Enemy_spotted
Cstrike_TitlesTXT_Need_backup
Cstrike_TitlesTXT_Hostage_down
Cstrike_TitlesTXT_Got_Hostages
Cstrike_TitlesTXT_Defusing_Bomb
Cstrike_TitlesTXT_Planting_Bomb
Cstrike_TitlesTXT_Fire_in_the_hole
Cstrike_TitlesTXT_Roger_that
Cstrike_TitlesTXT_Negative
Cstrike_TitlesTXT_Affirmative
Cstrike_TitlesTXT_Cheer
Cstrike_TitlesTXT_Thanks
Cstrike_TitlesTXT_Compliment
Cstrike_TitlesTXT_Sorry
Cstrike_TitlesTXT_Need_Drop
Cstrike_TitlesTXT_Game_afk_bomb_drop
Cstrike_TitlesTXT_Game_get_out_of_there
```

</details>

### blocked_text.txt

`addons/configs/chat_cleaner/blocked_text.txt`

Текстовые сообщения игры, которые нужно убрать: награды, деньги, вход и выход и т.д.

<details>
<summary>Весь файл blocked_text.txt</summary>

```
// Блокируемые текстовые сообщения

Player_Cash_Award_Killed_VIP
Player_Cash_Award_Killed_Enemy_Generic
Player_Cash_Award_Killed_Enemy
Player_Cash_Award_Bomb_Planted
Player_Cash_Award_Bomb_Defused
Player_Cash_Award_Rescued_Hostage
Player_Cash_Award_Interact_Hostage
Player_Cash_Award_Respawn
Player_Cash_Award_Get_Killed
Player_Cash_Award_Kill_Teammate
Player_Cash_Award_Damage_Hostage
Player_Cash_Award_Kill_Hostage
Team_Cash_Award_T_Win_Bomb
Team_Cash_Award_Elim_Hostage
Team_Cash_Award_Elim_Bomb
Team_Cash_Award_Win_Time
Team_Cash_Award_Win_Defuse_Bomb
Team_Cash_Award_Win_Hostages_Rescue
Team_Cash_Award_Win_Hostage_Rescue
Team_Cash_Award_Loser_Bonus
Team_Cash_Award_Bonus_Shorthanded
Team_Cash_Award_Loser_Bonus_Neg
Team_Cash_Award_Loser_Zero
Team_Cash_Award_Rescued_Hostage
Team_Cash_Award_Hostage_Interaction
Team_Cash_Award_Hostage_Alive
Team_Cash_Award_Planted_Bomb_But_Defused
Team_Cash_Award_Survive_GuardianMode_Wave
Team_Cash_Award_CT_VIP_Escaped
Team_Cash_Award_T_VIP_Killed
Team_Cash_Award_no_income
Team_Cash_Award_no_income_suicide
Team_Cash_Award_Generic
Team_Cash_Award_Custom
Team_Cash_Award_Dead_Terrorists
Team_Cash_Award_Dead_CTs
Player_Cash_Award_ExplainSuicide_YouGotCash
Player_Cash_Award_ExplainSuicide_TeammateGotCash
Player_Cash_Award_ExplainSuicide_EnemyGotCash
Player_Cash_Award_ExplainSuicide_Spectators
Notice_Bonus_Shorthanded_Eligibility
Notice_Bonus_Shorthanded_Eligibility_Single
Notice_Bonus_Enemy_Team
Player_Team_Award_Bonus_Weapon
Player_Team_Award_Bonus_Weapon_Plural
Player_Team_Award_Picked_Up_Dogtag
Player_Team_Award_Picked_Up_Dogtag_Plural
Player_Team_Award_Picked_Up_Dogtag_Friendly
Cstrike_TitlesTXT_Game_connected
Cstrike_TitlesTXT_Game_disconnected
Cstrike_TitlesTXT_Game_join_ct
Cstrike_TitlesTXT_Game_join_ct_auto
Cstrike_TitlesTXT_Game_join_terrorist
Cstrike_TitlesTXT_Game_join_terrorist_auto
Cstrike_game_join_spectators
Cstrike_game_join_terrorist
Cstrike_game_join_ct
```

</details>

## Переводы

Файл `addons/translations/chat_cleaner.phrases.txt`, языки: ru, en, ua. Его можно править под себя.

<details>
<summary>Все фразы</summary>

```
"Phrases"
{
	"User_Connect"
	{
		"en"		"Player {GREEN}%s{DEFAULT} has joined the server"
		"ru"		"Игрок {GREEN}%s{DEFAULT} подключился к серверу"
		"ua"		"Гравець {GREEN}%s{DEFAULT} приєднався до сервера"
	}
	"User_Leave"
	{
		"en"		"Player {GREEN}%s{DEFAULT} has left the server"
		"ru"		"Игрок {GREEN}%s{DEFAULT} покинул сервер"
		"ua"		"Гравець {GREEN}%s{DEFAULT} покинув сервер"
	}
	"ChangeTeam_SPEC"
	{
		"en"		"Player {GREEN}%s{DEFAULT} joined {GRAY}Spectators"
		"ru"		"Игрок {GREEN}%s{DEFAULT} перешёл в {GRAY}Наблюдатели"
		"ua"		"Гравець {GREEN}%s{DEFAULT} перейшов до {GRAY}Спостерігачів"
	}
	"ChangeTeam_T"
	{
		"en"		"Player {GREEN}%s{DEFAULT} joined {OLIVE}Terrorists"
		"ru"		"Игрок {GREEN}%s{DEFAULT} перешёл в {OLIVE}Террористы"
		"ua"		"Гравець {GREEN}%s{DEFAULT} перейшов до {OLIVE}Терористів"
	}
	"ChangeTeam_CT"
	{
		"en"		"Player {GREEN}%s{DEFAULT} joined {BLUE}Counter-Terrorists"
		"ru"		"Игрок {GREEN}%s{DEFAULT} перешёл в {BLUE}Контр-Террористы"
		"ua"		"Гравець {GREEN}%s{DEFAULT} перейшов до {BLUE}Контр-Терористів"
	}
}
```

</details>

## Что изменено

По сравнению с оригиналом:

- Переведено на новый SDK ([Wend4r/sourcesdk](https://github.com/Wend4r/sourcesdk)), старый после обновления CS2 от 12.11.2026 уже не подходит.
- Работает только на Metamod 2.0 (KHook), старый Metamod на SourceHook больше не поддерживается.
- Заголовки Utils обновлены под текущую версию, имена интерфейсов теперь `UTILS_INTERFACE` и `MENUS_INTERFACE`.
- Своя функция `GameEntitySystem()` убрана, в новом SDK entity system берётся через `IGameResourceService`.
- SchemaEntity обновлена: актуальные оффсеты виртуальных функций.
- Хуки переписаны на KHook из Metamod 2.0, без прослоек под старый SourceHook.
- При выгрузке плагин проверяет, что Utils ещё загружен. Раньше `meta unload` после выгрузки Utils мог уронить сервер.
- Имя игрового события читается по-новому, в новом SDK метода `GetUnscopedName` нет. Сборка на старом SDK после обновления 12.11.2026 роняла сервер.

## Сборка

Собирается на Linux. Нужны clang, python3, cmake и [AMBuild](https://github.com/alliedmodders/ambuild). Все команды ниже выполняются из одной папки.

**1. SDK.** Нужен [sourcesdk](https://github.com/Wend4r/sourcesdk) не старее обновления CS2 от 12.11.2026. Собирается один раз:

```bash
git clone --recursive https://github.com/Wend4r/sourcesdk hl2sdk-cs2
cmake -S hl2sdk-cs2 -B hl2sdk-cs2/build -DCMAKE_BUILD_TYPE=Release -DCMAKE_C_COMPILER=clang -DCMAKE_CXX_COMPILER=clang++ -DSOURCESDK_AM_DEFINES=ON -DSOURCESDK_USE_MINIMAL_PROTOS=OFF
cmake --build hl2sdk-cs2/build -j$(nproc)
export HL2SDKCS2=$PWD/hl2sdk-cs2
```

**2. Metamod.** Нужен Metamod 2.0 с KHook, ветка `master`. Со старым Metamod на SourceHook сборка остановится с ошибкой.

```bash
git clone --recursive https://github.com/alliedmodders/metamod-source
```

**3. Плагин.** Папка SchemaEntity должна лежать рядом с папкой плагина.

```bash
git clone https://github.com/{o}/SchemaEntity
git clone https://github.com/Cookies2122/cs2-chat_cleaner
cd cs2-chat_cleaner
mkdir build && cd build
python3 ../configure.py --enable-optimize --sdks=cs2 --targets=x86_64 --mms_path=$PWD/../../metamod-source --hl2sdk-manifests=../hl2sdk-manifests
ambuild
```

Готовые файлы появятся в `build/package`.

## Автор

Плагин написал [ABKAM](https://github.com/ABKAM2023), оригинал: [ABKAM2023/cs2-chat_cleaner](https://github.com/ABKAM2023/cs2-chat_cleaner).
Перенос на новый SDK и Metamod 2.0, исправления: \_ded\_cookies.

## Лицензия

GPL-3.0, текст в файле [LICENSE](LICENSE). В коде плагина лицензия тоже указана как GPL. Авторские права на оригинальный код у ABKAM.
