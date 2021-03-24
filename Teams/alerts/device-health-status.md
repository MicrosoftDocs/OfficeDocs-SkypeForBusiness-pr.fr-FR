---
title: Surveillance et alerte sur les appareils de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les fonctionnalités de surveillance et d’alerte de Teams dans le Centre d’administration Microsoft Teams pour surveiller de façon proactive l’état d’état des appareils Teams
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8c6a4ac89ddc90bcb00cf2741874e49a26ac775f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096474"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Surveillance de l’état des appareils de Microsoft Teams

La surveillance de l’état des appareils dans le Centre d’administration Microsoft Teams vous permet de surveiller de façon proactive l’état de différents appareils Teams. Surveillez l’état hors connexion d’un appareil et recevez des alertes en temps réel si l’appareil surveillé dans votre organisation se déconnecte.  

Avant de commencer, vous avez besoin des autorisations de création d’équipes/canaux dans votre client. [En savoir plus.](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)

## <a name="configure-device-state-rule"></a>Configurer la règle d’état de l’appareil

1. Dans la barre de navigation gauche du Centre d’administration Microsoft Teams, sélectionnez Notifications et & **des**  >  **alertes.**

   ![Section Règles dans le Centre d’administration](../media/select-rules.png)

2. Dans la page **Règles,** sélectionnez **Règle d’état de l’appareil.**

3. Sélectionnez l’appareil pour configurer la règle d’état afin d’activer les alertes.

    ![Page de règle d’état des appareils Teams.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpréter la configuration de la règle


|Champ |Description  |
|--------|-------------|
|**Type de règle**   |La règle d’état de l’appareil vous aide à gérer efficacement. Les appareils Teams et sont classés comme types de gestion des appareils. À l’avenir, d’autres règles de type de gestion des appareils seront disponibles pour surveiller d’autres fonctionnalités associées (par exemple, un appareil défectueux et l’état de la connectez-vous du périphérique).|
|**Condition**   |Vous pouvez surveiller l’état des appareils s’ils sont hors connexion. [En savoir plus sur](../devices/device-management.md) la gestion des appareils dans le Centre d’administration Teams. |
|**Étendue**   |Vous pouvez spécifier la fréquence à laquelle vous voulez surveiller l’état d’état de l’appareil en mentionnant la fréquence d’évaluation de la règle. Par défaut, les appareils Teams sont surveillés en temps quasi réel s’ils sont déconnectés. |
|**Utilisateurs d’appareils**   |Vous pouvez spécifier les appareils qui ont besoin d’une surveillance proactive de l’utilisation hors connexion en les sélectionnant en fonction des utilisateurs connectés. Pour plus [d’informations, voir](#select-devices-for-configuration) Sélectionner des appareils pour plus d’informations. |
|**Actions**  >  **Alerte de canal**   |Dans la section Actions, vous pouvez spécifier les canaux d’équipes pour qui vous souhaitez obtenir des alertes. Actuellement, une équipe par défaut nommée **Alertes** et notifications d’administrateur et canal **MonitoringAlerts** est créée où les notifications sont remis. <BR/> <BR/> Les administrateurs globaux et les administrateurs Teams de votre client sont automatiquement ajoutés à cette équipe par défaut.|
|**Actions**  >  **Web se**   |Vous pouvez également recevoir des notifications avec un site web externe (facultatif). Spécifiez une URL de site web externe public dans la section web de notification où une charge utile de notification JSON sera envoyée. <BR/> <BR/>  La charge utile de notification, via des sites web, peut être intégrée à d’autres systèmes de votre organisation pour créer des flux de travail personnalisés.<br/><br/> 

**Schéma de charge utile JSON pour le web :** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Exemple de charge utile JSON**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Sélectionner des appareils pour la configuration

1. Vous pouvez sélectionner les appareils Teams que vous voulez surveiller en sélectionnant les utilisateurs connectés à ces appareils. Sélectionnez **Ajouter dans** la section **Utilisateurs de l’appareil.**

2. Sélectionnez un ou plusieurs utilisateurs pour lesquels vous souhaitez surveiller l’état d’état de l’appareil

   ![ajouter un utilisateur à la règle d’état d’état de l’appareil.](../media/select-device-users.png )

   La liste sélectionnée des utilisateurs s’affiche dans la section **Utilisateurs d’appareil.** Vous pouvez modifier cette liste en ajoutant ou en supprimant des utilisateurs.

Tous les appareils de connexion utilisés par la liste d’utilisateurs sélectionnée seront contrôlés pour vérifier l’état d’état du mode hors connexion.

## <a name="notifications-in-teams-client"></a>Notifications dans le client Teams

Les notifications sont remis dans le canal **MonitoringAlerts** créé automatiquement de l’équipe d’alertes et de notifications de **l’administrateur.**

Une notification hors connexion d’appareil peut inclure les informations suivantes :

- Nom de l’appareil hors connexion.
- Utilisateur de l’appareil hors connexion.
- Heure à quelle heure l’appareil s’est déconnecté ? (Actuellement, l’heure est présentée en UTC.)
- Type de règle qui a élevé l’alerte.
- Pourquoi une alerte est-elle élevée ?