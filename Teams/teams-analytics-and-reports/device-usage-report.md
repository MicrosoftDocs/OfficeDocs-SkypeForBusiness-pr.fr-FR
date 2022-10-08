---
title: Rapport d’utilisation des périphériques de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation des appareils Teams dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation se connectent à Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033802"
---
# <a name="microsoft-teams-device-usage-report"></a>Rapport d’utilisation des périphériques de Microsoft Teams

Le rapport d’utilisation des appareils Teams dans le Centre d’administration Microsoft Teams vous fournit des informations sur la façon dont les utilisateurs se connectent à Teams. Vous pouvez utiliser le rapport pour voir les appareils utilisés au sein de votre organisation, y compris le nombre d’utilisateurs de Teams à partir de leurs appareils mobiles en déplacement.  

## <a name="view-the-device-usage-report"></a>Afficher le rapport d’utilisation de l’appareil


Vous devez être administrateur général, lecteur général ou administrateur du service Teams pour afficher les rapports dans le Centre d’administration Teams. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.


1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analyse & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des appareils Teams**.
2. Dans **Plage de dates**, sélectionnez une plage puis cliquez sur **Exécuter le rapport**.

    ![Capture d’écran du rapport d’utilisation des appareils Teams dans le Centre d’administration Teams avec des légendes.](../media/teams-reports-device-usage-with-callouts.png "Capture d’écran du rapport d’utilisation des appareils Teams dans le Centre d’administration Teams avec des légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’utilisation des appareils Teams peut être consulté pour les tendances des 7, 30, 90 et 180 derniers jours.  |
|**2**   |Chaque rapport a une date de génération du rapport. Les rapports reflètent généralement une latence de 24 à 48 heures à partir de l’heure d’activité. |
|**3**   |<ul><li>L’axe X du graphique représente les différents appareils (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) utilisés pour se connecter à Teams. </li><li>L’axe Y correspond au nombre d’utilisateurs utilisant l’appareil sur la période sélectionnée.</li> </ul>Pointez sur la barre représentant un appareil pour voir le nombre d’utilisateurs qui utilisent l’appareil pour se connecter à Teams.|
|**4**   |Le tableau vous donne une répartition de l’utilisation de l’appareil par utilisateur. <ul><li>**Le nom d’utilisateur** est le nom complet de l’utilisateur. Vous pouvez cliquer sur le nom d’affichage pour accéder à la page de paramètres de l’utilisateur dans le Centre d’administration Microsoft Teams. </li><li>**Windows** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur Windows.</li><li>**Mac** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur macOS. </li> <li>**Linux** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur Linux. </li> <li>**iOS** est sélectionné si l’utilisateur était actif sur le client mobile Teams pour iOS.</li><li>**Le téléphone Android** est sélectionné si l’utilisateur était actif sur le client mobile Teams pour Android.</li><li>**Le système d’exploitation Chrome** est sélectionné si l’utilisateur était actif dans le client de bureau Teams sur un ordinateur ChromeOS.</li><li>**Le web** est sélectionné si l’utilisateur était actif sur le client web Teams. <li>**La dernière activité** est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li> </ul> Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur s’affiche comme « - » dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
|**6**   |Exportez le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez l’icône **Exporter vers Excel** et le rapport sera téléchargé dans votre navigateur.|
|**7** |Les données de série chronologique représentées dans le graphique supérieur montrent différentes métriques d’utilisation agrégées pour l’ensemble du locataire|
|**8** |Les données tabulaires représentées dans la moitié botton affichent différentes métriques d’utilisation agrégées par utilisateur|


## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour rendre les données du rapport d’activité utilisateur Teams anonymes, vous devez être administrateur général. L’administrateur général peut masquer les informations d’identification (à l’aide de hachages MD5) telles que le nom d’affichage, le nom du groupe, l’e-mail et l’ID AAD dans le rapport et son exportation.

1. Dans Centre d'administration Microsoft 365, accédez aux **paramètres de l’organisation** **Paramètres** \> et, sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis choisissez **Afficher les noms d’utilisateur, de groupe et de site masqués dans tous les rapports**. Ce paramètre est appliqué à la fois aux rapports d’utilisation dans Centre d'administration Microsoft 365 ainsi qu’au Centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.

> [!NOTE]
> L’activation de ce paramètre permet d’identifier les informations de nom d’utilisateur, de groupe et de site dans le [rapport d’activité de l’utilisateur Teams](user-activity-report.md), le [rapport d’utilisation des appareils Teams](device-usage-report.md) et [le rapport d’utilisation de Teams](teams-usage-report.md). À compter du 1er septembre 2021, ce paramètre est activé par défaut pour tout le monde dans le cadre de notre engagement continu à protéger les informations importantes et à permettre aux entreprises de soutenir leurs lois locales en matière de confidentialité. 
>
>Ce paramètre s’applique également aux rapports d’utilisation de Microsoft 365 dans Centre d'administration Microsoft 365, Microsoft Graph et Power BI.

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
