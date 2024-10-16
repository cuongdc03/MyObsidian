
| id                            | hubs           | source                                                                                      |
| ----------------------------- | -------------- | ------------------------------------------------------------------------------------------- |
| 202410151117_Template Literal | [[TypeScript]] | https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html#handbook-content |
Template literal types build on [string literal types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#literal-types), and have the ability to expand into many strings via unions.
They have the same syntax as [template literal strings in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals), but are used in type positions. When used with concrete literal types, a template literal produces a new string literal type by concatenating the contents.
```ts
type World = "world";

type Greeting = `hello ${World}`;
```
For each interpolated position in the template literal, the unions are cross multiplied:
```TS
type AllLocaleIDs = `${EmailLocaleIDs | FooterLocaleIDs}_id`;

type Lang = "en" | "ja" | "pt";

type LocaleMessageIDs = `${Lang}_${AllLocaleIDs}`;
//`   type LocaleMessageIDs = "en_welcome_email_id" | "en_email_heading_id" | "en_footer_title_id" | "en_footer_sendoff_id" | "ja_welcome_email_id" | "ja_email_heading_id" | "ja_footer_title_id" | "ja_footer_sendoff_id" | "pt_welcome_email_id" | "pt_email_heading_id" | "pt_footer_title_id" | "pt_footer_sendoff_id"   `
```