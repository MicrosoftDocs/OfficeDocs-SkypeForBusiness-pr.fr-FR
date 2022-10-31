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
ms.openlocfilehash: d353a49dc074f721e805e3269580f13b8663b85f
ms.sourcegitcommit: 57616ad45eaa8be7f78dd0126d324c8777c5a367
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68792803"
---
# <a name="microsoft-teams-user-activity-report"></a>Rapport d’activité des utilisateurs de Microsoft Teams

Le rapport d’activité des utilisateurs Teams fournit des informations sur les types d’activités que les utilisateurs de votre organisation effectuent dans Teams. Vous pouvez voir combien d’utilisateurs communiquent sur une base non planifiée par le biais de réunions non planifiées (1:1 et appels de groupe). Découvrez le nombre de réunions qu’un utilisateur Teams a organisées et les réunions à laquelle un utilisateur Teams a participé. Consultez des détails sur les minutes d’écran, vidéo et audio, ainsi que sur les statistiques de communication de conversation, comme le nombre d’utilisateurs qui répondent aux messages de canal et les publient, et le nombre d’utilisateurs qui s’engagent dans des messages de conversation 1:1 ou de groupe.

Avec des informations supplémentaires sur les utilisateurs internes et externes, vous pouvez désormais mesurer l’interaction des utilisateurs dans les [canaux partagés](/Teams/shared-channels.md) internes et externes. Par exemple, les métriques telles que le nom du locataire auquel appartient l’utilisateur, les noms de locataires externes où l’utilisateur interagit et si l’utilisateur est externe au locataire aideront les administrateurs à mesurer l’inteaction des utilisateurs via des fonctionnalités de canal partagé. 

> [!NOTE]
> La possibilité de planifier un rapport d’activité utilisateur n’est pas disponible pour l’instant.

## <a name="view-the-user-activity-report"></a>Afficher le rapport d’activité de l’utilisateur

Vous devez être administrateur général, lecteur général ou administrateur de service Teams pour afficher le rapport dans le Centre d’administration Microsoft Teams. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](../using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Analytique & rapports** > **Rapports d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Activité utilisateur Teams**.
2. Sous **Plage de dates**, sélectionnez une plage, puis **sélectionnez Exécuter le rapport**.

    ![Capture d’écran du rapport d’activité des utilisateurs Teams dans le Centre d’administration Teams avec légendes.](../media/teams-reports-user-activity-with-callouts2.png "Capture d’écran du rapport d’activité des utilisateurs Teams dans le Centre d’administration Teams avec légendes")

## <a name="interpret-the-report"></a>Interpréter le rapport

| **Légende** |**Description**  |
|--------|-------------|
|**1**   |Le rapport d’activité des utilisateurs Teams peut être consulté pour connaître les tendances au cours des 7, 30, 90 ou 180 derniers jours. |
|**2**   |Chaque rapport comporte la date à laquelle il a été généré. Les rapports reflètent généralement une latence de 24 à 48 heures par rapport au moment de l’activité. |
|**3**   |Les données de série chronologique représentées dans le graphique supérieur montrent différentes métriques d’utilisation agrégées pour l’ensemble du locataire. |
|**4**   |Les données tabulaires représentées dans la moitié inférieure montrent différentes métriques d’utilisation agrégées par utilisateur. |
|**5**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y indique le nombre d’éléments ou activités actif(ve)s.</li> </ul>Pointez sur le point représentant un élément ou une activité à une date donnée pour voir le nombre d’instances de cet élément ou activité à cette date.|
|**6**   | Chacune des métriques est représentée dans le graphique au niveau du locataire. Filtrez ce que vous voyez sur le graphique en sélectionnant un élément dans la légende. Sélectionnez **Messages de canal**, **Messages de réponse**,  **Messages de conversation** ou **Réunions organisées** , etc. pour afficher les informations relatives à chacun d’eux. La modification de cette sélection ne modifie pas les informations du tableau lui-même. |
|**7**   |Le tableau vous donne une répartition de l’utilisation par utilisateur.   <ul><li>**Nom d’utilisateur** est l’adresse e-mail de l’utilisateur. Consultez [la section suivante](#make-the-user-specific-data-anonymous) pour obtenir des conseils sur la façon de l’anonymiser.  Sélectionnez le nom d’utilisateur pour accéder à la page des détails de l’utilisateur.</li><li>**Nom du locataire** (nouveau) est le nom d’un locataire interne ou externe auquel appartient un utilisateur. Si un utilisateur appartient à un locataire externe, différentes métriques d’utilisation (par exemple, messages de publication, messages de réponse, etc.) sont calculées en fonction de ses interactions dans un ou plusieurs canaux partagés du locataire de l’administrateur. Les interactions effectuées par un utilisateur externe dans son propre locataire ne sont pas prises en compte pour le rapport d’utilisation administrateur d’un locataire donné.  </li><li>**Les noms de locataires de canal partagé** (nouveau) sont les noms des locataires internes ou externes auxquels l’utilisateur a participé dans le cadre d’un canal partagé.</li><li>**Les messages de canal** sont le nombre de messages uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Réponses** est le nombre de messages de réponse uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li> <li>**Les publications** sont le nombre de messages de publication uniques que l’utilisateur a publiés dans un canal d’équipe pendant la période spécifiée.</li><li>**Les messages de conversation** sont le nombre de messages uniques que l’utilisateur a publiés dans une conversation privée au cours de la période spécifiée.</li><li>**Les messages urgents** correspondent au nombre de messages urgents que l’utilisateur a publiés dans une conversation au cours de la période spécifiée.</li><li>**Le nombre total de réunions organisées** correspond à la somme des réunions planifiées, périodiques, non planifiées et non classifiées organisées par un utilisateur pendant la période spécifiée.</li><li>**Réunions planifiées une fois** organisées est le nombre de réunions planifiées ponctuelles qu’un utilisateur a organisées au cours de la période spécifiée.</li><li>**Réunions planifiées périodiques organisées** est le nombre de réunions périodiques qu’un utilisateur a organisées au cours de la période spécifiée.</li><li>**Réunions organisées adhoc** est le nombre de réunions non planifiées qu’un utilisateur a organisées pendant la période spécifiée.</li><li>**Le nombre total de réunions ayant participé** est la somme des réunions planifiées, périodiques, non planifiées et non classifiées auxquelles un utilisateur a participé au cours de la période spécifiée.</li><li>**Réunions à participation planifiées une fois** est le nombre de réunions planifiées ponctuelles auxquelles un utilisateur a participé au cours de la période spécifiée.</li><li>**Réunions planifiées planifiées périodiques** est le nombre de réunions périodiques auxquelles un utilisateur a participé pendant la période spécifiée.</li><li>**Réunions ayant participé est** le nombre de réunions non planifiées auxquelles un utilisateur a participé au cours de la période spécifiée.</li><li>**Appels 1:1** est le nombre d’appels 1:1 auxquels l’utilisateur a participé pendant la période spécifiée.</li><li>**Temps audio** est le temps audio total (en minutes) auquel l’utilisateur a participé pendant la période spécifiée.</li><li>**L’heure de la vidéo** est la durée totale de la vidéo (en minutes) à laquelle l’utilisateur a participé pendant la période spécifiée.</li><li>**Temps de partage d’écran** est le temps total de partage d’écran (minutes) auquel l’utilisateur a participé pendant la période spécifiée.</li>  <li>**La dernière activité** est la dernière date (UTC) à laquelle l’utilisateur a participé à une activité Teams.</li><li>**Une autre activité** effectue le suivi quand l’utilisateur est considéré comme actif, mais a une valeur de zéro pour les messages de conversation, les appels 1:1, les messages de canal, le nombre total de réunions et les réunions organisées. Voici quelques exemples d’actions lorsqu’un utilisateur modifie l’état de Teams ou le message d’état Teams, lorsqu’un utilisateur ouvre un message de canal sans y répondre, ou lorsqu’un utilisateur reçoit un message privé et le lit sans y répondre.</li> </ul> **Les réunions non classifiées** ne peuvent pas être identifiées comme planifiées, périodiques ou non planifiées. Ils sont peu nombreux et ne peuvent souvent pas être identifiés en raison d’informations de télémétrie imparfaites.<br><br>**Les appels de groupe** ont été remplacés par **des réunions organisées ad hoc** et **des réunions ont participé ad hoc**. La somme de ces deux valeurs est égale à ce qui a été mesuré par **les appels de groupe**. <br/><br/>Notez que si un utilisateur n’existe plus, le nom s’affiche sous la forme « - » dans la table.
|**8**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau. |
**9**   |Exportez le rapport vers un fichier CSV à des fins d’analyse hors connexion. Sélectionnez **Exporter vers Excel** pour télécharger le rapport dans votre navigateur. <br>Lorsque vous affichez le rapport dans Excel : <br>- Vous verrez également une colonne **ID d’utilisateur** , qui représente l’ID d’utilisateur. Un ID d’utilisateur est généralement une chaîne alphanumérique. <br>- Vous remarquerez également que les colonnes **Durée de l’audio**, **Durée de la vidéo** et **Durée du partage d’écran** sont représentées en jours et en secondes. |


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques à l’utilisateur anonymes

Pour rendre les données du rapport d’activité utilisateur Teams anonymes, vous devez être administrateur général. Le Administrateur général peut masquer des informations d’identification (à l’aide de hachages MD5), telles que le nom d’affichage, le nom du groupe, l’e-mail et l’ID AAD dans les rapports et leur exportation.

1. Dans Centre d'administration Microsoft 365, accédez à **Paramètres Paramètres** \> **Paramètres de l’organisation**, puis sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis **affichez les noms des utilisateurs, des groupes et des sites masqués dans tous les rapports**. Ce paramètre est appliqué aux rapports d’utilisation dans Centre d'administration Microsoft 365 et dans le centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.


> [!NOTE]
> L’activation de ce paramètre permet d’identifier les informations de nom d’utilisateur, de groupe et de site dans le [rapport d’activité des utilisateurs Teams](user-activity-report.md), le [rapport d’utilisation des appareils Teams](device-usage-report.md) et le [rapport d’utilisation de Teams](teams-usage-report.md) . À compter du 1er septembre 2021, ce paramètre est activé par défaut pour tout le monde dans le cadre de notre engagement continu à aider à protéger les informations importantes et à permettre aux entreprises de prendre en charge leurs lois locales sur la confidentialité. Ce paramètre s’applique également aux rapports d’utilisation de Microsoft 365 dans les Centre d'administration Microsoft 365, Microsoft Graph et Power BI.
## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
