# WG Region Guard

NeoForge 1.21.1 мод — расширяет защиту WorldGuard регионов от обхода через модовые механики.

## Проблема

WorldGuard защищает регионы от игроков, но не от механик модов: машины Create, буры, сеятели Industrial Foregoing, снаряды Supplementaries и другие могут ломать/ставить блоки в защищённых зонах минуя проверки прав.

## Что блокирует

| Категория | Что именно |
|---|---|
| **Машины** | Block-break и block-place от не-игровых entity (Create, IF, …) |
| **Vein Mining** | Разрушение блоков в чужом регионе при добыче цепочкой |
| **Falling Tree** | Обрушение деревьев за пределы исходного региона |
| **Supplementaries** | Рогатка, говорящий блок и другие player interactions |
| **Create** | Deployer, пушки |
| **Industrial Foregoing** | Block Placer, Block Breaker |
| **Carry On** | Поднятие tile entity в защищённом регионе |
| **Mekanism** | Телепортация в защищённый регион |
| **L_Ender's Cataclysm** | Атаки боссов на защищённые блоки |
| **Immersive Aircraft** | Повреждения от летательных аппаратов |
| **Взрывы** | Любые модовые взрывы, затрагивающие защищённые блоки |

## Требования

- NeoForge 21.1.218 (Minecraft 1.21.1)
- WorldGuard (через Bukkit/Mohist bridge)
- Java 21

## Сборка

```bash
cd wg-region-guard
./gradlew build
# → build/libs/wgregionguard-*.jar
```

## Конфигурация

После первого запуска создаётся `wg-region-guard-server.toml`. Каждую категорию можно включить/выключить независимо:

```toml
[guard.machines]
blockMachineBreak = true
blockMachinePlace = true

[guard.playerEnhanced]
blockVeinMining = true
blockFallingTree = true

[guard.mods]
blockSupplementaries = true
blockCreateDeployer = true
# ...и т.д.
```

## Архитектура

```
RegionGuardMod.java          — точка входа, регистрация обработчиков
config/GuardConfig.java      — NeoForge ModConfigSpec (server.toml)
bridge/WorldGuardBridge.java — интеграция с WorldGuard API
handler/
  BlockBreakHandler.java     — машинный block-break, vein mining, falling tree
  PlayerActionHandler.java   — Carry On, Mekanism, взрывы, Supplementaries
  ProjectileHandler.java     — снаряды (Supplementaries, Immersive Aircraft)
```
