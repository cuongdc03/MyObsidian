
| id                                                                                     | hubs    | source                                                     |
| -------------------------------------------------------------------------------------- | ------- | ---------------------------------------------------------- |
| 202410181444_Define specific methods and return types for the queries you want to make | [[OOP]] | [[object_design_style_guide_matthias_noback.pdf#page=179]] |
Just keep smaller your method and make it like a module can resused
# not like this
```ts
final class CurrencyConverter
{
public function convert(Money money, Currency to): Money
{
httpClient = new CurlHttpClient();
response = httpClient.get(
'http://data.fixer.io/api/latest?access_key=...' .
'&base=' . money.currency().asString() .
'&symbols=' . to.asString()
);
decoded = json_decode(response.getBody());
rate = (float)decoded.rates[to.asString()];
return money.convert(to, rate);
}
}
```
# Must like this
```ts
final class FixerApi
{
public function exchangeRateFor(
Currency from,
Currency to
): ExchangeRate {
httpClient = new CurlHttpClient();
response = httpClient.get(/* ... */);
decoded = json_decode(response.getBody());
rate = (float)decoded.rates[to.asString()];
return ExchangeRate.from(from, to, rate);
}
}
final class ExchangeRate
{
public static function from(
Currency from,
Currency to,
float rate
): ExchangeRate {
// ...
}
final class CurrencyConverter
{
private FixerApi fixerApi;
public function __construct(FixerApi fixerApi)
{
this.fixerApi = fixerApi;
}
public function convert(Money money, Currency to): Money
{
exchangeRate = this.fixerApi
.exchangeRateFor(
money.currency(),
to
);
return money.convert(exchangeRate);
}
}
```
