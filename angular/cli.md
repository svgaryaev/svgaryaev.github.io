# Angular CLI

Создать новое приложение

```bash
ng new <appname> --directory <folder> -p <prefix> -g --routing true --style scss
```

> --prefix (-p) The prefix to apply to generated selectors.
app-root становится prefix-root, но app.component.ts остается тем же (-p после -g не работает)

Создать модуль

```bash
ng generate module <name> [options]
ng generate module core -m app --project <appname>
ng generate module system -m core --project <appname> --routing true

--flat=false|true
--module=module (-m)
--project=project
--routing=true|false
--routingScope=Child|Root
```

Создать страничные компоненты

```bash
ng generate component <name> [options]
ng generate component core/home -m core --project <appname> --export=true

--prefix=prefix (-p) менеят префикс на любой другой (по умолчанию общий для проекта)
--selector=selector меняет селектор полностью, даже префикс затирает
--export=true|false false by default
```

Создать директиву

```bash
ng generate directive <name> -m <module> --project <appname> --export=true
```

Создать пайпу

```bash
ng generate pipe  <name> -m <module> --project <appname> --export=true
```

Создать службу

```bash
ng generate service services/main --project <appname>
```
