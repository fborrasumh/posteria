# PosterIA

Del artículo al póster de congreso, con cada frase y cada cifra comprobadas. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/posteria/

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24100555.svg)](https://doi.org/10.5281/zenodo.24100555)

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- Lee el artículo (Word, PDF con texto o texto) o el resumen de congreso pegado, y las figuras como imágenes (PNG, JPG o WebP; hasta 8).
- La IA propone el contenido del póster: título, autores, afiliaciones, frases por sección (introducción, objetivo, métodos, resultados, conclusiones y referencias), de 2 a 4 resultados clave y la sección y el pie de cada figura. El póster puede redactarse en español, inglés o portugués, sea cual sea el idioma del texto.
- **El código comprueba**: que la cita literal de cada frase aparece en el texto (sin contar mayúsculas, tildes ni puntuación); que las cifras de dos o más dígitos y los decimales de cada frase están en el texto; que todas las cifras de cada resultado clave están en su cita; que los autores propuestos aparecen en el texto; y descarta figuras inexistentes y elementos de más. Lo que no se verifica empieza fuera del póster; la persona puede incluirlo, y la lista final de comprobaciones lo recuerda.
- Maquetación determinista en el navegador: tres plantillas (Columnas, Hallazgo central y Bloques), A0 o A1, vertical u horizontal. El texto se pone al mayor tamaño con el que todo cabe; si ni al mínimo cabe, se dice qué se queda fuera.
- Estilo institucional: colores principal y de acento (con cálculo de contraste), hasta 3 logos y pie; se guarda y se carga como fichero JSON.
- Descargas escritas en el navegador, sin librerías ni red: PDF vectorial del tamaño real (Helvetica estándar), PowerPoint de una diapositiva del tamaño del póster con cada bloque de texto editable, SVG y proyecto JSON para seguir otro día.
- Ejemplo con un artículo ficticio que funciona sin clave, en los tres idiomas.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. La clave se guarda solo en el navegador. No hace falta servidor.

## Privacidad

Texto, figuras, logos y póster se guardan solo en el navegador (IndexedDB). Al pulsar «Proponer el contenido del póster» sale hacia el proveedor de IA elegido el texto, con correos, teléfonos y DNI/NIE enmascarados, y la lista de figuras con su nombre y su pie; **las imágenes no se envían nunca**. Antes del primer envío de la sesión se muestra una muestra de lo que sale y se pide confirmación. El proyecto y el estilo exportados no llevan la clave.

## Límites

- La IA puede equivocarse: el código comprueba que cada frase tiene respaldo literal y que sus cifras existen, **no** que resuma bien su cita, que las conclusiones sean las adecuadas ni que la figura corresponda al pie. Los números de una sola cifra no se comprueban.
- De un PDF solo se lee el texto: las figuras hay que subirlas como imágenes. Los PDF escaneados (sin texto) no se leen; hay que pegar el texto.
- El PDF usa las fuentes estándar Helvetica sin incrustar y codificación WinAnsi: letras griegas, ≥, ≤, → y otros símbolos se sustituyen (la app lo avisa); el PowerPoint y el SVG los conservan. El PDF es RGB: si la imprenta exige PDF/X o CMYK, hay que convertirlo.
- Las imágenes se guardan en JPEG (máx. 2400 px las figuras y 1000 px los logos): sin transparencia, por eso los logos van sobre un panel blanco.
- En PowerPoint el texto vuelve a cortarse con Arial (mismas métricas que Helvetica); se deja un 1,5 % de holgura para que no aparezcan líneas de más, pero conviene revisarlo.
- Una sola página; sin ecuaciones, tablas editables ni códigos QR.
- Probado con IA simulada en Chromium (Playwright), con PDF validado con qpdf y PowerPoint abierto con python-pptx y LibreOffice. No probado aún con claves reales ni en PowerPoint de Microsoft.

## Inspiración

La función se inspira en el agente de pósteres académicos de Yila AI (yila.ai); no se ha reutilizado su código.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche).


ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. (2026). *PosterIA* (v1.0.0) [Software]. DOI: [10.5281/zenodo.24100555](https://doi.org/10.5281/zenodo.24100555)

## Licencia

MIT. Véase [LICENSE](LICENSE).
