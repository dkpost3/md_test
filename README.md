# # QA отчёт: .1 (Linux AUTO)

- Дата/время: **2025-12-19 16:50:57**
- Хост: **dkpost3-Cmp-NS483**
- ОС: **Linux Mint 22.2**
- Ядро: **6.14.0-37-generic**
- Raw log: `./qa_logs/qa_k1_1_linux_20251219_165047.log`

## Итог

- PASS: **7**
- FAIL: **2**
- SKIP: **2**

## Результаты по тестам

| ID | Статус | Тест | Ожидание | Факт | Примечание |
|---:|:------:|------|----------|------|------------|
| A-01 | PASS | Производитель (DMI Manufacturer) | Содержит: Aquarius | Aquarius |  |
| A-02 | PASS | Модель изделия (DMI Product Name) | Regex: .* | Cmp NS483 |  |
| A-03 | PASS | Модель в DMI (system-product-name) | Regex: .* | Cmp NS483 |  |
| A-04 | PASS | Серийный номер (DMI Serial Number) | Не пустой и не 'Not Specified' | 624063022992C-0071 | Сверить с наклейкой вручную |
| A-05 | PASS | Процессор (Model name) | Regex: .* | 11th Gen Intel(R) Core(TM) i5-1155G7 @ 2.50GHz  |  |
| A-06 | PASS | Количество логических CPU (CPU(s)) | >= 1 | 8 | Сверить P/E конфигурацию вручную по модели CPU |
| A-07 | PASS | Версия BIOS (строка) | Regex: .* | 	Version: AQNS483V2-1.4NFB.2 | Сверить с меню BIOS вручную |
| A-08 | INFO | ОЗУ (dmidecode -t memory) | Соответствует ТХ/конфигурации | см. raw log | Требует ручной интерпретации (объём/частоты/каналы) |
| A-09 | FAIL | PCIe (LnkCap) для 111 | Содержит: 16GT/s |  | 16GT/s ~ PCIe 4.0 |
| A-10 | FAIL | Secure Boot (mokutil) | SecureBoot enabled | SecureBoot disabled | Включить в BIOS, если по требованиям должен быть включён |
| A-11 | SKIP | Secure Boot (sbctl status) | sbctl установлен | — | sbctl не установлен |
| A-12 | SKIP | Secure Boot (bootctl status) | bootctl установлен | — | bootctl не установлен |
