---
title: Microsoft Teams Surveillance et alerte des appareils
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
description: Découvrez comment utiliser les fonctionnalités de surveillance et d’alerte Teams dans le Centre d’administration Microsoft Teams pour surveiller de manière proactive l’état d’Teams appareils
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336195"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams l’état de l’appareil

La surveillance de l’état des appareils dans Microsoft Teams centre d’administration vous permet de surveiller de manière proactive l’état de Teams périphériques. Surveillez l’état hors connexion d’un appareil et recevez des alertes en temps réel si l’appareil surveillé dans votre organisation est hors connexion.  

Avant de commencer, vous aurez besoin des autorisations de création d’équipes/de canaux dans votre client. [En savoir plus.](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)

## <a name="configure-device-state-rule"></a>Configurer la règle d’état de l’appareil

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, sélectionnez **Notifications & règles d’alertes.**  >  

   ![Section Règles dans le Centre d’administration](../media/select-rules.png)

2. Dans la page **Règles,** sélectionnez **Règle d’état de l’appareil.**

3. Sélectionnez l’appareil pour configurer la règle d’état pour l’activation des alertes.

    ![Teams page règle d’état des appareils.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpréter la configuration de la règle


|Champ |Description  |
|--------|-------------|
|**Type de règle**   |La règle d’état de l’appareil vous aide à gérer efficacement. Teams appareils et est classé en tant que type de gestion des appareils. À l’avenir, d’autres règles de type de gestion des appareils seront disponibles pour surveiller d’autres fonctionnalités associées (par exemple : périphérique défectueux et état de la signature de l’appareil).|
|**Condition**   |Vous pouvez surveiller l’état des appareils s’ils sont déconnectés. [Pour en savoir plus](../devices/device-management.md) sur la gestion des appareils, Teams centre d’administration. |
|**Scope**   |Vous pouvez spécifier la fréquence à laquelle vous souhaitez surveiller l’état d’état de l’appareil en mentionnant la fréquence d’évaluation des règles. Par défaut, les appareils teams sont surveillés en temps quasi réel s’ils sont mis hors connexion. |
|**Utilisateurs d’appareils**   |Vous pouvez spécifier les appareils qui ont besoin d’une surveillance proactive de l’analyse hors connexion en les sélectionnant en fonction des utilisateurs connectés. Pour plus [d’informations, voir](#select-devices-for-configuration) Sélectionner des appareils pour la configuration. |
|**Actions**  >  **Alerte de canal**   |Dans la section Actions, vous pouvez spécifier les canaux d’équipes pour qui vous souhaitez obtenir des alertes. Actuellement, une équipe par défaut nommée Alertes et **notifications** d’administration et canal **nommé MonitoringAlerts** sera créée là où les notifications seront remis. <BR/> <BR/> Les administrateurs globaux et Teams administrateurs de votre client seront automatiquement ajoutés à cette équipe par défaut.|
|**Actions**  >  **Webhook**   |Vous pouvez également recevoir des notifications avec un webhook externe (facultatif). Spécifiez une URL de webhook public externe dans la section webhook où une charge utile de notification JSON sera envoyée. <BR/> <BR/>  La charge utile de notification, via les webhooks, peut être intégrée à d’autres systèmes de votre organisation pour créer des flux de travail personnalisés.<br/><br/> 

**Schéma de charge utile JSON pour le webhook :** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Exemple de charge utile JSON**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Sélectionner des appareils pour la configuration

1. Vous pouvez sélectionner Teams que vous souhaitez surveiller en sélectionnant les utilisateurs connectés à ces appareils. Sélectionnez **Ajouter dans** la section **Utilisateurs de l’appareil.**

2. Sélectionnez un ou plusieurs utilisateurs pour lesquels vous souhaitez surveiller l’état d’état de l’appareil

   ![ajouter un utilisateur à la règle d’état d’état de l’appareil.](../media/select-device-users.png )

   La liste sélectionnée des utilisateurs s’affiche dans la section **Utilisateurs d’appareils.** Vous pouvez modifier cette liste en ajoutant ou en supprimant des utilisateurs.

Tous les périphériques de connexion utilisés par la liste sélectionnée d’utilisateurs seront surveillés pour l’état d’état d’état hors connexion.

## <a name="notifications-in-teams-client"></a>Notifications dans Teams client

Les notifications sont remis dans le canal **MonitoringAlerts** créé automatiquement de l’équipe d’administration **alertes et notifications.**

Une notification d’appareil hors connexion peut inclure les informations suivantes :

- Nom de l’appareil hors connexion.
- Utilisateur de l’appareil hors connexion.
- Heure à quelle heure l’appareil est passé hors connexion. (Actuellement, l’heure est présentée en UTC.)
- Type de règle qui a élevé l’alerte.
- Pourquoi une alerte est-elle élevée ?