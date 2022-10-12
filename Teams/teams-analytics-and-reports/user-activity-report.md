---
title: Rapport d’activité des utilisateurs de Microsoft Teams
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
description: Découvrez comment utiliser le rapport d’activité des utilisateurs Teams dans le Centre d’administration Microsoft Teams pour voir comment les utilisateurs de votre organisation utilisent Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3bd00dd9cf05adea6d37ad07c1a22c3000d78e94
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532384"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport d’activité des utilisateurs Teams donne un aperçu des types d’activités que les utilisateurs de votre organisation effectuent dans Teams. Vous pouvez voir combien d’utilisateurs communiquent de façon non planifiée via des réunions non planifiées (appels de groupe et 1:1). Découvrez le nombre de réunions qu’un utilisateur Teams a organisées et les réunions aux quelles un utilisateur Teams a participé. Consultez des détails sur les minutes d’écran, vidéo et audio, ainsi que les statistiques de communication de conversation, telles que le nombre d’utilisateurs qui répondent aux messages de canal et les messages de canal, et le nombre d’utilisateurs qui s’engagent dans des messages de conversation 1:1 ou de groupe.

Avec des informations supplémentaires sur les utilisateurs internes et externes, vous pouvez désormais mesurer l’interaction des utilisateurs dans les [canaux partagés](/Teams/shared-channels.md) internes et externes, par exemple, les métriques telles que le nom de locataire auquel l’utilisateur appartient, les noms de locataires externes où l’utilisateur interagit et si l’utilisateur est externe au locataire aideront les administrateurs à mesurer l’inteaction des utilisateurs via les fonctionnalités de canal partagé. 

> [!NOTE]
> La possibilité de planifier un rapport d’activité utilisateur n’est pas disponible pour l’instant.

## <a name="view-the-user-activity-report"></a>Afficher le rapport d’activité de l’utilisateur

Vous devez être administrateur général, lecteur général ou administrateur du service Teams pour afficher le rapport dans le Centre d’administration Microsoft Teams. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Analytics & rapports** > **d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **l’activité de l’utilisateur Teams**.
2. Sous **Plage de dates**, sélectionnez une plage, puis **sélectionnez Exécuter le rapport**.

    ![Capture d’écran du rapport d’activité des utilisateurs Teams dans le Centre d’administration Teams avec des légendes.](../media/teams-reports-user-activity-with-callouts2.png "Capture d’écran du rapport d’activité des utilisateurs Teams dans le Centre d’administration Teams avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

| **Légende** |**Description**  |
|--------|-------------|
|**1**   |Le rapport d’activité des utilisateurs Teams peut être consulté pour les tendances des 7, 30, 90 ou 180 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures à partir de l’heure d’activité. |
|**3**   |Les données de série chronologique représentées dans le graphique supérieur montrent différentes métriques d’utilisation agrégées pour l’ensemble du locataire. |
|**4**   |Les données tabulaires représentées dans la moitié inférieure affichent différentes métriques d’utilisation agrégées par utilisateur. |
|**5**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**6**   | Chacune des métriques est représentée dans le graphique au niveau du locataire. Filtrez ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Sélectionnez **Les messages de canal**, **les messages de réponse**, les  **messages de conversation** ou **les réunions organisées** , etc. pour afficher les informations relatives à chacune d’elles. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**7**   |Le tableau vous donne une répartition de l’utilisation par utilisateur.   <ul><li>**Le nom d’utilisateur** est l’adresse e-mail de l’utilisateur. Consultez [la section suivante](#make-the-user-specific-data-anonymous) pour obtenir des conseils sur la façon de l’anonymiser.  Sélectionnez le nom d’utilisateur pour accéder à la page des détails de l’utilisateur.</li><li>**Le nom du locataire** (nouveau) est le nom d’un locataire interne ou externe auquel appartient un utilisateur. Si un utilisateur appartient à un locataire externe, différentes métriques d’utilisation (par exemple, les messages postaux, les messages de réponse, etc.) sont calculées en fonction de ses interactions dans un ou plusieurs canaux partagés du locataire de l’administrateur. Les interactions effectuées par un utilisateur externe dans son propre locataire ne sont pas prises en compte pour le rapport d’utilisation administrateur d’un locataire donné.  </li><li>**Les noms de locataire de canal partagé** (nouveau) sont les noms des locataires internes ou externes auxquels l’utilisateur a participé dans le cadre d’un canal partagé.</li><li>**Les messages de canal** sont le nombre de messages uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Les réponses** correspondent au nombre de messages de réponse uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li> <li>**Les publications** sont le nombre de messages post uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Les messages de conversation** correspondent au nombre de messages uniques que l’utilisateur a publiés dans une conversation privée pendant la période spécifiée.</li><li>**Les messages urgents** sont le nombre de messages urgents que l’utilisateur a publiés dans une conversation pendant la période spécifiée.</li><li>**Le nombre total de réunions organisées** correspond à la somme des réunions planifiées, périodiques, non planifiées et non classées qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Les réunions organisées une seule fois** sont le nombre de réunions planifiées uniques qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Les réunions planifiées périodiques** sont le nombre de réunions périodiques organisées par un utilisateur pendant la période spécifiée.</li><li>**L’adhoc des réunions organisées** correspond au nombre de réunions non planifiées qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Le nombre total de réunions participantes** correspond à la somme des réunions planifiées, périodiques, non planifiées et non classées à laquelle un utilisateur a participé pendant la période spécifiée.</li><li>**Les réunions aux réunions planifiées une seule fois** sont le nombre de réunions planifiées uniques aux cours de la période spécifiée par un utilisateur.</li><li>**Les réunions planifiées périodiques sont** le nombre de réunions périodiques aux laquelle un utilisateur a participé pendant la période spécifiée.</li><li>Le nombre de **réunions aux laquelle un utilisateur a participé** au cours de la période spécifiée est le nombre de réunions non planifiées aux cours des réunions.</li><li>**Les appels 1:1** sont le nombre d’appels 1:1 auxquels l’utilisateur a participé pendant la période spécifiée.</li><li>**La durée audio** est la durée audio totale (en minutes) à laquelle l’utilisateur a participé pendant la période spécifiée.</li><li>**Le temps vidéo** est le temps vidéo total (en minutes) auquel l’utilisateur a participé pendant la période spécifiée.</li><li>**Le temps de partage** d’écran est le temps total de partage d’écran (minutes) auquel l’utilisateur a participé pendant la période spécifiée.</li>  <li>**La dernière activité** est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li><li>**Les autres activités** s’assurent du suivi lorsque l’utilisateur est considéré comme actif, mais qu’il a la valeur zéro pour les messages de conversation, les appels 1:1, les messages de canal, le nombre total de réunions et les réunions organisées. Des exemples d’actions sont lorsqu’un utilisateur modifie l’état Teams ou le message d’état Teams, lorsqu’un utilisateur ouvre un message de canal mais ne lui répond pas, ou lorsqu’un utilisateur reçoit un message privé et le lit, mais ne répond pas à celui-ci.</li> </ul> **Les réunions non classées** sont celles qui ne peuvent pas être identifiées comme planifiées, périodiques ou non planifiées. Ils sont peu nombreux et ne peuvent souvent pas être identifiés en raison d’informations de télémétrie imparfaites.<br><br>**Les appels de groupe** ont été **remplacés par les réunions organisées adhoc** et **les réunions ont participé à l’adhoc**. La somme de ces deux valeurs est égale à ce qui a été mesuré par **les appels de groupe**. <br/><br/>Notez que si un utilisateur n’existe plus, le nom s’affiche sous la forme « - » dans le tableau.
|**8**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
**9**   |Exportez le rapport vers un fichier CSV pour une analyse hors connexion. Sélectionnez **Exporter vers Excel** et le rapport sera téléchargé dans votre navigateur. <br>Lorsque vous affichez le rapport dans Excel, vous voyez également une colonne **d’ID d’utilisateur** , qui représente l’ID utilisateur. Un ID d’utilisateur est généralement une chaîne alphanumérique. |


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques à l’utilisateur anonymes

Pour rendre les données du rapport d’activité utilisateur Teams anonymes, vous devez être administrateur général. Le Administrateur général peut masquer les informations d’identification (à l’aide de hachages MD5) telles que le nom d’affichage, le nom du groupe, l’e-mail et l’ID AAD dans les rapports et leur exportation.

1. Dans Centre d'administration Microsoft 365, accédez aux **paramètres de l’organisation** **Paramètres** \> et, sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis choisissez **d’afficher les noms d’utilisateur, de groupe et de site masqués dans tous les rapports**. Ce paramètre est appliqué aux rapports d’utilisation dans Centre d'administration Microsoft 365 et au Centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.


> [!NOTE]
> L’activation de ce paramètre dé-identifie les informations de nom d’utilisateur, de groupe et de site dans le [rapport d’activité de l’utilisateur Teams](user-activity-report.md), le [rapport d’utilisation des appareils Teams](device-usage-report.md) et [le rapport d’utilisation teams](teams-usage-report.md) . À compter du 1er septembre 2021, ce paramètre est activé par défaut pour tous dans le cadre de notre engagement continu à protéger les informations importantes et à permettre aux entreprises de soutenir leurs lois locales sur la confidentialité. Ce paramètre s’applique également aux rapports d’utilisation de Microsoft 365 dans les Centre d'administration Microsoft 365, Microsoft Graph et Power BI.
## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
