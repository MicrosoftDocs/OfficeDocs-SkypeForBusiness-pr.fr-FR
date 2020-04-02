---
title: Créer une application de portail intranet d’équipe à partir d’une page ou d’un site SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Prenez un site ou une page SharePoint Online existant et créez un onglet statique autonome qui peut être utilisé comme portail intranet pour votre organisation.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106631"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Créer une application de portail intranet d’équipe à partir d’une page ou d’un site SharePoint Online

Suivez les étapes décrites dans cet article pour créer une application autonome et statique dans une équipe qui pointe vers le site intranet de votre organisation.

Une *application personnelle teams* de votre site intranet SharePoint est créée et s’affiche sous la forme d’un onglet à l’intérieur de teams. Cet onglet peut contenir des informations importantes pour tous les utilisateurs de votre équipe. C’est un moyen rapide et pratique pour les utilisateurs de teams d’accéder aux mises à jour, cliquez sur un onglet.

Sachez que le processus présenté **doit utiliser** un site ou une page SharePoint *moderne* pour fonctionner. Ce processus n’est pas disponible pour les pages ou sites *classiques* .

> [!IMPORTANT]
> Assurez-vous que le chargement hors Windows Store des applications teams est activé pour votre client. En fonction de l’endroit où vous vous trouvez dans le processus de migration du portail d’administration Teams, vous devrez peut-être l’activer sous équipes > administrateur, ou sous paramètres de > d’administration > services et compléments > les applications Microsoft teams > applications > applications externes, dans la version précédente du portail. 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Utiliser app Studio pour créer votre application SharePoint Online autonome
Avant de commencer :
1. Vous devez connaître l’URL d’une communication moderne SharePoint Online ou d’un site d’équipe ou d’une page.
    - Les chemins d’accès de ces sites seront toujours */équipes* ou */sites/* .

2. Vous devez connaître le sous-domaine de votre client, qui sera utilisé dans l’espace réservé **{{subdomain}}**.

3. Cet article utilise l’espace réservé **{{SiteUrl}}** pour vous en êtes l' *URL* du site ou de la page que vous avez choisi.
    - Exemples d' *URL*: https://contoso.sharepoint.com/teams/Contoso *ou*   https://contoso.sharepoint.com/sites/Contoso 
4. Par ailleurs, **{{sitePath}}** sera utilisé pour indiquer le *chemin d’accès* de l’URL (par exemple:/teams/Contoso).
    - Exemples de *chemins*:/teams/Contoso *ou* /sites/contoso 

Commencez par suivre les étapes ci-dessous :

1. Accédez au magasin d’équipes.

2. Installez ou ouvrez App Studio.

3. Cliquez sur **ouvrir**, en regard de l’option application.

4. Avec App studio ouvert, cliquez sur **éditeur de manifeste**.

5. **Créer une nouvelle application**.

6. Renseignez les **Détails**de l’application.

7. Cliquez sur les **onglets** sous capacités.

8. Dans l’onglet personnel, cliquez sur **Ajouter** .

9. Entrez le **nom** et choisissez **un nouvel ID d’entité unique**.

10. Entrez l' **URL du site Web contentURL et**. 

- **contentUrl**: {{SiteUrl}}/_layouts/15/teamslogon.aspx ? SPFX = true&dest = {{sitePath}}  
- **web’iteUrl**: {{SiteUrl}} ' 'exemple **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. Accédez à **Domains et Permissi’ns**. Assurez-vous que la section domaines valides contient votre nom de domaine SharePoint Online.
' 'Exemple : contoso.sharepoint.com

12. Ajoutez les propriétés **d’authentification unique suivantes de** l’application Web à l’aide de' 'exemple : ' ' ' 'ID de l' **application AAD**: URL de la **ressource**00000003-0000-0ff1-CE00-000000000000 : {{subdomain} ![}. SharePoint. com' ' 'Web App unique, avec ID et URL](media/personal-app.png)

13. **Enregistrez** ces propriétés, puis naviguez vers le **test et la distribution**. 

14. Installez l’application pour tester l’application personnellement.

> [!IMPORTANT]
> Si vous n’utilisez pas le logiciel teams Studio, vous devez. zip du manifeste. Fichier JSON que vous venez de créer, accédez au magasin d’applications dans Microsoft Teams, puis cliquez sur Télécharger un lien vers une **application personnalisée** (en bas à droite de l’App Store). Cela vous permettra d’accéder à l’application.

15. L’application est désormais disponible sous la forme d’un onglet statique que vous pouvez charger et afficher dans Teams.

## <a name="test-and-view-your-new-static-tab"></a>Tester et afficher votre nouvel onglet statique

Pour afficher l’onglet nouveau sur le bureau Teams, accédez aux points de suspension (**...**) sur le côté gauche de la barre de l’application. Recherchez votre nouvelle application, chargez-la et testez-la dans Teams.

Si vous souhaitez que la nouvelle application soit disponible dans le menu de gauche, vous devez utiliser un paramètre de stratégie d’application pour cela. Ce paramètre est disponible dans la section Administration de l’équipe > stratégie de l’application > ajouter une application épinglée. Lorsque vous affectez la stratégie à un utilisateur à des fins de test, cette modification est affichée plus de 24 heures. Dans cet esprit, nous vous conseillons de décider de l’endroit où l’application doit apparaître pour vous permettre d’éviter des retards.

Pour afficher et tester la nouvelle application sur un appareil mobile, ouvrez le tiroir de l’application en appuyant sur**^** le Chevron () situé au-dessus de la barre d’onglets en bas de votre écran. Recherchez votre application et accédez-y sur votre appareil mobile.
        
> [!CAUTION]
> La prise en charge des appareils mobiles est actuellement dans la version préliminaire du développeur. Pour activer l’aperçu des développeurs, accédez à paramètres > à propos de et activez le mode aperçu des développeurs.

## <a name="a-sample-manifestjson-file"></a>Exemple de fichier manifest. JSON

Le fichier JSO que vous générez ressemble à ce qui suit.

```JSON'
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso" 

    },                     
                        
    "des    ription": {                 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 
''
    "staticTabs": [ 

        { 
                                       
                     "       nti        Id":       "com    unicat    onSi    eTab", 
                                       
            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```