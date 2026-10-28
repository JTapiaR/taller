# presenta-en-ingles

Plugin de Claude Code para preparar y ensayar en inglés la presentación de resultados anuales de una organización. Las instrucciones y el feedback están en español; las frases de práctica, en inglés.

## Contenido

```
.claude-plugin/plugin.json          Manifiesto del plugin
skills/
├── coach-presentacion/             Coach automático (Claude la usa sola)
│   ├── SKILL.md
│   └── frases.md                   Banco de frases en inglés
├── ensayo/SKILL.md                 Ensayo guiado (solo manual)
├── preguntas-dificiles/SKILL.md    Simulación de preguntas (solo manual)
└── practica-diaria/SKILL.md        Ficha diaria para tarea programada
```

## Instalación

### Para probarlo

Desde cualquier terminal:

```
claude --plugin-dir C:\Users\jesic\Downloads\taller\plugins\presenta-en-ingles
```

El plugin se carga solo durante esa sesión.

### Instalación permanente (desde el marketplace de GitHub)

Dentro de Claude Code:

```
/plugin install presenta-en-ingles --marketplace <tu-usuario>/taller
```

O en dos pasos:

```
/plugin marketplace add <tu-usuario>/taller
/plugin install presenta-en-ingles@taller
```

## Uso

### Coach automático

No hace falta invocarlo. Basta con pedir algo como:

> Ayúdame a preparar en inglés la presentación de resultados de 2026 para la junta.

Claude activará `coach-presentacion`, propondrá una estructura y frases del banco, y revisará tus textos.

### Ensayo (manual)

```
/presenta-en-ingles:ensayo Opening
/presenta-en-ingles:ensayo Our revenue grew 12% to 4.2 million euros this year.
```

Lo que escribas después del comando es el material a ensayar. Sin argumentos, te pedirá un texto o una sección.

### Preguntas difíciles (manual)

```
/presenta-en-ingles:preguntas-dificiles inversores, caída de ingresos
/presenta-en-ingles:preguntas-dificiles prensa
```

Simula 5 preguntas, una a una, y te da feedback y una respuesta modelo para cada una.

### Práctica diaria

Genera una ficha breve sin hacer preguntas. Si el plugin está instalado, se puede lanzar a mano (si no, añade `--plugin-dir C:\Users\jesic\Downloads\taller\plugins\presenta-en-ingles`):

```
claude -p "/presenta-en-ingles:practica-diaria"
```

O con un tema:

```
claude -p "/presenta-en-ingles:practica-diaria cifras y porcentajes"
```

#### Programarla cada día

- **Tarea programada de Claude:** crea una tarea programada (por ejemplo, de lunes a viernes a las 8:00) cuyo prompt sea `/presenta-en-ingles:practica-diaria`.
- **Programador de tareas de Windows:** crea una tarea diaria que ejecute en PowerShell:

  ```
  claude --plugin-dir C:\Users\jesic\Downloads\taller\plugins\presenta-en-ingles -p "/presenta-en-ingles:practica-diaria" > "$env:USERPROFILE\Documents\practica-$(Get-Date -Format yyyy-MM-dd).md"
  ```

  Cada día tendrás tu ficha en `Documentos`.

## Personalizar

Añade tus propias frases a `skills/coach-presentacion/frases.md`, respetando las secciones existentes. Todas las skills lo usan como fuente.
