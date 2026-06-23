# 🏰 WG Region Guard

> NeoForge 1.21.1 мод — блокирует обход защиты WorldGuard регионов через механики модов.

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.1-brightgreen?logo=minecraft)
![NeoForge](https://img.shields.io/badge/NeoForge-21.1.x-orange)
![Java](https://img.shields.io/badge/Java-21-ED8B00?logo=openjdk&logoColor=white)
![Requires WorldGuard](https://img.shields.io/badge/requires-WorldGuard-blue)
![License](https://img.shields.io/badge/license-proprietary-red)

---

## 🗺️ Место в экосистеме

```
  Модовые механики (Create, Mekanism, Cataclysm...)
        │ пытаются сломать/поставить блок
        ▼
  wg-region-guard (NeoForge, сервер)
        │ проверяет WorldGuard флаги региона
        ▼
  ✅ разрешено (нет региона / у игрока права)
  ❌ заблокировано (защищённый регион)
```

**Проблема:** WorldGuard защищает регионы от игроков, но не от не-игровых механик модов. Машины Create, буры, сеятели, снаряды и боссы могут свободно разрушать и строить в защищённых зонах.

---

## ✨ Что блокируется

| Категория | Механика |
|---|---|
| **Create** | Deployer, пушки, механизмы block-place/break |
| **Industrial Foregoing** | Block Placer, Block Breaker |
| **Supplementaries** | Рогатка, говорящий блок, player interactions |
| **Carry On** | Поднятие tile entity в защищённом регионе |
| **Mekanism** | Телепортация в защищённый регион |
| **L_Ender's Cataclysm** | Атаки боссов на защищённые блоки |
| **Immersive Aircraft** | Повреждения от летательных аппаратов |
| **Vein Mining** | Цепная добыча за границами региона |
| **Falling Tree** | Обрушение дерева за пределы исходного региона |
| **Взрывы** | Любые модовые взрывы на защищённых блоках |
| **Не-игровые entity** | Любой block-break/place от не-player entity |

---

## 📋 Требования

| Компонент | Версия |
|---|---|
| Minecraft | 1.21.1 |
| NeoForge | 21.1.x |
| WorldGuard | через Bukkit/Mohist bridge |
| Java | 21 |

Требует Mohist или аналогичный гибридный сервер с поддержкой Bukkit API на NeoForge.

---

## 🚀 Сборка и установка

```bash
cd wg-region-guard
./gradlew jar
# → build/libs/wg-region-guard-*.jar
```

Скопировать jar в `mods/` сервера. Конфигурация не требуется — мод активен сразу.

---

## 🔗 Связанные репозитории

| Репо | Связь |
|---|---|
| [voidrp-gamesync-plugin](https://github.com/VOIDRP-MINECRAFT/voidrp-gamesync-plugin) | Управляет регионами наций через WorldGuard |
| [voidrp-async-ai](https://github.com/VOIDRP-MINECRAFT/voidrp-async-ai) | Параллельный performance-мод на сервере |

---

<div align="center">
<a href="https://void-rp.ru">🌐 Сайт</a> ·
<a href="https://github.com/VOIDRP-MINECRAFT">🏠 Организация</a>
</div>
