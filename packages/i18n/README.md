# i18n

## Usages

- Update missing translations into the base resources, a.k.a the `src/resources/en.json`
- Replace literal text with translation keys

```tsx
import { useTranslation } from '@affine/i18n';

// src/resources/en.json
// {
//     'Text': 'some text',
//     'Switch to language': 'Switch to {{language}}', // <- you can interpolation by curly brackets
// };

const App = () => {
  const { t } = useTranslation();

  const changeLanguage = (language: string) => {
    i18n.changeLanguage(language);
  };

  return (
    <div>
      <div>{t('Text')}</div>

      <button onClick={() => changeLanguage('en')}>
        {t('Switch to language', { language: 'en' })}
      </button>
      <button onClick={() => changeLanguage('zh-Hans')}>
        {t('Switch to language', { language: 'zh-Hans' })}
      </button>
    </div>
  );
};
```

## How to sync translations manually

- Set token as environment variable

```shell
export TOLGEE_API_KEY=tgpak_XXXXXXX
```

- Run the `sync-languages:check` to check all languages
- Run the `sync-languages` script to add new keys to the tolgee platform

## References

- [AFFiNE | Tolgee](https://i18n.affine.pro/)
- [Tolgee Documentation](https://tolgee.io/docs/)
- [i18next](https://www.i18next.com/)
- [react-i18next](https://react.i18next.com/)
