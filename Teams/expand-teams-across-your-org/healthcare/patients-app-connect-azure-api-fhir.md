---
title: Connecter l’application coordination des soins à l’API Azure pour FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Découvrez comment connecter l’application patients dans Microsoft teams à l’API Azure pour FHIR (ressources d’interopérabilité Fast Healthcare).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 29447791a8ba169bfc50173b249b3f8b987c7a17
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803552"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Connecter l’application coordination des soins à l’API Azure pour FHIR

> [!NOTE]
> À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe. Toutes les données associées à l’application patients sont conservées dans ce groupe, mais vous ne pouvez plus y accéder par le biais de l’interface utilisateur. Les utilisateurs peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale. Consultez le modèle patients dans les listes pour commencer. Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).

Suivez ces étapes pour autoriser l’application patients dans Microsoft teams à accéder à une API Azure pour l’instance FHIR. Cet article part du principe que vous disposez d’une [API Azure pour](https://azure.microsoft.com/services/azure-api-for-fhir/) la configuration de l’instance FHIR et qu’elle est configurée dans votre client.  Si vous n’avez pas encore créé d’API Azure pour FHIR dans votre client, reportez-vous à [démarrage rapide : déployer l’API Azure pour FHIR à l’aide d’Azure Portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).


1. Cliquez [ici](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) pour accorder l’autorisation d’administrateur pour l’application patients. Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur client ou d’administrateur général, puis cliquez sur **accepter** pour accorder les autorisations requises.

    ![Capture d’écran de la demande d’autorisation pour l’application patients](../../media/patients-app-permissions-request.png)

    Fermez la fenêtre après l’avoir acceptée. Une page peut ressembler à ce qui suit. Vous pouvez ignorer le message d’erreur sur la page. C’est inoffensif et indique que cette autorisation est accordée. (Nous travaillons actuellement sur une page plus conviviale pour cette URL. Restez informé !)

    ![Capture d’écran d’une demande d’autorisation pour l’application patients](../../media/patients-app-permissions-request-granted.png)
    
2. Connectez-vous au [portail Azure](https://portal.azure.com) à l’aide de vos informations d’identification d’administrateur.

3. Dans le volet de navigation de gauche, cliquez sur **Azure Active Directory** , puis sélectionnez **applications d’entreprise** .

    Recherchez une ligne nommée **patients (dev)** , puis copiez la valeur de la colonne **ID d’objet** dans le presse-papiers.
    
    ![Capture d’écran de la ligne patients (dev) dans Azure Portal](../../media/patients-app-azure-portal-object-id.png)
    
4. Accédez à l’instance d’API Azure pour FHIR à laquelle vous voulez connecter l’application patients (en effectuant une recherche ou en naviguant dans vos ressources), puis ouvrez les paramètres de cette instance.

    ![Capture d’écran de l’API Azure pour les paramètres d’instance FHIR dans Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Cliquez sur **authentification** , puis collez l’ID d’objet que vous avez copié à l’étape 3 dans la zone **ID d’objet autorisés** . Cela permet à l’application patients d’accéder au serveur FHIR. Après avoir collé l’ID d’objet, Azure Active Directory le valide et une coche verte apparaît à côté de celui-ci.

    ![Capture d’écran des paramètres d’authentification dans le portail Azure](../../media/patients-app-azure-portal-authentication.png)

6. Cliquez sur **Enregistrer** . Cette opération redéploie l’instance, qui peut prendre quelques minutes.

7. Cliquez sur **vue d’ensemble** , puis copiez l’URL à partir du **point de terminaison de métadonnées FHIR** . Supprimez la balise Metadata pour obtenir l’URL du serveur FHIR. Par exemple, https://test02-teamshealth.azurehealthcareapis.com/ . 

    ![Capture d’écran du point de terminaison de métadonnées dans Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. Dans Teams, accédez à l’instance d’application patients qui est chargée dans votre équipe, cliquez sur **paramètres** , puis dans la zone **lien** , entrez l’URL du point de terminaison du serveur FHIR. Cliquez ensuite sur **connexion** pour établir une connexion et Rechercher et ajouter des patients à votre liste.  

    ![Capture d’écran des paramètres de l’application patients dans teams](../../media/patients-app-teams.png)
    
    Si vous obtenez un message d’erreur lors de la connexion à teams au cours de cette étape, vous pouvez envoyer une capture d’écran détaillée de l’erreur, des journaux de [Fiddler](https://www.telerik.com/download/fiddler) et de toutes les autres étapes de reproduction dans un courrier électronique avec une ligne d’objet de «application patients – résolution de EMR en mode [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Sujets associés

- [Présentation de l’application Patients](patients-app-overview.md)
- [Intégration des dossiers médicaux électroniques dans Microsoft Teams](patients-app.md)
