---
title: Rapport d’utilisation des événements en direct Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Découvrez comment utiliser le rapport d’utilisation des événements en direct Teams dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble de l’activité des événements en direct Teams dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 970247bf863942a4f938f96e30533ff550d37e94
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "68964980"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Rapport d’utilisation des événements en direct Microsoft Teams

Le rapport d’utilisation des événements en direct Teams dans le Centre d’administration Microsoft Teams vous montre la vue d’ensemble de l’activité pour les événements en direct organisés dans votre organisation. Vous pouvez afficher les informations d’utilisation, notamment l’état de l’événement, l’heure de début, les vues et le type de production pour chaque événement. Vous pouvez obtenir des informations sur les tendances d’utilisation et voir qui, dans votre organisation, planifie, présente et produit des événements en direct.

## <a name="view-the-live-event-usage-report"></a>Afficher le rapport d’utilisation des événements en direct

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Analytics & rapports** > **Rapports d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation des événements en direct Teams**.
2. Sous **Plage de dates**, sélectionnez une plage prédéfinie ou définissez une plage personnalisée. Vous pouvez définir une plage pour afficher les données jusqu’à un an, six mois avant et après la date actuelle.
3. (Facultatif) Sous **Organisateur**, vous pouvez choisir d’afficher uniquement les événements en direct organisés par un utilisateur spécifique.
4. Cliquez sur **Exécuter le rapport**.  

   :::image type="content" alt-text="Capture d’écran du rapport d’utilisation des événements en direct Teams dans le Centre d’administration Teams avec légendes." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport d’événements en direct Teams peut être consulté pour connaître les tendances des 7 derniers jours, 28 jours ou une plage de dates personnalisée que vous définissez. |
|**2**   |Chaque rapport a une date de génération. Le rapport reflète l’activité en quasi-temps réel lorsque la page est actualisée. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y est le nombre total de vues.</li> </ul>Pointez sur le point à une date donnée pour voir le nombre de vues sur tous les événements en direct à cette date.|
|**4**   |Le tableau vous donne une répartition de chaque événement en direct. <ul><li>**Event** est le nom complet de l’événement en direct. Cliquez sur le nom de l’événement pour [obtenir plus de détails](#view-event-details) sur l’événement. </li> <li>**L’heure de début** fait référence à la date et à l’heure de début de l’événement.</li> <li>**État de** l’événement indique si l’événement a eu lieu.  </li><li>**Organisateur** est le nom de l’organisateur de l’événement.</li> <li>**Les présentateurs** sont les noms des présentateurs d’événements.</li><li>**Les producteurs** sont les noms des producteurs de l’événement.</li><li>**Views** est le nombre de vues uniques une fois l’événement terminé.</li><li>**L’enregistrement** indique si le paramètre d’enregistrement est activé ou désactivé.</li><li>**Le type de production** indique si l’événement est produit dans Teams ou par une application ou un appareil externe.</li></li> </ul>Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur est affiché sous la forme « -- » dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|

## <a name="notes"></a>Remarques
Nous affichons un maximum de 100 événements en direct qui correspondent aux critères actuels du rapport. Pour afficher davantage d’événements en direct, appliquez des filtres de date pour réduire la taille de la liste.

Les présentateurs anonymes ne seront pas inclus dans le rapport.

Toute personne qui regarde l’enregistrement de l’événement ou de l’événement à la demande ne sera pas incluse dans le nombre d’affichages. 

## <a name="view-event-details"></a>Afficher les détails de l’événement

La page détails de l’événement en direct vous donne un résumé des détails d’un événement en direct et répertorie tous les fichiers, y compris les transcriptions et les enregistrements, associés à l’événement. Cliquez sur un nom de fichier pour afficher ou télécharger le fichier.

:::image type="content" alt-text="Capture d’écran montrant les détails d’un événement en direct." source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

Si votre organisation utilise Microsoft eCDN, les analyses avancées peuvent être consultées et exportées à partir du [tableau de bord eCDN](https://admin.ecdn.microsoft.com).  Si votre organisation est activée pour [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) eCDN ou [Kollective](https://kollective.com) eCDN, vous pouvez obtenir des analyses de participants supplémentaires en cliquant sur le lien du rapport partenaire.

## <a name="related-topics"></a>Voir aussi

- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Que sont les événements en direct Teams ?](../teams-live-events/what-are-teams-live-events.md)
