# Research notes (landscape, authorities, key sources)

Собрано 2026-09-21 (ночь). Сетевой доступ из среды был ограничен: напрямую открывались только github.com
и поисковый API; всё остальное (arxiv, lesswrong, 80000hours, reducing-suffering, t.me, docs.google.com)
восстановлено по поисковым сводкам и по памяти модели. Ссылки ниже — на первоисточники (проверить утром).

## 1. Кто менторы и что они делают
- **Caspar Oesterheld** — CMU (Foundations of Cooperative AI Lab), ныне Redwood Research, команда
  "conceptual reasoning capabilities". Главные работы:
  - *Multiverse-wide Cooperation via Correlated Decision Making* (2017) — ECL / evidential cooperation in large worlds.
    https://longtermrisk.org/media/Multiverse-wide-Cooperation-via-Correlated-Decision-Making.pdf
  - *Robust program equilibrium* (Theory and Decision, 2019) — ε-grounded FairBot (пример из задания).
    https://link.springer.com/article/10.1007/s11238-018-9679-3
  - *Similarity-based cooperative equilibrium* (NeurIPS 2023).
  - *A typology of Newcomblike problems* (Treutlein & Oesterheld).
    https://johannestreutlein.com/wp-content/uploads/2024/10/a-typology-of-newcomblike-problems.pdf
  - *Can CDT rationalise the ex ante optimal policy via modified anthropics?* (Cooper, Oesterheld, Conitzer; arXiv 2411.04462)
    — CDT + неопределённость «я — симуляция предиктора?» может one-box'ить. Прямо связано с идеей BAC.
  - *Recursive Joint Simulation in Games* (Kovařík, Oesterheld, Conitzer; arXiv 2402.08128).
  - Safe Pareto improvements (Oesterheld & Conitzer) — упомянуты в задании.
- **Emery Cooper** — Redwood Research; соавтор DTBench и LMCA; валидировала все вопросы DTBench.
- Позиция Остерхельда: симпатизирует EDT-подобным теориям и акаузальной кооперации (ECL), но в датасетах
  строго разделяет «capability»-вопросы (единственно верный ответ: «что рекомендует EDT/CDT») и «attitude».

## 2. Датасеты команды (что уже «насыщено»)
- **DTBench** — 407 (в статье 2024: 537) рукописных MCQ по Newcomb-подобным задачам.
  Статья: *A dataset of questions on decision-theoretic reasoning in Newcomb-like problems* (arXiv 2411.10588;
  LW: https://www.lesswrong.com/posts/d9amcRzns5pwg9Fcu/). Категории: scenario analysis, theory application
  (apply EDT / apply CDT), multiagent (twin PD и т.п.), **Fauxcomb** (выглядит как Newcomb, но корреляции нет —
  контроль на эвристики). Вывод статьи: capability коррелирует с общей силой модели и с EDT-склонностью;
  CoT критичен. По заданию: датасет насыщен к июню 2026.
- **LMCA** — *A dataset of rated conceptual arguments* (arXiv 2607.27499; PDF: andrew.cmu.edu/user/coesterh/LMCA_dataset.pdf).
  951 критик к 442 позиционным текстам, 1458 экспертных оценок (centrality, strength, correctness, clarity).
  Модели плохо воспроизводят экспертные рейтинги; «thinking modes» систематически не помогают.
- **ACCoRD** — consistency-датасет (~14k constraint'ов, 18 типов; напр. p(A) ≥ p(A|B)·p(B)).
- **Conceptual Reasoning Index** (Anthropic alignment blog + Redwood, 12 авг 2026): LMCA 60% + ACCoRD 20% + DTBench 20%.
  https://alignment.anthropic.com/2026/conceptual-reasoning-index/ ; https://conceptualreasoning.ai/

## 3. Аргумент 1: Haste consideration
- Оригинал: 80000 Hours, апрель 2012. https://80000hours.org/2012/04/the-haste-consideration/
- Известная критика: Brian Tomasik, *The Haste Consideration, Revisited* (2013, upd. 2018)
  https://reducing-suffering.org/the-haste-consideration-revisited/ — движения растут логистически, а не
  экспоненциально; насыщение; IRR не так высок. Это ЭМПИРИЧЕСКАЯ критика (compounding-версии аргумента).
- Наш вывод (см. task2/): у аргумента в том виде, как он дан, есть более фундаментальная СТРУКТУРНАЯ дыра —
  мысленный эксперимент вообще не сравнивает «ресурсы сейчас» с «ресурсами позже», а сравнивает
  «рекрутинг» с «прямой работой» (оговорка «не хуже тебя» делает всю работу). См. critique.

## 4. Аргумент 2: Blind Anthropic Cooperation (BAC)
- Идея Caspar Oesterheld; публично существует только в его Google Doc (недоступен из среды) и в explainer'е
  из задания. Родственники: ECL, Bostrom simulation argument (https://simulation-argument.com/simulation.pdf),
  «modified anthropics» (arXiv 2411.04462), acausal trade.
- Наш вывод (см. task2/): центральное утверждение explainer'а — «BAC структурно изоморфен многопользовательскому
  Stag Hunt» — ложно при его же собственных выплатах: стоимость BAC условна (платишь только BAC-детям),
  поэтому BAC = 1 + 2p ≥ 1 = Take, т.е. BAC слабо доминирует, и никакой «охоты на оленя» (риск-доминирование,
  salience) нет. Подробности и альтернативные критики — в task2/.

## 5. Известные слабости LLM в decision theory (для Task 1)
- Смешение EDT с FDT/UDT (one-box в transparent Newcomb, платить в counterfactual mugging, Parfit's hitchhiker).
- Эвристика «есть предиктор → one-box», «есть копия → cooperate» вне зависимости от screening-off.
- Путаница «точность предиктора» vs «информативность предсказания» (base rates).
- Путаница уровней: доля популяции vs вероятность для конкретного контрагента; условная vs безусловная цена.
- LW-пост «Kimi likes causal decision theory more after RL in twin PD» — RL сдвигает attitude.

## 6. Предыдущий кандидат (для калибровки, НЕ копировать)
- https://github.com/dani2442/MATS_application — Task 1: «summarization method, two Claude failures»;
  Task 2: критика BAC. Содержимое не читалось детально (только структура).
