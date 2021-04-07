---
title: Créer une application de portail intranet Teams à partir d’un site ou d’une page SharePoint Online
author: cichur
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Prenez un site ou une page SharePoint Online et créez un onglet personnel autonome pouvant être utilisé comme portail intranet pour votre organisation.
localization_priority: Priority
ms.openlocfilehash: c6d138b1bf95edb619de6563f644e76ec123e3c6
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607537"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>Créer une application de portail intranet Teams à partir d’un site ou d’une page SharePoint Online

Suivez les étapes décrites dans cet article pour créer une application autonome et statique à l’intérieur de Teams qui crée un lien vers le site intranet de votre organisation.

Une *application personnelle Teams* de votre site intranet SharePoint est créée et apparaît sous forme d’onglet dans Teams. Cet onglet peut contenir des informations importantes pour les utilisateurs de tous les membres de votre Teams. Il s’agit d’un moyen rapide et commode pour les utilisateurs de Teams d'accéder aux mises à jour en un seul clic.

N’oubliez pas que le processus présenté **doit utiliser** un site ou page *Moderne* SharePoint. Ce processus n’est pas disponible pour les *sites ou pages* classiques.

> [!IMPORTANT]
> Assurez-vous que le chargement latéral des applications Teams est activé pour votre locataire. Selon l’endroit où vous vous trouvez dans le processus de migration du portail d’administration Teams, vous devrez peut-être l’activer soit sous Teams > Administrateur, soit sous Paramètres > Administration > Services et compléments > Microsoft Teams > Applications > Applications externes, dans la version précédente du portail.

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>Utilisez l’application Studio pour créer votre application SharePoint Online autonome

Avant de commencer :

1. Vous devez connaître l'URL d'un site ou d'une page de communication ou d'équipe moderne SharePoint Online.

   Les chemins d’accès de ces sites sont toujours */teams/* ou */sites/*.

2. Vous devez connaître le sous-domaine de votre client, lequel sera utilisé dans l’espace réservé **{{subdomain}}**.

3. Cet article utilise l’espace réservé **{{siteUrl}}** pour l’*URL* du site ou de la page que vous avez choisi.

   Exemple *URL* :
   
   - `https://contoso.sharepoint.com/teams/Contoso`
      <br/>*ou*
   - `https://contoso.sharepoint.com/sites/Contoso`
        
4. De plus, **{{sitePath}}** sera utilisé pour indiquer le *chemin d’accès* de l’URL (par exemple : /teams/Contoso).

   Exemple *trajectoires* :
   
   - /teams/Contoso
     <br/>*ou*
   - /sites/Contoso

Commencez par suivre les étapes ci-dessous :

1. Accédez au Store Teams.

2. Installez ou ouvrez App Studio.

3. Cliquez sur **Ouvrir**, en regard de l’option App.

4. Avec App studio ouvert, cliquez sur **Éditeur de manifeste**.

5. **Créer une nouvelle application**.

6. Renseignez tous les **Détails de l’application**.

7. Cliquez sur **Onglets** sous Fonctionnalités.

8. Cliquez sur **Ajouter** sous l’onglet Personnel.

9. Entrez le **Nom** puis sélectionnez **une nouvelle ID d’entité unique**.

10. Renseignez les **contentURL et URL du site web**.

    - **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
    
    - **websiteUrl**: {{siteUrl}}

      Exemple **contentURL** :
      
      `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. Accédez à la page **Domaines et autorisations**. Assurez-vous que la section domaines valides contient votre nom de domaine SharePoint Online.

    Exemple : `contoso.sharepoint.com`

12. Ajoutez les propriétés **Authentification unique** de l’application web suivante :

    Exemple :
    
    - **ID de l’application AAD** : 00000003-0000-0ff1-ce00-000000000000
    
    - **Url de ressource** : {{subdomain}}.sharepoint.com

      ![Authentification unique de l’application web avec ID et URL.](media/personal-app.png)

13. **Enregistrez** ces propriétés, puis accédez à **Tester et distribuer**.

14. Installez l’application pour tester l’application personnellement.

    > [!IMPORTANT]
    > Si vous n'utilisez pas Teams App Studio, vous devrez compresser le fichier manifest.JSON que vous venez de créer, accédez à l’App Store dans Teams, puis cliquez sur le lien **télécharger l’application personnalisée** (en bas à droite de l’App Store). L’application est alors disponible.

15. L’application est désormais disponible sous la forme d’un onglet personnel que vous pouvez charger et afficher dans Teams.

## <a name="test-and-view-your-new-personal-tab"></a>Tester et afficher votre nouvel onglet personnel

Pour afficher l’onglet nouveau sur le bureau Teams, accédez aux points de suspension (**...**) sur le côté gauche de la barre de l’application. Trouvez votre nouvelle application, chargez-la et testez-la dans Teams.

Si vous souhaitez que la nouvelle application soit disponible dans le menu de gauche à une position supérieure, vous devez utiliser un paramètre de stratégie d’application. Ce paramètre se trouve dans la section administrateur Teams > stratégie d’application > Ajouter une application épinglée. Lorsque vous attribuez la politique à un utilisateur pour le test, le changement apparaîtra quelques heures plus tard. À cet esprit, n’hésitez pas à choisir l’emplacement dans lequel l’application doit apparaître à votre guise pour éviter les retards.

Pour afficher et tester la nouvelle application sur un appareil mobile, ouvrez le tiroir de l’application en appuyant sur le chevron (**^**) au-dessus de la barre d’onglets située en bas de l’écran. Recherchez votre application et accédez-y sur votre appareil mobile.

## <a name="a-sample-manifestjson-file"></a>Exemple de fichier Manifest.JSON

Le fichier JSON que vous avez généré ressemble à celui ci-dessous.

```json
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.9/MicrosoftTeams.schema.json",

    "manifestVersion": "1.9",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso",

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet",

        "full": "Intranet Portal for Contoso"

    },

    "description": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

            "entityId": "communicationSiteTab",

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
