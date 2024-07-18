<p align="center">
  <img src="https://github.com/esrayildiizz/Example/assets/106755194/e0197438-b265-449a-a90b-cf4f526a0e01" alt="PAYGATE Image"/>
</p>

<p align="center">
<strong>PAYGATE</strong>
</p>

<p align="center">
PayGate ile tüm online ödemelerinizi tek merkezden yönetin 
</p>
<p align="center">
katma değerli servislerimiz ile ödeme giderlerinizi azaltın, cironuzu artırın ve işletmenizi büyütün.
</p>

## PAYGATE
[![Paygate Dotnet CI](https://img.shields.io/badge/Paygate%20Dotnet%20CI-passing-brightgreen)]()
[![nuget](https://img.shields.io/badge/nuget-v1.0.61-blue)]()


## Gereksinimler
- .NET Standart 2.0
- .NET Core 8 (Tests ve Web projeleri için)

## Kurulum
`Install-Package  ...... `



## Kullanım
PayGate API'sine erişmek için öncelikle API kimlik bilgilerini (örneğin bir API anahtarı ve gizli anahtar) edinmeniz gerekir. 

API kimlik bilgilerinizi aldıktan sonra, PayGate kimlik bilgilerinizle bir örnek oluşturarak PayGate'i kullanmaya başlayabilirsiniz.

## Örnekler

### Kredi Kartı Ödeme Kullanım Örneği

```java
PaymentService _payment = new PaymentService();
CreatePaymentInput request = new CreatePaymentInput();
request.setAmount(new BigDecimal("100.0"));
request.setPaidAmount(new BigDecimal("100.0"));
request.setWalletAmount(new BigDecimal("0.0"));
request.setInstallment(1);
request.setConversationId("456d1297-908e-4bd6-a13b-4be31a6e47d5");
request.setCurrency(Currency.TRY);
request.setPaymentGroup(PaymentGroup.LISTING_OR_SUBSCRIPTION);

CardDto card = new CardDto();
card.setCardHolderName("Haluk Demir");
card.setCardNumber("5258640000000001");
card.setExpireYear("2044");
card.setExpireMonth("07");
card.setCvc("000");
request.setCard(card);

CreatePaymentResponse response = _payment.createPaymentAsync(request);
Assert.assertNotNull(response);
```


### Katkılar
For all contributions to this client please see the contribution guide here.

## Lisans

*MIT*
