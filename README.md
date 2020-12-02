# EN

## Scraping resmigazete.gov.tr Data Daily and Sending Mail to Registered Subscribers
### Thanks to its establishment on Herokuapp and Heroku Scheduler, it sends the official newspaper via web scraping at 05.00 and sends mail to its registered subscribers. 

------------------



The element xpath-id selections will be specific as the desired data will be specific when capturing data through the website.
For example, the element properties I use in [Turkey Official Newspaper Website](https://resmigazete.gov.tr/);

```
Official Newspaper Date and Number xpath    =     //h6/u/span[@id='spanGazeteTarih']
Daily Flow xpath                            =     //div[@id='gunluk-akis']
```


After the tags related to HTML Tag xpaths were on the page, we received HTML content with .get_'attribute ("innerHTML") 'as we wanted to send the ready HTML content and links as an e-mail.

We used MailChimp because it has easier integration with Wordpress to sign up to the subscriber list and keep registered subscribers.

Thanks to the MailChimp3 Python API, we can pull the entire registered subscriber list from MailChimp using the API code, username and the Audience ID with registered subscribers.

We then send the secure SMTP mail using the SMTPLib library to ensure that the e-mails sent do not fall into the spam box and reach registered subscribers.

We use the HTML content scraped while setting the mail content with SMTP.

Finally, every time you connect to the mail service again and again; For user mail privacy, we send mail to each user individually within the for loop.



[Click here](https://www.sinerjik.org/resmi-gazete-e-posta-hizmeti/) to sign up for the mailing list.

------------------



&nbsp;
&nbsp;



# TR

## resmigazete.gov.tr Verilerini Günlük Olarak Çekme ve Kayıtlı Abonelere Mail Gönderme
### Herokuapp üzerinde kurulmuş olması ve Heroku Scheduler sayesinde resmi gazeteyi 06.00'da web scraping ile çekip kayıtlı abonelerine mail atıyor.

------------------


Web sitesi üzerinden veri çekerken istenilen veri spesifik olacağından element xpath-id seçimleri de spesifik olacaktır.
Örneğin [Resmi Gazete](https://resmigazete.gov.tr/)'de kullandığım element özellikleri;

```
Resmi Gazete Tarihi ve Sayısı    =     //h6/u/span[@id='spanGazeteTarih']
Günlük Akış                      =     //div[@id='gunluk-akis']
```


HTML Tag xpath'leriyle ilgili tag'ler sayfada bulunduktan sonra, mail olarak hazır HTML içeriğini ve linklerini göndermek istediğimizden .get_'attribute("innerHTML")' ile HTML içeriğini aldık.

Abone listesine kaydolma ve kayıtlı aboneleri tutma konusunda Wordpress ile daha kolay entegrasyona sahip olduğu için MailChimp kullandık. 

MailChimp3 Python API'si sayesinde API kodunu, kullanıcı adını ve kayıtlı abonelerin bulunduğu Audience ID'sini kullanarak MailChimp'den tüm kayıtlı abone listesini çekebiliyoruz.

Sonrasında SMTPLib kütüphanesini kullanarak güvenli SMTP maili göndererek, gönderilen mail'lerin spam kutusuna düşmemesini ve kayıtlı abonelere ulaşmasını sağlıyoruz. 

SMTP ile mail içeriğini ayarlarken çekilen HTML içeriğini kullanıyoruz. 

Son olarak her seferinde mail seferinde tekrar mail serverine bağlanıp; kullanıcı mail gizliliği için for döngüsü içinde her kullanıcıya ayrı ayrı mail gönderiyoruz.



Mail listesine kaydolmak için [tıklayınız.](https://www.sinerjik.org/resmi-gazete-e-posta-hizmeti/)

------------------