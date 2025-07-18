<p align="center">
  <a href="https://integrify.mmzeynalli.dev/"><img width="400" src="https://raw.githubusercontent.com/Integrify-SDK/integrify-docs-python/main/docs/az/docs/assets/integrify.png" alt="Integrify"></a>
</p>
<p align="center">
    <em>Integrify API inteqrasiyalarını rahatlaşdıran sorğular kitabaxanasıdır. Bu kitabxana EPoint inteqrasiyası üçün nəzərdə tutulmuşdur.</em>
</p>
<p align="center">
<a href="https://github.com/Integrify-SDK/integrify-epoint-python/actions/workflows/test.yml" target="_blank">
    <img src="https://github.com/Integrify-SDK/integrify-epoint-python/actions/workflows/test.yml/badge.svg?branch=main" alt="Test">
</a>
<a href="https://github.com/Integrify-SDK/integrify-epoint-python/actions/workflows/publish.yml" target="_blank">
    <img src="https://github.com/Integrify-SDK/integrify-epoint-python/actions/workflows/publish.yml/badge.svg" alt="Publish">
</a>
<a href="https://pypi.org/project/integrify-epoint" target="_blank">
  <img src="https://img.shields.io/pypi/v/integrify-epoint?color=%2334D058&label=pypi%20package" alt="Package version">
</a>
<a href="https://app.netlify.com/sites/integrify-docs/deploys">
  <img src="https://api.netlify.com/api/v1/badges/d8931b6a-80c7-41cb-bdbb-bf6ef5789f80/deploy-status" alt="Netlify Status">
</a>
</p>
<p align="center">
<a href="https://pepy.tech/project/integrify-epoint" target="_blank">
  <img src="https://static.pepy.tech/badge/integrify-epoint" alt="Downloads">
</a>
<a href="https://pypi.org/project/integrify-epoint" target="_blank">
    <img src="https://img.shields.io/pypi/pyversions/integrify-epoint.svg?color=%2334D058" alt="Supported Python versions">
</a>
<a href="https://coverage-badge.samuelcolvin.workers.dev/redirect/Integrify-SDK/integrify-epoint-python" target="_blank">
    <img src="https://coverage-badge.samuelcolvin.workers.dev/Integrify-SDK/integrify-epoint-python.svg" alt="Coverage">
</a>

</p>

---

**Dokumentasiya**: [https://integrify.mmzeynalli.dev](https://integrify.mmzeynalli.dev)

**Kod**: [https://github.com/Integrify-SDK/integrify-epoint-python](https://github.com/Integrify-SDK/integrify-epoint-python)

---

## Əsas özəlliklər

- Kitabxana həm sync, həm də async sorğu dəyişimini dəstəkləyir.
- Kitabaxanadakı bütün sinif və funksiyalar tamamilə dokumentləşdirilib.
- Kitabaxanadakı bütün sinif və funksiyalar tipləndirildiyindən, "type hinting" aktivdir.
- Sorğuların çoxunun məntiq axını (flowsu) izah edilib.

---

## Kitabxananın yüklənməsi

<div class="termy">

```console
$ pip install integrify-epoint
```

</div>

## İstifadəsi

Məsələn, sorğuları istifadə etmək istərsək:

### Sync

```python
from integrify.epoint import EPointRequest

resp = EPointRequest.pay(amount=100, currency='AZN', order_id='12345678', description='Ödəniş')
print(resp.ok, resp.body)

```

### Async

```python
from integrify.epoint import EPointAsyncRequest

# Async main loop artıq başlamışdır
resp = await EPointAsyncRequest.pay(amount=100, currency='AZN', order_id='12345678', description='Ödəniş')
print(resp.ok, resp.body)

```

### Sorğu cavabı

Yuxarıdakı sorğuların (və ya istənilən sorğunun) cavab formatı `ApiResponse` class-ıdır:

```python
class ApiResponse:
    ok: bool
    """Cavab sorğusunun statusu 400dən kiçikdirsə"""

    status_code: int
    """Cavab sorğusunun status kodu"""

    headers: dict
    """Cavab sorğusunun header-i"""

    body: Dəyişkən
    """Cavab sorğusunun body-si"""
```

> [!Caution]
> Bütün sorğular rəsmi dokumentasiyalara uyğun yazılsalar da, Integrify qeyri-rəsmi API klient-dir.

## Dəstəklənən başqa API inteqrasiyaları

<!-- AUTO-UPDATE SECTION -->