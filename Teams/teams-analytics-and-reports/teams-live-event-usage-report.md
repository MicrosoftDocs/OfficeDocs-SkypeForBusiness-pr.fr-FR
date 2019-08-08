---
title: Rapport sur l’utilisation des événements Microsoft teams Live
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment utiliser le rapport d’utilisation du centre d’administration Microsoft teams dans le centre d’administration Microsoft teams pour avoir une vue d’ensemble des activités d’événements en direct au sein de votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4eacd7df49de824ac6c0a98b7b923331fdee61f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239805"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Rapport sur l’utilisation des événements Microsoft teams Live

Le rapport utilisation des événements en direct dans le centre d’administration Microsoft teams vous montre la vue d’ensemble des activités liées aux événements en direct au sein de votre organisation. Vous pouvez afficher les informations d’utilisation, telles que l’état de l’événement, l’heure de début, les affichages et le type de production pour chaque événement. Vous pouvez découvrir les tendances d’utilisation et savoir qui dans votre organisation planifie, présente et génère des événements en direct. 

![Capture d’écran du rapport d’utilisation des événements en direct teams dans le centre d’administration Microsoft teams] (../media/teams-live-event-usage-report.png "Capture d’écran du rapport utilisation de Microsoft teams dans le centre d’administration")

## <a name="view-the-report"></a>Afficher le rapport

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, cliquez sur **analyse & rapports**, puis sous **rapport**, sélectionnez **utilisation des événements en direct**par Teams.
2. Sous **plage de dates**, sélectionnez une plage prédéfinie ou définissez une plage personnalisée. Vous pouvez définir une plage pour afficher les données jusqu’à une année, six mois avant et après la date du jour.
3. Facultatif Sous **organisateur**, vous pouvez choisir d’afficher uniquement les événements dynamiques organisés par un utilisateur spécifique.
4. Cliquez sur **exécuter un rapport**.  

## <a name="interpret-the-report"></a>Interpréter le rapport

![Capture d’écran du rapport d’utilisation des événements en direct teams dans le centre d’administration Microsoft teams] (../media/teams-live-event-usage-report-with-callouts.png "Capture d’écran du rapport sur l’utilisation des événements en direct teams dans le centre d’administration avec des légendes numérotées")

|Légende |Description  |
|--------|-------------|
|**1**   |Le rapport sur les événements en direct teams peut être consulté pour les tendances au cours des 7, 28 ou une plage de dates personnalisée que vous définissez. |
|**2**   |Date de génération de chaque rapport. Le rapport reflète une activité en temps réel lors de l’actualisation de la page. |
|**3**   |<ul><li>L’axe X représente la plage de dates sélectionnée pour ce rapport.</li> <li> L’axe Y représente le nombre total de vues.</li> </ul>Pointez sur le point d’une date donnée pour afficher le nombre d’affichages de tous les événements en direct à cette date.|
|**4**   |Le tableau fournit une répartition de chaque événement en direct. <ul><li>**Événement** est le nom d’affichage de l’événement en direct. Cliquez sur le nom de l’événement pour [obtenir plus d’informations](#view-event-details) sur l’événement. </li> <li>**Heure de début** fait référence à la date et l’heure de début de l’événement.</li> <li>**État** de l’événement indique si l’événement a eu lieu.  </li><li>**Organizer** est le nom de l’organisateur d’événements.</li> <li>**** Les présentateurs sont les noms des présentateurs d’événements.</li><li>Les **producteurs** sont les noms des producteurs d’événements.</li><li>**Affichages** indique le nombre d’affichages uniques.</li><li>L' **enregistrement** indique si le paramètre d’enregistrement est activé ou désactivé.</li><li>**Type de production** indique si l’événement se produit dans teams ou par un appareil ou une application externe.</li></li> </ul>Notez que si un compte d’utilisateur n’existe plus dans Azure AD, le nom d’utilisateur est affiché en tant que «--» dans la table. <br><br>Pour afficher les informations que vous souhaitez dans le tableau, veillez à ajouter les colonnes correspondantes au tableau. |
|**5**   |Sélectionnez **Modifier les colonnes** pour ajouter ou supprimer des colonnes dans le tableau.|

## <a name="view-event-details"></a>Afficher les détails des événements

La page Détails de l’événement en direct fournit un résumé des détails d’un événement en direct et répertorie tous les fichiers, y compris les transcriptions et les enregistrements, associés à l’événement. Cliquez sur un nom de fichier pour l’afficher ou le télécharger.

![Capture d’écran montrant les détails d’un événement en direct](../media/teams-live-event-usage-report-event-detail.png)

Si votre organisation est activée pour la [ruche](https://www.hivestreaming.com/partners/integration-partners/microsoft/) ECDN ou [Kollective](https://kollective.com) eCDN, vous pouvez obtenir des analyses de participants supplémentaires en cliquant sur le lien du rapport partenaire.

## <a name="related-topics"></a>Voir aussi
- [Analyses et rapports Teams](teams-reporting-reference.md)
- [Que sont les événements en direct Teams ?](../teams-live-events/what-are-teams-live-events.md)