---
title: Microsoft Teams d’utilisation d’événements en direct
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Découvrez comment utiliser le rapport d’utilisation Teams d’événements en direct dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble de Teams activité d’événements en direct dans votre organisation.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 504c8822146efa7101ca1435cab961a86068ccaf
ms.sourcegitcommit: 4df3d144296b9b8982109be7edaffd636aabdf29
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60959893"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams d’utilisation d’événements en direct

Le Teams d’utilisation des événements en direct dans le centre Microsoft Teams d’administration vous donne une vue d’ensemble de l’activité pour les événements en direct qui se tiennent dans votre organisation. Vous pouvez afficher les informations d’utilisation, y compris l’état d’événement, l’heure de début, les affichages et le type de production pour chaque événement. Vous pouvez obtenir des informations sur les tendances d’utilisation et voir qui dans votre organisation planifier, présenter et produire des événements en direct.

## <a name="view-the-live-event-usage-report"></a>Afficher le rapport d’utilisation des événements en direct

1. Dans le panneau de navigation gauche du Centre Microsoft Teams’administration, cliquez sur **Analyse & rapports**  >  **d’utilisation.** Sous **l’onglet Afficher les rapports,** sous **Rapport,** sélectionnez **Teams’utilisation des événements en direct.**
2. Sous **Plage de dates,** sélectionnez une plage prédéfinée ou définissez une plage personnalisée. Vous pouvez définir une plage pour afficher les données jusqu’à une année, six mois avant et après la date actuelle.
3. (Facultatif) Sous **Organisateur,** vous pouvez choisir d’afficher uniquement les événements en direct organisés par un utilisateur spécifique.
4. Cliquez sur **Exécuter le rapport.**  

   :::image type="content" alt-text="Capture d’écran Teams rapport d’utilisation des événements en direct dans Teams centre d’administration avec des appels." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>Interpréter le rapport

|Légende |Description  |
|--------|-------------|
|**1**   |Le Teams des événements en direct peut être pris en compte pour les tendances des 7, 28 derniers jours ou une plage de dates personnalisée que vous avez définie. |
|**2**   |Chaque rapport indique la date à laquelle il a été généré. Le rapport reflète l’activité en temps quasi réel lors de l’actualisation de la page. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y est le nombre total d’affichages.</li> </ul>Pointez sur le point sur une date donnée pour voir le nombre de vues sur tous les événements en direct de cette date.|
|**4**   |Le tableau vous offre une répartition par événement en direct. <ul><li>**L’événement** est le nom d’affichage de l’événement en direct. Cliquez sur le nom de l’événement [pour obtenir plus de détails](#view-event-details) sur l’événement. </li> <li>**L’heure de** début fait référence à la date et à l’heure de début de l’événement.</li> <li>**Le statut de l’événement** indique si l’événement a eu lieu.  </li><li>**Organisateur** est le nom de l’organisateur de l’événement.</li> <li>**Les présentateurs** sont les noms des présentateurs de l’événement.</li><li>**Les producteurs** sont les noms des producteurs d’événements.</li><li>**Les affichages** sont le nombre d’affichages uniques une fois l’événement terminé.</li><li>**L’enregistrement** indique si le paramètre d’enregistrement est en cours ou non.</li><li>**Le type de** production indique si l’événement est produit dans une Teams par une application ou un appareil externe.</li></li> </ul>Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur s’affiche en tant que « - » dans le tableau. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|

## <a name="notes"></a>Remarques
Nous montrons jusqu’à 100 événements en direct qui correspondent aux critères du rapport actuel. Pour voir davantage d’événements en direct, appliquez des filtres de date afin de réduire la taille de la liste. 

Toute personne qui regarde l’enregistrement de l’événement ou de l’événement à la demande ne figure pas dans le nombre d’affichages. 

## <a name="view-event-details"></a>Afficher les détails de l’événement

La page des détails de l’événement en direct offre un résumé des détails d’un événement en direct et répertorie tous les fichiers, y compris les transcriptions et enregistrements, associés à l’événement. Cliquez sur un nom de fichier pour afficher ou télécharger le fichier.

:::image type="content" alt-text="Capture d’écran montrant les détails d’un événement en direct." source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

Si votre organisation est [](https://www.hivestreaming.com/partners/integration-partners/microsoft/) activée pour la ruche eCDN ou l’eCDN [Kollective,](https://kollective.com) vous pouvez obtenir des données d’analyse des participants supplémentaires en cliquant sur le lien du rapport partenaire.

## <a name="related-topics"></a>Sujets associés

- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Que sont les événements en direct Teams ?](../teams-live-events/what-are-teams-live-events.md)
