# Interface-segregation-principle
Цей приклад демонструє застосування ISP у C#.  

---

code:

```csharp
using System;

namespace Interface_segregation_principle
{
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
}
