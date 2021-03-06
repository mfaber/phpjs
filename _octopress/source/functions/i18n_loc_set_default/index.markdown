---
layout: page
title: "JavaScript i18n_loc_set_default function"
comments: true
sharing: true
footer: true
alias:
- /functions/view/i18n_loc_set_default:865
- /functions/view/i18n_loc_set_default
- /functions/view/865
- /functions/i18n_loc_set_default:865
- /functions/865
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's i18n_loc_set_default

{% codeblock i18n/i18n_loc_set_default.js lang:js https://raw.github.com/kvz/phpjs/master/functions/i18n/i18n_loc_set_default.js raw on github %}
function i18n_loc_set_default (name) {
  // http://kevin.vanzonneveld.net
  // +   original by: Brett Zamir (http://brett-zamir.me)
  // %          note 1: Renamed in PHP6 from locale_set_default(). Not listed yet at php.net
  // %          note 2: List of locales at http://demo.icu-project.org/icu-bin/locexp (use for implementing other locales here)
  // %          note 3: To be usable with sort() if it is passed the SORT_LOCALE_STRING sorting flag: http://php.net/manual/en/function.sort.php
  // *     example 1: i18n_loc_set_default('pt_PT');
  // *     returns 1: true

  // BEGIN REDUNDANT
  this.php_js = this.php_js || {};
  // END REDUNDANT

  this.php_js.i18nLocales = {
    en_US_POSIX: {
      sorting: function (str1, str2) { // Fix: This one taken from strcmp, but need for other locales; we don't use localeCompare since its locale is not settable
        return (str1 == str2) ? 0 : ((str1 > str2) ? 1 : -1);
      }
    }
  };

  this.php_js.i18nLocale = name;
  return true;
}
{% endcodeblock %}

 - [Raw function on GitHub](https://github.com/kvz/phpjs/blob/master/functions/i18n/i18n_loc_set_default.js)

Please note that php.js uses JavaScript objects as substitutes for PHP arrays, they are 
the closest match to this hashtable-like data structure. 

Please also note that php.js offers community built functions and goes by the 
[McDonald's Theory](https://medium.com/what-i-learned-building/9216e1c9da7d). We'll put online 
functions that are far from perfect, in the hopes to spark better contributions. 
Do you have one? Then please just: 

 - [Edit on GitHub](https://github.com/kvz/phpjs/edit/master/functions/i18n/i18n_loc_set_default.js)

### Example 1
This code
{% codeblock lang:js example %}
i18n_loc_set_default('pt_PT');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
true
{% endcodeblock %}


### Other PHP functions in the i18n extension
{% render_partial _includes/custom/i18n.html %}
