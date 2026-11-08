# Гатчина: индикаторы кварталов

## Что это

Одностраничный дашборд по 349 кварталам Гатчины (в исходном файле было
351; две геометрии нулевой площади отброшены), собранный из файла
`examples/data/blocks_agg_with_indicators.geojson`.

Страница: `examples/gatchina_dashboard.html`

Ноутбук: `examples/gatchina_dashboard.ipynb`

## Что внутри

- интерактивная карта с переключением метрик и фильтрами;
- KPI-карточки;
- графики по землепользованию, доступности, FSI/GSI, морфотипам и топ-10;
- сводные таблицы, топ-10 и проверки качества;
- объяснение показателей, методики и ограничений;
- автоматические выводы.

## Как запустить

```powershell
cd "C:\Users\pc\Desktop\р\python-package-boilerplate"
.\.venv\Scripts\jupyter.exe nbconvert --to notebook --execute --inplace examples\gatchina_dashboard.ipynb
```

Или откройте ноутбук в Jupyter Lab и выполните **Kernel → Restart & Run All**.

## Результаты

- `examples/gatchina_dashboard.html` — готовая страница;
- `examples/data/gatchina/blocks_clean.geojson` — очищенные кварталы;
- `examples/data/gatchina/indicators.csv` — показатели по кварталам;
- `examples/data/gatchina/summary.json` и `summary.csv` — городские итоги;
- `examples/data/gatchina/land_use_summary.csv`;
- `examples/data/gatchina/morphotype_summary.csv`;
- `examples/data/gatchina/validation_report.csv`;
- `examples/data/gatchina/chart_data.json`.

## Важное ограничение

В исходном файле `site_area` посчитана в EPSG:3857 и примерно в 3,88 раза больше
метрической площади. Поэтому FSI/GSI пересчитаны на `area_m2` в UTM 36N; исходные значения
сохранены для сверки. Население — оценка, а не официальная статистика.
