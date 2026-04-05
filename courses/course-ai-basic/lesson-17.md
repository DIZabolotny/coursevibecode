# Урок 17. Сжатый практический конспект по ИИ-инструментам (актуально на 2026-02-20)

Этот файл: только практика, без философии.  
Логика: от простого к сложному.

## 0) Быстрый старт (30 минут)

1. Выберите 1 основной чат (например, ChatGPT или Gemini) и 1 резервный.
2. Настройте единый шаблон запроса:
   - `Контекст`
   - `Цель`
   - `Ограничения`
   - `Формат ответа`
   - `Критерии качества`
3. Создайте папку проекта:
   - `00_inputs` (исходники)
   - `01_drafts` (черновики)
   - `02_final` (финал)
   - `03_prompts` (рабочие промпты)

## 1) Выбор инструмента по задаче

## 1.1 Текст и аналитика (ежедневная работа)

- Нужна универсальность и экосистема: ChatGPT.
- Нужна глубокая работа с длинным контекстом/доками: Claude.
- Нужен tight-stack с Google Docs/Sheets: Gemini.
- Нужна бюджетная API-автоматизация: DeepSeek / Mistral / Grok API (сравнивайте цену и latency под ваши задачи).

## 1.2 Глубокие исследования (research mode)

- Для отчетов с источниками и многошаговым поиском:
  - ChatGPT Deep Research.
  - Gemini Deep Research.
  - Claude Research (beta).
  - Mistral Le Chat Deep Research.
  - Grok DeepSearch.

## 1.3 Медиа

- Изображения:
  - Midjourney (сильная эстетика и стилистика).
  - Stable Image (Stability API) для программной интеграции.
  - OpenAI image generation через API.
- Видео:
  - OpenAI Sora (видео через Sora / API-видео-пайплайн).
  - Stability Video API (если нужен API-first поток).
- Речь:
  - OpenAI speech-to-text / text-to-speech модели для интеграций.

## 2) Базовый шаблон промпта (используйте всегда)

```text
Ты — [роль].
Контекст: [данные/фон].
Цель: [что получить].
Ограничения: [что нельзя, дедлайн, объем, тон].
Формат: [таблица/список/JSON/план].
Критерии качества: [точность, проверяемость, применимость].
Сначала задай до 3 уточняющих вопросов, если данных не хватает.
```

## 3) От простого к сложному: рабочие сценарии

## 3.1 Уровень 1: быстрые задачи (минуты)

- Рерайт, суммаризация, письмо, пост, перевод.
- Правило: 1 задача = 1 запрос, без смешивания целей.
- Выход фиксируйте в `01_drafts`.

## 3.2 Уровень 2: повторяемые задачи (часы)

- Создайте библиотеку промптов по ролям:
  - `редактор`
  - `аналитик`
  - `маркетолог`
  - `технический помощник`
- Вынесите входные параметры в чеклист:
  - аудитория
  - цель
  - ограничения
  - KPI результата

## 3.3 Уровень 3: работа с вашими материалами (дни)

- Используйте проекты/рабочие пространства:
  - загрузите базовые документы,
  - зафиксируйте «правила проекта»,
  - работайте итерациями.
- На каждом цикле:
  1. черновик;
  2. критика по чеклисту;
  3. правка;
  4. финал.

## 3.4 Уровень 4: deep research под решение

Минимальный pipeline:
1. Сформулируйте исследовательский вопрос в 1 предложении.
2. Задайте критерии источников (дата, тип, гео, исключения).
3. Попросите план исследования перед запуском.
4. Запустите исследование.
5. Проверьте:
   - есть ли ссылки на источники,
   - нет ли неподтвержденных выводов,
   - можно ли повторить логику выводов.
6. Синтезируйте выводы в action-plan (что делать на практике).

## 3.5 Уровень 5: агентные сценарии

- Когда переходить к агентам:
  - многошаговый процесс,
  - регулярные запуски,
  - несколько инструментов и источников,
  - требуется оркестрация.
- Минимальная архитектура:
  - `Planner` (разбивает задачу),
  - `Researcher` (собирает факты),
  - `Writer` (готовит output),
  - `Reviewer` (валидирует).
- Обязательные guardrails:
  - лимиты бюджета/токенов,
  - whitelist источников,
  - логирование шагов,
  - human-in-the-loop перед публикацией.

## 4) Актуализация (что изменилось относительно старых материалов)

1. В ChatGPT произошла смена модельной линейки: GPT-5 и GPT-5 Pro в ChatGPT; часть старых моделей выведена из ChatGPT-интерфейса.
2. Deep Research в экосистеме OpenAI заметно расширился (коннекторы, экспорт, улучшения точности, MCP-интеграции).
3. В Gemini актуальны семейства 2.5/3.x и Deep Research в Gemini Apps.
4. В Anthropic актуальна линейка Claude 4.x, а режим Research запущен в beta.
5. В xAI API доступны модели Grok 4/4.1 Fast и встроенные инструменты (web search, code execution).
6. В DeepSeek API обновлены reasoner/chat-модели (V3.1/V3.2 поколения).
7. В Mistral Le Chat доступен режим Deep Research; в API развивается Agents-подход.
8. В генерации изображений/видео выросла роль API-first сценариев (OpenAI/Stable API), при этом Midjourney остается сильным в художественных стилях.

## 5) Короткие playbooks по кейсам

## 5.1 Маркетинг/контент

1. Бриф (ЦА, оффер, канал, KPI).
2. 3 варианта структуры.
3. 1 финальный текст + 5 адаптаций под каналы.
4. Отдельный этап фактчека цифр и утверждений.

## 5.2 Аналитика/исследование рынка

1. Deep Research по гипотезам.
2. Сводная таблица фактов с источниками.
3. Риски/слабые места гипотез.
4. Решение: `делать / не делать / что проверить дополнительно`.

## 5.3 Редактура расшифровок

1. STT (speech-to-text).
2. «Бережная редактура» без потери смысла.
3. Версия для публикации + краткое саммари.
4. Контроль: термины, имена, цифры.

## 5.4 Медиа-производство

1. Промпт-пакет: стиль, референсы, ограничения.
2. Генерация 5-10 вариантов.
3. Отбор по чеклисту (бренд, читаемость, соответствие задаче).
4. Постобработка и финал.

## 6) Чеклист качества перед любым релизом

- Цель решена?  
- Формат ровно тот, что требовался?  
- Есть неподтвержденные факты?  
- Есть ссылки/источники для спорных утверждений?  
- Можно повторить результат по этому же промпту?

## 7) Официальные источники для актуальности (проверено 2026-02-20)

- OpenAI Deep Research: <https://openai.com/index/introducing-deep-research/>
- OpenAI ChatGPT release notes: <https://help.openai.com/en/articles/6825453-chatgpt-release-notes>
- OpenAI GPTs: <https://help.openai.com/en/articles/8554397-creating-a-gpt00>
- OpenAI Projects: <https://help.openai.com/en/articles/10169521-using-projects-in-chatgpt>
- OpenAI API models: <https://platform.openai.com/docs/models>
- OpenAI image generation: <https://platform.openai.com/docs/guides/image-generation>
- OpenAI speech-to-text: <https://platform.openai.com/docs/guides/speech-to-text>
- OpenAI text-to-speech: <https://platform.openai.com/docs/guides/text-to-speech>
- OpenAI video generation: <https://platform.openai.com/docs/guides/video>
- Google Gemini API models: <https://ai.google.dev/gemini-api/docs/models/gemini>
- Google Gemini Deep Research: <https://support.google.com/gemini/answer/15719111>
- Anthropic model lineup: <https://docs.anthropic.com/en/docs/about-claude/models/all-models>
- Anthropic Research mode (beta): <https://www.anthropic.com/news/research>
- DeepSeek API docs/news: <https://api-docs.deepseek.com/>
- xAI API models/tools: <https://docs.x.ai/docs/models>
- Mistral Le Chat Deep Research: <https://docs.mistral.ai/getting-started/changelog/>
- Mistral Agents overview: <https://docs.mistral.ai/agents/agents_overview/>
- Midjourney docs (V7): <https://docs.midjourney.com/hc/en-us/articles/32859204029709-Version-7-Model>
- Stability API docs: <https://platform.stability.ai/docs/getting-started>


## Навигация по курсу

- [Предыдущий урок](./lesson-16.md)
- [Содержание курса](./README.md#карта-уроков)
- Следующий урок: нет (конец курса)
