# CommonMark Linkify

This extention to [CommonMark](https://commonmark.thephpleague.com) turns plain text URLs into clickable links.

## Usage

```php
use League\CommonMark\Converter;
use League\CommonMark\DocParser;
use League\CommonMark\Environment;
use League\CommonMark\HtmlRenderer;
use Jonnybarnes\CommonmarkLinkify\LinkifyExtension;

$environment = Environment::createCommonMarkEnvironment();
$environment->addExtension(new LinkifyExtension());

$converter = new Converter(new DocParser($environment), new HtmlRenderer($environment));

echo $converter->convertToHtml('Some text-only link https://example.org');
// Some text link <a href="https://example.org">example.org</a>
```