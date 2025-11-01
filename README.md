# Character Abilities — Приклад SOLID (Interface Segregation Principle)

Цей приклад демонструє **принцип розділення інтерфейсів (ISP)** із SOLID у мові C#.

## Суть принципу ISP

> **Клієнти не повинні залежати від інтерфейсів, які вони не використовують.**

Іншими словами:
- Інтерфейси повинні бути **дрібними та спеціалізованими**.
- Клас реалізовує **лише ті інтерфейси**, які йому дійсно потрібні.
- Клас *не має бути змушений* реалізовувати зайві методи.

---

## Структура

У прикладі використані два незалежні інтерфейси:

| Інтерфейс | Мета |
|----------|------|
| `IMagician` | Визначає можливість кастувати закляття |
| `ISwordsman` | Визначає можливість атакувати мечем |

Класи реалізовують тільки потрібні їм інтерфейси:

| Клас | Реалізує | Що вміє |
|------|---------|--------|
| `MasterOfAll` | `IMagician`, `ISwordsman` | І кастує, і атакує |
| `Witch` | `IMagician` | Тільки кастує |

---

## Код

```csharp
interface IMagician
{
    void Cast();
}

interface ISwordsman
{
    void Attack();
}

class MasterOfAll : IMagician, ISwordsman
{
    public void Cast() => Console.WriteLine("Кастую реквієм");
    public void Attack() => Console.WriteLine("Атакую мечем");
}

class Witch : IMagician
{
    public void Cast() => Console.WriteLine("Відьмую відьмовське");
}
