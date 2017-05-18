# sparkpost-sdk-dotnet
SparkPost Sdk para .Net Core

SDK baseado https://github.com/RoushTech/SparkPostDotNet,com leves alteração.
A documentação  a mesma.

Não esqueça de alterar a API Key no arquivo SparkPostClient

Exemplo 
# Sending an e-mail

``` csharp
public static async void SendEmail(string email, string contentHtml, string title)
  {
      try
      {
          var transmission = new Transmission();
          transmission.Content.From.EMail = "email";
          transmission.Content.From.Name = "name";
          transmission.Content.Subject = title;
          transmission.Content.Html = contentHtml;
          var recipient = new Recipient {Address = {EMail = email}};
          transmission.Recipients.Add(recipient);
          var spark = new SparkPostClient();
          await spark.CreateTransmission(transmission);

      }
      catch(Exception e)
      {
          Console.WriteLine("Erro de envio de email");
      }

  }
  ```
