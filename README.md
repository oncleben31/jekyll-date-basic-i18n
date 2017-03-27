# jekyll-date-basic-i18n

> This code is a basic internationalization of dates in Jekyll without plugin. You just have to copy the include, a string file and make a correct call with the liquid tag `{% translated_date.html ... %}`

## Usage

Insert the following liquid tag in your code:

`{% include translated_date.html date=A_DATE format=YOUR_FORMAT lang=THE_LANG_TO_USE %}`

*   `date` is the date to be used (ex: `page.date`)
*   `format` is the date format you want to use (ex: `"%A %-d %B %Y"`) following the [date filter syntax](https://help.shopify.com/themes/liquid/filters/additional-filters#date). If you omit this parameter the default will be:
    *   `date_format` if set in the `_config.yml`
    *   `"%b %-d, %Y"` otherwise.
*   `lang` is the language to use for the translation (ex: `en` or `fr`). You have to put a file `THE_LANG_TO_USE.yml` in the `_data/locales` folder. If you omit `lang` parameter the default will be:
    *   `lang` set in the Front Matter of your post or page.
    *   `lang` set in the `_config.yml`

This include will replace in the `format` string the `%a` (abbreviated day name), `%A` (full day name), `%b` (abbreviated month name) and `%B` (full month name), by the corresponding translation found in the `_data/locales/[lang].yml` file.

## Example

```
{% include translated_date.html date=post.date format="%-d %B %Y" lang="pl" %}
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am "Add some feature"`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

If you find any issues, please feel free to contribute to [repository issues](https://github.com/oncleben31/jekyll-date-basic-i18n/issues)

If you want to share your translation to others languages, make a Pull Request.

## Context

This is the code I've designed when trying to localized [my blog oncleben31.cc](http://oncleben31.cc) (Jekyll sources available at [oncleben31/oncleben31-cc](https://github.com/oncleben31/oncleben31-cc)).

I've made it the more reusable possible with the idea to push it in minima, the default Jekyll theme. There is still an opened PR [jekyll/minima#60](https://github.com/jekyll/minima/pull/60) with this code and some strings to translate the theme.
