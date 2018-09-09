---
title: Sécurité et configuration requises pour Enterprise Voice sur Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Découvrez les composants de sécurité et configuration requis pour Enterprise Voice sur Skype pour Business Server.'
ms.openlocfilehash: 9fd7a4fd35785c0cb4a7c10efb7dc781b84b8186
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887586"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Sécurité et configuration requises pour Enterprise Voice sur Skype pour Business Server
 
**Résumé :** Découvrez les composants de sécurité et configuration requis pour Enterprise Voice sur Skype pour Business Server.
  
Avant de déployer Enterprise Voice, vérifiez que votre infrastructure réunit la sécurité suivante, configuration de l’utilisateur et conditions préalables matérielles des scénarios spécifiques. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Droits d’administration et infrastructure de certificats

Avant de procéder au déploiement, vérifiez les points suivants :
  
- Les administrateurs déployant Enterprise Voice doivent être membres du groupe RTCUniversalServerAdmins.
    
- Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
  - **CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
  - **CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.
    
  - **CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
- L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    > [!NOTE]
    > Pour plus d’informations sur les certificats requis dans Skype pour Business Server, consultez [exigences pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [configuration serveur requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuration utilisateur

Si vous colocalisé le serveur de médiation à chaque pool frontal ou Standard Edition server au cours du déploiement frontal, les paramètres utilisateur nécessaires pour Enterprise Voice ont été configurés automatiquement lors de l’installation des fichiers de ces rôles de serveur.
  
Si vous déployez nouvellement la charge de travail Enterprise Voice à ce stade, avant de commencer le processus de déploiement, désigner un numéro de téléphone principal pour chaque utilisateur qui vous envisagez d’activer pour Enterprise Voice. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant l’implémentation, principal tous les téléphone numéros doivent être normalisées (correctement mis en forme) et copié dans la propriété **URI de ligne** de chaque utilisateur à l’aide de Skype pour le panneau de configuration serveur Business.
  
> [!NOTE]
> Pour obtenir des exemples des numéros de téléphone principaux requis pour le déploiement de Voix Entreprise, reportez-vous à la rubrique [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Étapes suivantes : installation des fichiers ou configuration de la connectivité RTC

Après avoir vérifié les logiciels et les conditions préalables pour Enterprise Voice, vous pouvez :
  
- Installer le serveur de médiation, comme décrit dans [déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server](deploy-a-mediation-server.md), mais uniquement si vous souhaitez déployer un serveur de médiation autonome ou un pool, car les serveurs de médiation sont installés dans le cadre du serveur frontal pool ou le processus de déploiement de Standard Edition server lorsque colocalisés.
    
- Ou, commencer à configurer les paramètres pour acheminer les appels pour les utilisateurs d’Enterprise Voice, comme décrit dans [configurer les jonctions dans Skype pour Business Server](configure-trunks.md).
    

