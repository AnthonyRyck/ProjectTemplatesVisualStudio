# MySQL Template

Un projet Blazor Server avec une base de données MySQL et l'authentification "Comptes Individuel".

- Les logs sont fait avec [Serilog](https://serilog.net/).
- J'ai "Scaffolding" toutes les pages Identity.
- La connexion (_Login_) se fait sur le "UserName" avec Identity, et non plus sur l'Email.
- La base de données SQLite est créée au démarrage de l'application et est mise dans un répertoire "Database", pour simplifier dans le cas ou l'application serait dans un container.  
- A la création de la base de données, un utilisateur "root" est injecté et il a le rôle "Admin"
```csharp
var poweruser = new IdentityUser
                {
                    UserName = "root",
                    Email = "root@email.com",
                    EmailConfirmed = true
                };
string userPwd = "Azerty123!";
var createPowerUser = await userManager.CreateAsync(poweruser, userPwd);
```
- J'ai traduit les pages de Login, Register,... en français.
