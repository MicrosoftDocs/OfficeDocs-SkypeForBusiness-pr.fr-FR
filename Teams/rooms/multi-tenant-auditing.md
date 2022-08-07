---
title: Audit multilocataire
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Journalisation d’audit pour TRM.
f1keywords: ''
ms.openlocfilehash: de7f01a3c93dc31ff10c9e00cb3d0f3ef5806cb3
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269101"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Journalisation d’audit dans le service managé salles Teams

L’audit dans salles Teams service managé (TRM) vous permet de rechercher les enregistrements d’audit pour les activités effectuées dans le portail par les utilisateurs et les administrateurs. Cette fonctionnalité est activée par défaut. Seul l’administrateur du service géré a l’autorisation d’exporter, puis d’afficher les journaux.

> [!NOTE]
> Les actions effectuées dans le service TRM ne sont pas enregistrées dans Microsoft 365 ou l’audit Office 365 

## <a name="exporting-logs"></a>Exportation de journaux d’activité

Lorsque vous exportez tous les résultats d’une recherche dans le journal d’audit, les données brutes du journal d’audit unifié sont copiées dans un fichier de valeurs séparées par des virgules (CSV) téléchargé sur votre ordinateur local. 

**Pour télécharger les journaux d’activité** 

1. Accédez à **Paramètres > journaux d’audit > généraux**.
1. Pour définir la plage de dates des journaux d’intérêt, **entrez la date de début** et la **date de fin.**

   > [!NOTE]
   > Les journaux d’activité ne sont disponibles que pendant 180 jours.

1. Sélectionnez **Télécharger les journaux.**

   ![Plage de dates du journal d’audit](../media/multi-tenant-auditing.png)

   Un message affiché en bas de la fenêtre vous invite à ouvrir ou enregistrer le fichier CSV. 

1. Sélectionnez **Enregistrer** > **sous**, puis enregistrez le fichier CSV sur votre ordinateur local. 

1. Il faut un certain temps pour télécharger de nombreux résultats de recherche lors de la recherche de toutes les activités, ou sur une plage de dates étendue. Une fois le téléchargement du fichier CSV terminé, un message s’affiche en bas de la fenêtre.

## <a name="detailed-properties-in-the-audit-log"></a>Propriétés détaillées dans le journal d’audit

Le tableau suivant décrit les propriétés incluses dans le fichier CSV.

|Propriété|Description|
| - | - |
|activity.category|<p>Catégorie de l’objet sur lequel l’action a été effectuée. Valeurs possibles ;</p><p>**Utilisateur, Affectation, PartnerInvitation, Rôle**</p>|
|activity.objectName|Nom de l’objet qui a été modifié.|
|activity.operation|Type d’opération effectuée. Les valeurs possibles sont : **Créer, Mettre à jour, Supprimer** |
|activity.resultStatus|<p>Indique si l’action (spécifiée dans la propriété **activity.operation** ) a réussi ou non.</p><p>La valeur est **Réussite** ou **Échec**.</p>|
|activity.tenantId|GUID du locataire sur lequel l’action a été effectuée|
|creationTime|Date et heure en temps universel coordonné (UTC) au format ISO lorsque l’utilisateur a effectué l’activité.|
|user.userId|Utilisateur qui a effectué l’action qui a entraîné la journalisation de l’enregistrement.|
|user.userTenantId|GUID du locataire pour l’utilisateur qui a effectué l’action|


