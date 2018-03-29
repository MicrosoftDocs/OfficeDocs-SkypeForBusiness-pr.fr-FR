---
title: Conditions préalables requises de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Découvrez les conditions de sécurité et de configuration requises pour Voix Entreprise dans Skype pour Business Server 2015.'
ms.openlocfilehash: 400af6d42026007315e30a7706e9730901f90708
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a>Conditions préalables requises de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur les conditions de sécurité et de configuration requises pour Voix Entreprise dans Skype pour Business Server 2015.
  
Avant le déploiement de Voix Entreprise, vérifiez que votre infrastructure répond aux suivante de sécurité, configuration de l’utilisateur et les conditions matérielles spécifiques d’un scénario. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Droits d’administration et infrastructure de certificats

Avant de procéder au déploiement, vérifiez les points suivants :
  
- Les administrateurs de déploiement de Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.
    
- Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
  - **CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
  - **CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.
    
  - **CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
- L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    > [!NOTE]
    > Pour plus d’informations sur la configuration requise des certificats dans Skype pour Business Server, reportez-vous à la section [exigences environnementales pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). 
  
## <a name="user-configuration"></a>Configuration utilisateur

Si vous colocalisé avec chaque pool frontal, le serveur de médiation ou le serveur Standard Edition server pendant le déploiement de Front-End, les paramètres utilisateur nécessaires pour les Voix Entreprise ont été configurés automatiquement lors de l’installation des fichiers de ces rôles de serveur.
  
Si vous déployez récemment la charge de travail de Voix Entreprise à ce moment, avant de commencer le processus de déploiement, désigner un numéro de téléphone principal pour chaque utilisateur à qui vous souhaitez activer pour les Voix Entreprise. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant la mise en oeuvre, principal de tous les de téléphone numéros doivent être normalisées (correctement mis en forme) et copiés vers la propriété de **Ligne URI** de chaque utilisateur à l’aide de Skype pour le panneau de configuration de Business Server.
  
> [!NOTE]
> Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la rubrique [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Étapes suivantes : installation des fichiers ou configuration de la connectivité RTC

Après avoir vérifié le logiciel et la configuration requise pour les Voix Entreprise, vous pouvez :
  
- Installer le serveur de médiation, comme décrit dans le [déploiement d’un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015](deploy-a-mediation-server.md), mais uniquement si vous souhaitez déployer un serveur de médiation autonome ou un pool, car les serveurs de médiation sont installés dans le cadre de l’avant Pool de fin ou le processus de déploiement du serveur Standard Edition lorsque colocalisés.
    
- Ou bien, commencer à configurer les paramètres à acheminer les appels pour les utilisateurs de Voix Entreprise, comme décrit dans les [puits de configurer dans Skype pour Business Server 2015](configure-trunks.md).
    

