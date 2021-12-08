---
title: Salles Microsoft Teams’entreprise
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
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Enregistrement d’audit pour TRM.
f1keywords: ''
ms.openlocfilehash: e5e5cd25385f6e8a71484c57aa9c44da5d4c9cd8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331223"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Enregistrement d’audit dans salles Teams service géré

L’audit salles Teams service géré (TRM) vous permet de rechercher des enregistrements d’audit pour les activités effectuées dans le portail par les utilisateurs et les administrateurs. Cette fonctionnalité est activée par défaut. Seul l’administrateur du service géré est autorisé à exporter, puis à afficher les journaux.

> [!NOTE]
> Les actions effectuées dans le service TRM ne sont pas enregistrées dans les Microsoft 365'Office 365 audit 

## <a name="exporting-logs"></a>Exportation de journaux

Lorsque vous exportez tous les résultats pour une recherche dans le journal d’audit, les données brutes du journal d’audit unifié sont copiées dans un fichier de valeurs séparées par des virgules (CSV) téléchargé sur votre ordinateur local. 

**Pour télécharger les journaux** 

1. Voir les **journaux Paramètres >'audit >'équipe.**
1. Pour définir la plage de dates des journaux d’intérêt, entrez la **date de** début et la **date de fin.**

   > [!NOTE]
   > Les journaux ne sont disponibles que pendant 180 jours.

1. Sélectionnez **Les journaux de téléchargement.**

   ![Plage de dates du journal d’audit](../media/multi-tenant-auditing.png)

   Un message affiché en bas de la fenêtre vous invite à ouvrir ou enregistrer le fichier CSV. 

1. Sélectionnez   >  **Enregistrer sous,** puis enregistrez le fichier CSV sur votre ordinateur local. 

1. Le téléchargement de nombreux résultats de recherche lors de la recherche de toutes les activités ou sur une plage de dates étendue prend du temps. Une fois le téléchargement du fichier CSV terminé, un message s’affiche en bas de la fenêtre.

## <a name="detailed-properties-in-the-audit-log"></a>Propriétés détaillées dans le journal d’audit

Le tableau suivant décrit les propriétés incluses dans le tableau CSV.

|Propriété|Description|
| - | - |
|activity.category|<p>Catégorie de l’objet sur lequel l’action a été effectuée. Valeurs possibles ;</p><p>**Utilisateur, Affectation, Invitation partenaire, Rôle**</p>|
|activity.objectName|Nom de l’objet modifié.|
|activity.operation|Type d’opération effectuée. Valeurs possibles : **Créer, Mettre à jour, Supprimer** |
|activity.resultStatus|<p>Indique si l’action (spécifiée dans la propriété **activity.operation)** a réussi ou non.</p><p>La valeur est Réussi **ou** **Échoué.**</p>|
|activity.tenantId|GUID du client sur lequel l’action a été effectuée|
|creationTime|Date et heure en temps universel coordonné (UTC) au format ISO lorsque l’utilisateur a effectué l’activité.|
|user.userId|Utilisateur ayant effectué l’action ayant entraîné la journalisé de l’enregistrement.|
|user.userTenantId|GUID du client de l’utilisateur qui a exécuté l’action|


