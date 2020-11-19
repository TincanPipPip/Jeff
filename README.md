# Shopify-Template

---

-- If you are starting from scratch and want to get a quick start, run the following:

    theme new --password=[your-password] --store=[your-store.myshopify.com] --name=[theme name]

    This will link the your shopify template to a shopify account, creating a config.yml file.

    Your configuration will be setup per environment. Here is an example config file for you to understand the usage of environments and config


    development:
        password: 16ef663594568325d64408ebcdeef528
        theme*id: "123"
        store: can-i-buy-a-feeling.myshopify.com
        proxy: http://localhost:3000
        ignore_files: - "*.gif" - "\_.jpg" - config/settings_data.json
    production:
        password: 16ef663594568325d64408ebcdeef528
        theme_id: "456"
        store: can-i-buy-a-feeling.myshopify.com
        timeout: 60s
        readonly: true
    test:
        password: 16ef663594568325d64408ebcdeef528
        theme_id: "789"
        store: can-i-buy-a-feeling.myshopify.com
        ignores: ignore.txt

-- Add this the bottom of your config.yml file, which will now be in the root directory of your theme

    ignore_files: - config/settings_data.json

    **\*** (if working on an existing site)
    Download theme file from the shopify admin area
    url: /admin/themes -> actions -> download theme file
    extract all files and directories from the theme file download
    copy downloaded directories into your theme - merging/overwriting any conflicting files or directories

-- Run npm install in the root of your template

-- add these tags to you theme.liquid file
directory location: root/layout/theme.liquid

    {{ 'styles.scss.css' | asset_url | stylesheet_tag }}
    {{ 'application.scss.css' | asset_url | stylesheet_tag }}
    {{ 'application.js' | asset_url | script_tag }}

-- Run theme deploy --env=development --allow-live
to deploy your new directory and file structure to the live theme on your chosen dev site

-- To begin development

    In one terminal I start the gulp task with gulp
    In another terminal I use theme watch to upload any changes with Themekit to my theme.

REFERENCES:
theme kit setup:
https://shopify.github.io/themekit/

gulp setup:
https://dev.to/roroland/setup-a-local-dev-environment-to-work-with-shopify-themes-without-messing-your-workflow-5gah
http://www.codeshopify.com/blog_posts/using-gulp-for-sass-compilation-allows-for-sass-partials-with-liquid-tags
