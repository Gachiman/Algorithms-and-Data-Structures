# Экзаменационный билет №23

## 1. Способы агрегации графических объектов (группирование и конструирование).

**Агрегация** – это абстракция, которая превращает связь между объектами в некоторый агрегированный объект.

### Группирование

**Составной объект** - набор геометрических объектов (как базовых так и составных), рассматриваемых при выполнении операций обработки как единый объект\

```C++
class TChartGroup : public TChartRoot
{
 protected:
    TDatList Group;  // Список объектов
 public:
    TChartGroup() { }
    void InsUnit(TChartRoot *pUnit);  // Добавление
    virtual void Show();  // Визуализация
    virtual void Hide();  // Скрытие
    virtual void CalcParams(double t = -1);  // Пересчет параметров
};
```

### Конструирование

**Геометрический объект** может быть сконструирован с использованием уже существующих объектов

- например, ломаная может быть определена через набор конечных точек составляющих отрезков

```C++
class TChartPolyline : public TChartGroup
{
 public:
    TChartPolyline() { }
    void InsPoint(TChartRoot *pUnit);  // Добавление
    virtual void Show();  // Визуализация
    virtual void Hide();  // Скрытие
    virtual void CalcParams(double t = -1);  // Пересчет параметров
};
```

## 2. Сравнение структур хранения линейных и динамических структур данных.

### Линейные структуры

- Базисное множество - множество элементов
- Базисное отношение - отношение следования
- В структуре хранения хранятся все элементы структуры
- Отношение следования реализуется при помощи адресной арифметики

### Динамические структуры

- Элементы базисного множества являются структурами (ДС - структуры структур)
- Базисное отношение - отношение включения
- В структуре хранения хранится только текущий элемент
- Отношение включения реализуется при помощи программ
