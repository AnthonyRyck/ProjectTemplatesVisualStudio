# Project Templates for Visual Studio

Il y aura plusieurs projet pour avoir la base pour la cr�ation de templates de projet pour Visual Studio.

### Projets
- **TemplateSqlite** : un projet Blazor Server avec une base de donn�es SQLite et l'authentification "Comptes Individuel".



### Choses communes

- Les logs sont fait avec [Serilog](https://serilog.net/).
- J'ai "Scaffolding" toutes les pages Identity.
- La connexion (_Login_) se fait sur le "UserName" avec Identity, et non plus sur l'Email.
- La base de donn�es SQLite est cr��e au d�marrage de l'application et est mise dans un r�pertoire "Database", pour simplifier dans le cas ou l'application serait dans un container.  
- A la cr�ation de la base de donn�es, un utilisateur "root" est inject� et il a le r�le "Admin"
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
- J'ai traduit les pages de Login, Register,... en fran�ais.