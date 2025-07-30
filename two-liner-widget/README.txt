**************IMPORTANT NOTICE**************

1) There are 6 logo files in the snippets folder these also need to be added to Shopify’s snippet folder. The rest of the files are already rendered in the code, so they will display automatically.

2) There are script and style files in the assets folder after adding both files to the assets folder, if it’s a Shopify site, then link them inside `theme.liquid`, and if the website is built on any other technology, then they should be linked inside the `<head>` tag, just before `</head>`. I’m providing the code for that below.

Note: We should not add jQuery. Even if we need to write any custom code, it must be written in plain JavaScript jQuery should not be used.

{% # BaadMay CSS/JS Start %}
{{ 'baadmay-styles.css' | asset_url | preload_tag: as: 'style', type: 'text/css' }}
<link rel="stylesheet" href="{{ 'baadmay-styles.css' | asset_url }}">
    
{{ 'baadmay-script.js' | asset_url | preload_tag: as: 'script', type: 'text/javascript' }}
<script src="{{ 'baadmay-script.js' | asset_url }}" defer></script>
{% # BaadMay CSS/JS End %}

HOW TO RENDER `collection-widget`:
{% render 'two-liner-widget' %}

IF YOU WANT TO APPLY THE LIMIT THEN USE THIS CODE:

{% # BaadMay Product Widget Start # %}
{% assign max_limit = product.selected_or_first_available_variant.price | divided_by: 100 | times: 1 %}
{% if max_limit <= 20000 %}
   {% render 'two-liner-widget' %}
{% endif %}
{% # BaadMay Product Widget End # %}
