---
title: Conditions préalables à la sécurité et à la configuration d’Enterprise voix dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé: Obtenez des informations sur la sécurité et la configuration requise pour Enterprise Voice dans Skype entreprise Server.'
ms.openlocfilehash: b3fced9ecac9020da9601c2ab6831769b34ae00a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294157"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Conditions préalables à la sécurité et à la configuration d’Enterprise voix dans Skype entreprise Server
 
**Résumé:** En savoir plus sur la sécurité et la configuration requise pour Enterprise Voice dans Skype entreprise Server.
  
Avant de déployer Enterprise Voice, assurez-vous que votre infrastructure répond à la configuration requise en matière de sécurité, de configuration utilisateur et de matériel spécifique. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Droits d’administration et infrastructure de certificats

Avant de procéder au déploiement, vérifiez les points suivants :
  
- Le déploiement d’Enterprise Voice par les administrateurs doit être membre du groupe RTCUniversalServerAdmins.
    
- Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
  - **CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
  - **CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.
    
  - **CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
- L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    > [!NOTE]
    > Pour plus d’informations sur les exigences relatives aux certificats dans Skype entreprise Server, voir [configuration environnementale requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour skype entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuration utilisateur

Si vous avez localisé le serveur de médiation avec chaque pool frontal ou serveur Standard Edition au cours du déploiement frontal, les paramètres utilisateur nécessaires à l’utilisation d’Enterprise Voice étaient configurés automatiquement lors de l’installation des fichiers pour ces rôles de serveur.
  
Si vous venez de déployer la charge de travail voix entreprise pour le moment, avant de commencer le processus de déploiement, spécifiez le numéro de téléphone principal de chaque utilisateur que vous envisagez d’activer pour voix entreprise. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant l’implémentation, tous les numéros de téléphone principal doivent être normalisés (correctement mis en forme) et copiés sur les propriétés d' **URI de ligne** de chaque utilisateur à l’aide de Skype entreprise Server Control Panel.
  
> [!NOTE]
> Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la rubrique [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Étapes suivantes : installation des fichiers ou configuration de la connectivité RTC

Après vérification de la configuration logicielle et environnementale requise pour Enterprise Voice, vous pouvez effectuer l’une des opérations suivantes:
  
- Installez le serveur de médiation, comme décrit dans la rubrique [déploiement d’un serveur de médiation dans le générateur de topologie de Skype entreprise Server](deploy-a-mediation-server.md), mais uniquement si vous voulez déployer un serveur de médiation autonome ou un pool, car les serveurs de médiation sont installés comme partie intégrante du front-end. processus de déploiement d’une réserve ou d’un serveur Standard Edition lorsqu’il est localisé.
    
- Vous pouvez aussi commencer à configurer des paramètres pour acheminer les appels pour les utilisateurs d’Enterprise Voice, comme décrit dans la rubrique [configurer des Trunks dans Skype entreprise Server](configure-trunks.md).
    

