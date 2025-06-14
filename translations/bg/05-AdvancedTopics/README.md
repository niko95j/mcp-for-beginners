<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "adaf47734a5839447b5c60a27120fbaf",
  "translation_date": "2025-06-11T16:26:20+00:00",
  "source_file": "05-AdvancedTopics/README.md",
  "language_code": "bg"
}
-->
# Разширени теми в MCP

Тази глава е предназначена да разгледа серия от напреднали теми в имплементацията на Model Context Protocol (MCP), включително мултимодална интеграция, мащабируемост, най-добри практики за сигурност и интеграция в корпоративна среда. Тези теми са от съществено значение за изграждане на стабилни и готови за продукция MCP приложения, които могат да отговорят на изискванията на съвременните AI системи.

## Преглед

Този урок разглежда напреднали концепции в имплементацията на Model Context Protocol, с фокус върху мултимодална интеграция, мащабируемост, най-добри практики за сигурност и корпоративна интеграция. Тези теми са важни за изграждане на MCP приложения с производствен клас, които могат да се справят със сложни изисквания в корпоративна среда.

## Учебни цели

След края на този урок ще можете да:

- Имплементирате мултимодални възможности в рамките на MCP
- Проектирате мащабируеми MCP архитектури за среди с високи натоварвания
- Прилагате най-добри практики за сигурност, съобразени с принципите на сигурност на MCP
- Интегрирате MCP с корпоративни AI системи и рамки
- Оптимизирате производителността и надеждността в продукционни среди

## Уроци и примерни проекти

| Връзка | Заглавие | Описание |
|------|-------|-------------|
| [5.1 Integration with Azure](./mcp-integration/README.md) | Интеграция с Azure | Научете как да интегрирате вашия MCP сървър в Azure |
| [5.2 Multi modal sample](./mcp-multi-modality/README.md) | MCP мултимодални примери | Примери за аудио, изображения и мултимодални отговори |
| [5.3 MCP OAuth2 sample](../../../05-AdvancedTopics/mcp-oauth2-demo) | MCP OAuth2 Демонстрация | Минимално Spring Boot приложение, показващо OAuth2 с MCP, както като Authorization, така и като Resource Server. Демонстрира сигурно издаване на токени, защитени крайни точки, разгръщане в Azure Container Apps и интеграция с API Management. |
| [5.4 Root Contexts](./mcp-root-contexts/README.md) | Root контексти | Научете повече за root контекста и как да ги имплементирате |
| [5.5 Routing](./mcp-routing/README.md) | Рутинг | Научете различни видове маршрутизация |
| [5.6 Sampling](./mcp-sampling/README.md) | Семплиране | Научете как да работите със семплиране |
| [5.7 Scaling](./mcp-scaling/README.md) | Мащабиране | Научете за мащабирането |
| [5.8 Security](./mcp-security/README.md) | Сигурност | Осигурете сигурността на вашия MCP сървър |
| [5.9 Web Search sample](./web-search-mcp/README.md) | Уеб търсене MCP | Python MCP сървър и клиент, интегриращи се с SerpAPI за реално време уеб, новинарско, продуктово търсене и въпроси и отговори. Демонстрира мултиинструментна оркестрация, интеграция на външни API и стабилна обработка на грешки. |
| [5.10 Realtime Streaming](./mcp-realtimestreaming/README.md) | Поточно предаване | Поточното предаване на данни в реално време се превърна в основен елемент в днешния свят, ориентиран към данни, където бизнесите и приложенията се нуждаят от незабавен достъп до информация за вземане на навременни решения. |

## Допълнителни източници

За най-актуална информация относно напредналите теми в MCP, вижте:
- [MCP Documentation](https://modelcontextprotocol.io/)
- [MCP Specification](https://spec.modelcontextprotocol.io/)
- [GitHub Repository](https://github.com/modelcontextprotocol)

## Основни изводи

- Мултимодалните MCP имплементации разширяват възможностите на AI отвъд обработката на текст
- Мащабируемостта е ключова за корпоративни внедрявания и може да се постигне чрез хоризонтално и вертикално мащабиране
- Комплексните мерки за сигурност защитават данните и осигуряват правилен контрол на достъпа
- Корпоративната интеграция с платформи като Azure OpenAI и Microsoft AI Foundry разширява възможностите на MCP
- Напредналите MCP имплементации се възползват от оптимизирани архитектури и внимателно управление на ресурсите

## Упражнение

Проектирайте MCP имплементация с корпоративен клас за конкретен случай на употреба:

1. Идентифицирайте мултимодалните изисквания за вашия случай
2. Опишете необходимите мерки за сигурност за защита на чувствителни данни
3. Проектирайте мащабируема архитектура, която може да се справи с променливо натоварване
4. Планирайте интеграционните точки с корпоративни AI системи
5. Документирайте потенциални проблеми с производителността и стратегии за тяхното овладяване

## Допълнителни ресурси

- [Azure OpenAI Documentation](https://learn.microsoft.com/en-us/azure/ai-services/openai/)
- [Microsoft AI Foundry Documentation](https://learn.microsoft.com/en-us/ai-services/)

---

## Какво следва

- [5.1 MCP Integration](./mcp-integration/README.md)

**Отказ от отговорност**:  
Този документ е преведен с помощта на AI преводаческа услуга [Co-op Translator](https://github.com/Azure/co-op-translator). Въпреки че се стремим към точност, моля, имайте предвид, че автоматизираните преводи могат да съдържат грешки или неточности. Оригиналният документ на неговия първоначален език трябва да се счита за авторитетен източник. За критична информация се препоръчва професионален човешки превод. Ние не носим отговорност за каквито и да е недоразумения или неправилни тълкувания, възникнали от използването на този превод.