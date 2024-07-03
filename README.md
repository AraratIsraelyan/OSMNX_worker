# OSMNX Graph Processor

Этот проект содержит класс `OSMNX`, который предоставляет методы для работы с графами, основанными на данных OpenStreetMap (OSM). Класс включает функциональность для чтения графов, поиска кратчайших маршрутов, вычисления длины маршрутов и визуализации графов.

Для использования данного проекта необходимо установить следующие зависимости:

```sh
pip install osmnx geopandas scikit-learn
```
_________
## Пример использования:

from osmnx_graph_processor import OSMNX
graph_processor = OSMNX()

### Чтение графа из онлайн-источника
graph = graph_processor.read_online_osmnx('path_to_polygon.shp')

### Поиск кратчайшего маршрута
shortest_route = graph_processor.search_shortest_route(
    graph, 
    weight_param='length', 
    latlng1=(lat1, lng1), 
    latlng2=(lat2, lng2)
)

### Вычисление длины маршрута
route_length = graph_processor.search_route_length(graph, shortest_route)

### Визуализация кратчайшего маршрута
graph_processor.draw_shortest_route(graph, shortest_route)

### Сохранение графа в файлы
graph_processor.save_graph(graph, 'path_to_save_directory')
