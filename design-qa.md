**Findings**
- [P0] Автоматический visual QA заблокирован системными настройками Safari
  Location: локальный рендер блока `#teachers`.
  Evidence: source visual truth доступен по пути `/var/folders/qy/4p252svs3l163qm5brjjkr5r0000gn/T/TemporaryItems/NSIRD_screencaptureui_Ais3eG/Снимок экрана — 2026-06-24 в 17.37.03.png`, но Safari WebDriver вернул `You must enable 'Allow remote automation' in the Developer section of Safari Settings`.
  Impact: не удалось снять implementation screenshot и провести side-by-side сравнение фактического рендера со скриншотом-референсом.
  Fix: включить `Allow remote automation` в Safari или дать доступный browser capture tool, затем повторить QA-проход.

**Open Questions**
- Если хочешь, могу следующим сообщением добить финальный pixel-pass после того, как будет доступен любой способ снять screenshot страницы.

**Implementation Checklist**
- Локальные портреты преподавателей сгенерированы и подключены в секцию.
- Секция `#teachers` заменена на отдельный showcase-блок по референсу.
- Добавлены адаптивные стили для desktop, tablet и mobile.
- Добавлена локальная иконка стрелки для CTA-карточки.

**Follow-up Polish**
- После живого screenshot-сравнения можно доточить ширины колонок, crop портретов и переносы текста до более плотного совпадения со скриншотом.

source visual truth path: `/var/folders/qy/4p252svs3l163qm5brjjkr5r0000gn/T/TemporaryItems/NSIRD_screencaptureui_Ais3eG/Снимок экрана — 2026-06-24 в 17.37.03.png`
implementation screenshot path: blocked, Safari remote automation disabled
viewport: target desktop, implementation capture unavailable
state: static default state
full-view comparison evidence: blocked, implementation screenshot unavailable
focused region comparison evidence: blocked, implementation screenshot unavailable
patches made since the previous QA pass: replaced the teachers section with a five-card showcase; generated and connected four portrait assets; added a right-arrow icon asset; added responsive CSS tuning
final result: blocked
